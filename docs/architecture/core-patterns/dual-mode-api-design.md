# Dual-Mode API Design

## Overview

SPlectrum provides two complementary modes for interacting with all platform functionality, designed to optimize both human understanding and AI collaboration.

## The Two Modes

### 1. Formal API Mode - Documented Precision

**AVRO-backed APIs** serving as the formal, documented interface layer.

**Characteristics:**
- **Schema-defined contracts** - Every input/output formally specified in AVRO
- **Type safety and validation** - All interactions validated against schemas
- **Clear documentation** - Schemas serve as living, enforceable API documentation
- **Discoverability** - AI can read schemas to understand available functionality
- **Interoperability** - Standardized format across the entire ecosystem

**Best for:**
- Initial discovery of platform capabilities
- When precision and validation are critical
- Integration with external systems
- Formal contract enforcement

**Example Usage Pattern:**
```
// Clear, documented, validated
await splectrum.api.processData(schema, inputData, options)
```

### 2. Programmatic Mode - Fluent Expression

**Functional continuation syntax** enabling natural, flowing composition of operations.

**Characteristics:**
- **Continuation-based flow** - Operations chain naturally together
- **Expressive composition** - Complex logic reads like natural thought
- **Flexible orchestration** - Easy to compose multi-step workflows
- **AI-friendly expression** - Matches how AI naturally thinks about sequences

**Best for:**
- Complex workflow composition
- When expressing multi-step logic flows
- Rapid prototyping and exploration
- Natural language to code translation

**Example Usage Pattern:**
```
// Fluent, expressive, compositional
await inputData
  .validate(schema)
  .transform(rules)
  .distribute(peers)
  .onSuccess(handleResult)
  .onError(handleFailure)
```

## AI Collaboration Benefits

### Formal Mode for AI
- **Schema discovery** - AI can read AVRO schemas to understand capabilities
- **Contract verification** - AI knows exactly what inputs are expected
- **Error prevention** - Type validation prevents common integration errors
- **Documentation** - Self-documenting through schema definitions

### Programmatic Mode for AI
- **Natural expression** - AI can "think out loud" in code form
- **Compositional reasoning** - Matches how AI builds complex logic
- **Flow-based thinking** - Aligns with AI's sequential processing approach
- **Rapid iteration** - Easy to modify and extend workflows

## Interoperability

Both modes are **fully interoperable** - the same underlying functionality is accessible through either approach:

```
// Formal API call
const result = await splectrum.api.processData(schema, data, options)

// Equivalent programmatic expression
const result = await data
  .conformTo(schema)
  .process(options)
```

## Implementation Strategy

1. **AVRO schemas** define the authoritative contracts for all functionality
2. **Formal APIs** provide direct schema-validated access
3. **Continuation syntax** provides a fluent wrapper over the same underlying operations
4. **Both modes** share the same execution engine and audit trails

## Design Principles

- **Single Source of Truth** - AVRO schemas define all contracts
- **Mode Equivalence** - Both modes access identical functionality
- **Context-Appropriate** - Use formal for precision, programmatic for composition
- **AI-Optimized** - Both modes designed for effective AI collaboration
- **Human-Readable** - Both modes remain accessible to human developers

---

*Dual-mode design enables optimal interaction patterns for both human developers and AI collaborators.*