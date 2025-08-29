# Development Runtime Architecture

## SPlectrum Engine as Development Runtime

### Core Concept
Every `app-*` repository requires a **SPlectrum Engine (SE)** as its development runtime to provide the prerequisites necessary for development, testing, and deployment.

### Development SE Bundle
The **Development SPlectrum Engine** comes preloaded with a curated selection of essential service apps to enable immediate productivity.

## Cross-App Service Pattern

### Architectural Principle
Instead of inherited APIs or implicit composition, SPlectrum uses **cross-app invocation** for common development capabilities, maintaining **single concern encapsulation**.

### Pattern Structure
```
Business App: myapp/user/create
├── Calls: test-runner/validation/execute
├── Calls: deploy-tools/package/build
├── Calls: audit-logger/event/record
└── Calls: object-builder/factory/create

Service Apps (preloaded in Dev SE):
├── test-runner/* (testing concerns)
├── deploy-tools/* (deployment concerns)  
├── audit-logger/* (logging concerns)
└── object-builder/* (factory concerns)
```

### Method Invocation
All methods follow three-part naming: `[package]/[api]/[method]`

**Business App Methods:**
- `myapp/user/create`
- `myapp/user/update`
- `myapp/data/process`

**Service App Methods:**
- `test-runner/validation/execute`
- `deploy-tools/package/module`
- `audit-logger/event/record`
- `object-builder/factory/create`

## Development SE Preloaded Apps

### Essential Service Apps
The Development SE includes these core service apps:

#### **test-runner**
- `test-runner/validation/execute` - Schema and data validation
- `test-runner/suite/run` - Test suite execution
- `test-runner/coverage/report` - Code coverage analysis

#### **deploy-tools**
- `deploy-tools/package/module` - Convert app to module packaging
- `deploy-tools/package/container` - Create container deployments
- `deploy-tools/publish/registry` - Publish to container registry

#### **validation-engine**
- `validation-engine/schema/check` - AVRO schema validation
- `validation-engine/data/verify` - Data structure verification
- `validation-engine/api/validate` - API contract validation

#### **object-builder**
- `object-builder/factory/create` - Object factory patterns
- `object-builder/template/generate` - Code template generation
- `object-builder/schema/build` - Schema-driven object construction

#### **audit-logger**
- `audit-logger/event/record` - Development event logging
- `audit-logger/trace/capture` - Execution trace capture
- `audit-logger/debug/log` - Debug information logging

#### **aux-dev-tools**
- `aux-dev-tools/conversion/app-to-module` - App to module conversion
- `aux-dev-tools/scaffolding/create` - New app scaffolding
- `aux-dev-tools/dependency/analyze` - Dependency analysis

## Benefits of This Architecture

### **Single Concern Encapsulation**
- Each service app has one clear responsibility
- No "god objects" with mixed concerns
- Easy to reason about what each app does

### **Cross-App Invocation Advantages**
- **True modularity** - Each capability is a separate, testable app
- **Independent evolution** - Update service apps without touching business logic
- **Explicit dependencies** - Clear what each app relies on
- **Reusable services** - Multiple apps can use same service apps

### **Development SE Benefits**
- **Immediate productivity** - All essential tools ready out-of-box
- **No setup friction** - No hunting for testing/deployment/validation apps
- **Consistent environment** - Every developer gets same foundational tools
- **Runtime optimization** - Preloaded apps perform better than on-demand loading

### **P2P Architecture Alignment**
- **Decentralized** - No monolithic "base" methods
- **Composable** - Mix and match service apps as needed
- **Distributed** - Each service app can run on different peers
- **Extensible** - Add new service apps without changing existing ones

## Implementation Flow

### App Development Process
1. **Initialize** - Start with Development SE runtime
2. **Develop** - Write business logic in `app-*` repository
3. **Test** - Use `test-runner` service app for validation
4. **Package** - Use `deploy-tools` for module/container creation
5. **Deploy** - Use deployment service apps for distribution

### Service App Integration
```javascript
// Business app calls service app
const result = await splectrum.invoke('test-runner/validation/execute', {
  schema: mySchema,
  data: myData
});

// Service app processes request and returns result
if (result.valid) {
  // Continue with business logic
}
```

## Extensibility

### Adding New Service Apps
The Development SE can be extended with additional service apps:
- `security-scanner/*` - Security analysis tools
- `performance-profiler/*` - Performance analysis
- `documentation-generator/*` - Auto-documentation tools
- `integration-tester/*` - Cross-app integration testing

### Custom Service Apps
Organizations can develop custom service apps for specific needs:
- `company-standards/validation/check` - Company-specific validation
- `legacy-bridge/conversion/migrate` - Legacy system integration
- `custom-deployment/platform/deploy` - Custom deployment targets

## Conclusion

This architecture provides the **convenience of implicit composition** with the **architectural benefits of cross-app invocation**. Developers get immediate productivity with essential tools while maintaining clean separation of concerns and P2P-friendly architecture.

**Key Principle**: Single concern encapsulation through cross-app services, bundled for developer convenience.