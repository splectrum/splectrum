# ISSUE_CACHE Workflow Enhancement with MCP Tools

## Overview

This document demonstrates how the ISSUE_CACHE workflow could be enhanced using MCP filesystem tools while maintaining compatibility with existing patterns.

## Current vs Enhanced Implementation

### 1. Cache Directory Initialization

**Current Implementation:**
```bash
# Initialize cache directory if missing
mkdir -p claude/project/cache

# Check if metadata exists
if [ ! -f claude/project/cache/metadata.json ]; then
    echo '{"last_sync": "", "cache_version": "1.0.0"}' > claude/project/cache/metadata.json
fi
```

**Enhanced with MCP:**
```python
# Create cache directory with explicit operation
mcp__filesystem__create_directory("claude/project/cache")

# Check metadata with file info
metadata_info = mcp__filesystem__get_file_info("claude/project/cache/metadata.json")

if not metadata_info:
    # Initialize with structured write
    default_metadata = {
        "last_sync": "",
        "cache_version": "1.0.0",
        "created_at": datetime.utcnow().isoformat() + "Z"
    }
    mcp__filesystem__write_file(
        path="claude/project/cache/metadata.json",
        content=json.dumps(default_metadata, indent=2)
    )
```

### 2. Batch Cache Reading

**Current Implementation:**
```bash
# Read each cache file individually
CURRENT_CACHE=$(cat claude/project/cache/issues.json 2>/dev/null || echo "{}")
MILESTONE_CACHE=$(cat claude/project/cache/milestones.json 2>/dev/null || echo "{}")
METADATA=$(cat claude/project/cache/metadata.json 2>/dev/null || echo "{}")
```

**Enhanced with MCP:**
```python
# Batch read all cache files in one operation
cache_files = mcp__filesystem__read_multiple_files([
    "claude/project/cache/issues.json",
    "claude/project/cache/milestones.json",
    "claude/project/cache/metadata.json"
])

# Parse results with proper error handling
caches = {}
for file_result in cache_files:
    if file_result.success:
        filename = os.path.basename(file_result.path)
        try:
            caches[filename] = json.loads(file_result.content)
        except json.JSONDecodeError:
            caches[filename] = {}
    else:
        # File doesn't exist, use empty default
        filename = os.path.basename(file_result.path)
        caches[filename] = {}
```

### 3. Cache Size Monitoring

**Current Implementation:**
```bash
# No built-in size monitoring
# Would require: du -sh claude/project/cache/
```

**Enhanced with MCP:**
```python
# Get cache directory with sizes
cache_contents = mcp__filesystem__list_directory_with_sizes(
    path="claude/project/cache",
    sortBy="size"
)

# Monitor cache growth
total_size = sum(item.size for item in cache_contents if item.type == "file")
if total_size > 10_000_000:  # 10MB threshold
    print(f"Warning: Cache size ({total_size} bytes) exceeds recommended limit")
    
# Find largest cache file
largest = max(cache_contents, key=lambda x: x.size if x.type == "file" else 0)
print(f"Largest cache file: {largest.name} ({largest.size} bytes)")
```

### 4. Cache Structure Visualization

**Current Implementation:**
```bash
# Manual listing
ls -la claude/project/cache/
```

**Enhanced with MCP:**
```python
# Get structured tree view
cache_tree = mcp__filesystem__directory_tree("claude/project")

# Visualize cache structure
print("Cache Structure:")
print(json.dumps(cache_tree, indent=2))

# Validate expected structure
expected_files = ["issues.json", "milestones.json", "metadata.json"]
cache_files = [
    child["name"] 
    for child in cache_tree.get("children", [])
    if child["name"] == "cache"
    for grandchild in child.get("children", [])
]

missing_files = set(expected_files) - set(cache_files)
if missing_files:
    print(f"Missing cache files: {missing_files}")
```

### 5. Atomic Cache Updates

**Current Implementation:**
```bash
# Write to temp file then move
jq '.' temp_issues.json > claude/project/cache/issues.json
rm temp_issues.json
```

**Enhanced with MCP:**
```python
def atomic_cache_update(cache_file, new_data):
    """Atomically update cache file with rollback on failure"""
    
    # Read current data for rollback
    current = mcp__filesystem__read_file(cache_file)
    
    try:
        # Validate new data structure
        if not isinstance(new_data, dict):
            raise ValueError("Cache data must be a dictionary")
            
        # Write new data
        mcp__filesystem__write_file(
            path=cache_file,
            content=json.dumps(new_data, indent=2)
        )
        
        # Verify write succeeded
        verify = mcp__filesystem__read_file(cache_file)
        if json.loads(verify) != new_data:
            raise ValueError("Cache verification failed")
            
    except Exception as e:
        # Rollback on any failure
        if current:
            mcp__filesystem__write_file(
                path=cache_file,
                content=current
            )
        raise Exception(f"Cache update failed: {e}")
```

### 6. Gap Detection Enhancement

**Current Implementation:**
```bash
# Complex shell pipeline
LAST_CACHED_ISSUE=$(jq -r 'keys | map(tonumber) | max // 0' claude/project/cache/issues.json 2>/dev/null || echo "0")
```

**Enhanced with MCP:**
```python
def detect_cache_gaps():
    """Detect missing issues in cache with detailed reporting"""
    
    # Get file info first to check if cache exists
    cache_info = mcp__filesystem__get_file_info("claude/project/cache/issues.json")
    
    if not cache_info:
        return {
            "has_gaps": True,
            "last_cached": 0,
            "latest_github": None,
            "missing_count": None,
            "cache_status": "missing"
        }
    
    # Read cache file
    cache_content = mcp__filesystem__read_file("claude/project/cache/issues.json")
    cache_data = json.loads(cache_content)
    
    # Find highest cached issue number
    if cache_data:
        last_cached = max(int(k) for k in cache_data.keys())
    else:
        last_cached = 0
    
    # Get latest from GitHub (keeping existing gh command)
    # This would remain as a Bash call since it's GitHub API
    
    return {
        "has_gaps": gaps_exist,
        "last_cached": last_cached,
        "latest_github": latest_github,
        "missing_count": latest_github - last_cached,
        "cache_status": "current" if not gaps_exist else "outdated",
        "cache_size": cache_info.size,
        "last_modified": cache_info.modified
    }
```

## Complete Enhanced Workflow Example

```python
def enhanced_issue_cache_workflow():
    """Enhanced ISSUE_CACHE workflow using MCP tools"""
    
    # 1. Initialize cache structure
    print("Initializing cache structure...")
    mcp__filesystem__create_directory("claude/project/cache")
    
    # 2. Batch read all cache files
    print("Reading cache files...")
    cache_results = mcp__filesystem__read_multiple_files([
        "claude/project/cache/issues.json",
        "claude/project/cache/milestones.json",
        "claude/project/cache/metadata.json"
    ])
    
    # 3. Parse cache data with defaults
    caches = {}
    for result in cache_results:
        filename = os.path.basename(result.path).replace('.json', '')
        if result.success:
            caches[filename] = json.loads(result.content)
        else:
            caches[filename] = {} if filename != "metadata" else {
                "last_sync": "",
                "cache_version": "1.0.0"
            }
    
    # 4. Check cache health
    cache_stats = mcp__filesystem__list_directory_with_sizes("claude/project/cache")
    total_size = sum(f.size for f in cache_stats if f.type == "file")
    print(f"Cache size: {total_size:,} bytes")
    
    # 5. Detect gaps
    gap_info = detect_cache_gaps()
    if gap_info["has_gaps"]:
        print(f"Gap detected: {gap_info['missing_count']} issues need caching")
        
        # 6. Fetch missing issues (using existing gh command)
        # ... GitHub API calls remain the same ...
        
        # 7. Atomic update with validation
        atomic_cache_update(
            "claude/project/cache/issues.json",
            updated_issues
        )
    
    # 8. Update metadata
    metadata = {
        "last_sync": datetime.utcnow().isoformat() + "Z",
        "cache_version": "1.0.0",
        "total_issues": len(caches["issues"]),
        "total_milestones": len(caches["milestones"]),
        "cache_size_bytes": total_size
    }
    
    mcp__filesystem__write_file(
        "claude/project/cache/metadata.json",
        json.dumps(metadata, indent=2)
    )
    
    # 9. Final verification
    tree = mcp__filesystem__directory_tree("claude/project/cache")
    print("Cache structure updated:")
    print(json.dumps(tree, indent=2))
```

## Benefits of MCP Enhancement

### 1. **Atomic Operations**
- Batch reads ensure consistent cache state
- Structured writes with validation
- Built-in rollback capabilities

### 2. **Better Monitoring**
- File size tracking without shell commands
- Modification time tracking
- Directory structure visualization

### 3. **Error Handling**
- Explicit file existence checks
- Structured error responses
- No silent failures from shell redirects

### 4. **Performance**
- Single batch read vs multiple cat commands
- No shell process overhead
- Direct JSON handling without jq

### 5. **Cross-Platform**
- No dependency on Unix commands
- Consistent behavior across systems
- Clearer error messages

## Migration Strategy

1. **Phase 1**: Add MCP tools alongside existing implementation
2. **Phase 2**: Create feature flags to switch between implementations
3. **Phase 3**: Gradually migrate based on success metrics
4. **Phase 4**: Remove legacy implementation after validation

## Compatibility Notes

- GitHub API calls remain unchanged (using `gh` CLI)
- Audit logging continues using existing patterns
- File formats remain identical
- Cache structure unchanged

This enhancement maintains full backward compatibility while providing significant improvements in reliability, performance, and maintainability.