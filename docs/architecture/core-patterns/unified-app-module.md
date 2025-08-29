# Apps and Modules: Unified Architecture

## Key Insight: Modules as Stateless Apps

**Revolutionary Simplification**: Modules are equivalent to 'stateless apps' - they can use the same repository template, same naming convention, and same development patterns as apps.

## Unified Development Model

### Single Repository Template
- **One Development Pattern**: `app-*` repositories serve both purposes
- **Unified Naming**: `[package]/[api]/[method]` across all components
- **Same Structure**: AVRO schemas, DSL patterns, and development tooling

### Deployment Flexibility
- **Apps**: Deployed in stateful execution environment
- **Modules**: Packaged as stateless components for code-area installation
- **Same Codebase**: Identical development, different deployment modes

## Implementation Benefits

### For SPlectrum Organization
- **Simplified Repository Types**: Only `api-*` and `app-*` needed
- **No Separate Module Category**: Modules are just a packaging option for apps
- **Unified Tooling**: One template, one development process

### For Developers
- **Single Mental Model**: Everything is an "app"
- **Flexible Deployment**: Choose stateful or stateless deployment
- **Consistent Patterns**: Same naming, same structure, same development flow

### For Architecture
- **Reduced Complexity**: Fewer repository types to manage
- **Cleaner Organization**: No ambiguity about where components belong
- **Easier Maintenance**: Single template to maintain and improve
- **Service Integration**: Cross-app pattern enables specialized development tools

## Technical Implementation

### Module Characteristics
- **Stateless**: Expose methods that execute on supplied data structures
- **No Persistent State**: All data comes from input parameters
- **Code-Area Installation**: Installed like JavaScript modules
- **Same Interface**: `[package]/[api]/[method]` naming convention

### App Characteristics  
- **Stateful**: Live in persistent execution environment
- **Persistent State**: Can maintain state between calls
- **Same Interface**: `[package]/[api]/[method]` naming convention
- **Same Development**: Built using identical templates and patterns

## Organizational Impact

### Before: Two Repository Types
```
SPlectrum/
├── api-* (tool wrappers)
├── app-* (stateful applications)  
└── mod-* (stateless modules) ❌ Unnecessary complexity
```

### After: Unified Architecture
```
SPlectrum/
├── api-* (tool wrappers)
└── app-* (unified: apps + modules) ✅ Elegant simplicity
```

## Deployment Modes

### Stateful Deployment (App Mode)
- Deployed in persistent execution environment
- Can maintain state between calls
- Full application lifecycle management

### Stateless Deployment (Module Mode)
- Packaged for code-area installation
- No persistent state
- Pure function execution on input data

## Development Runtime Requirement

### SPlectrum Engine as Development Runtime
Every `app-*` repository requires a **SPlectrum Engine (SE)** as its development runtime to provide the prerequisites necessary for development, testing, and deployment.

### Cross-App Service Pattern
Instead of inherited APIs, apps use **cross-app invocation** to access common development capabilities:
- `test-runner/validation/execute` - Testing and validation
- `deploy-tools/package/module` - App to module conversion
- `audit-logger/event/record` - Development logging
- `object-builder/factory/create` - Object construction

**Benefits**: Single concern encapsulation, independent evolution, P2P-friendly architecture.

## Conclusion

This unified architecture eliminates unnecessary complexity while maintaining all functional requirements. The same development template serves both stateful apps and stateless modules, with cross-app services providing common capabilities.

**Key Principle**: Simplicity through unification - one development pattern, flexible deployment options, single-concern service apps.