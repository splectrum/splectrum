# Visual Documentation Examples

## Event-Driven Choreography

### Mermaid Sequence Diagram
```mermaid
sequenceDiagram
    participant U as User
    participant CS as claude-swift
    participant S as splectrum
    participant I as infometish
    
    U->>CS: Create home automation
    CS->>CS: Process in serial
    CS->>S: outbox: need api-mqtt
    S->>S: inbox: process request
    S->>S: Create api-mqtt
    S->>I: outbox: package api-mqtt
    I->>I: Create container
    I->>CS: inbox: api-mqtt ready
    CS->>U: Complete
```

### Component Overview
```mermaid
graph TB
    subgraph "SPlectrum Quartet + Extensions"
        SP[SPlectrum<br/>Engine & APIs]
        IM[InfoMetish<br/>Packaging]
        SE[Sesameh<br/>AI & WoW]
        CA[Carambah<br/>Composition]
        BFP[bare-for-pear<br/>P2P Foundation]
    end
    
    SP -->|packages| IM
    SE -->|guides| SP
    SP -->|components| CA
    CA -->|solutions| IM
    BFP -->|runtime| IM
    
    IM -->|containers| D1[P2P Deploy]
    IM -->|containers| D2[K8s Deploy]
    IM -->|packages| D3[Plain Install]
    
    %% Styling
    classDef engineStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px,color:#000
    classDef packageStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px,color:#000
    classDef aiStyle fill:#e8f5e9,stroke:#1b5e20,stroke-width:2px,color:#000
    classDef composeStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#000
    classDef p2pStyle fill:#fce4ec,stroke:#880e4f,stroke-width:2px,color:#000
    classDef deployStyle fill:#f5f5f5,stroke:#424242,stroke-width:2px,color:#000
    
    class SP engineStyle
    class IM packageStyle
    class SE aiStyle
    class CA composeStyle
    class BFP p2pStyle
    class D1,D2,D3 deployStyle
```

### Colorful Flow Diagram
```mermaid
flowchart LR
    A[User Request] -->|1| B{AI Analysis}
    B -->|2| C[TDD Test]
    C -->|3| D[Implementation]
    D -->|4| E{Quality Gate}
    E -->|Pass| F[Deploy]
    E -->|Fail| C
    
    style A fill:#bbdefb,stroke:#1976d2,color:#000
    style B fill:#c8e6c9,stroke:#388e3c,color:#000
    style C fill:#ffe0b2,stroke:#f57c00,color:#000
    style D fill:#f8bbd0,stroke:#c2185b,color:#000
    style E fill:#d1c4e9,stroke:#512da8,color:#000
    style F fill:#b2dfdb,stroke:#00796b,color:#000
```

### ASCII Alternative
```
User     claude-swift     splectrum      infometish
 │            │              │              │
 ├─request───▶│              │              │
 │            ├──process────▶              │
 │            ├──outbox─────▶              │
 │            │              ├──create────▶│
 │            │              ├──outbox─────▶
 │            │              │              ├──package─▶
 │            │◀───inbox─────────────────┤
 │◀──complete──┤              │              │
```

## Repository Single Concern

### Mermaid Graph
```mermaid
graph TB
    subgraph "Traditional Monolith"
        M[big-app repo]
        M --> B1[Branch 1: Auth]
        M --> B2[Branch 2: API]
        M --> B3[Branch 3: UI]
        B1 -.conflicts.-> B2
        B2 -.conflicts.-> B3
    end
    
    subgraph "SPlectrum Approach"
        A1[api-auth] --> D1[Direct to main]
        A2[api-users] --> D2[Direct to main]
        A3[app-ui] --> D3[Direct to main]
        A1 --event--> A2
        A2 --event--> A3
    end
```

## TDD Quality Gates

### Simple Flow
```
┌───────────────────┐
│  Write Test First │
└────────┬─────────┘
         │
         ▼
┌───────────────────┐     ┌─────────────────┐
│    Test Fails     │────▶│  Implement Code │
└───────────────────┘     └───────┬────────┘
                                     │
                                     ▼
                            ┌─────────────────┐
                            │   Test Passes   │
                            │  ✓ Quality Gate │
                            └───────┬────────┘
                                     │
                                     ▼
                            ┌─────────────────┐
                            │  Commit to Main │
                            └─────────────────┘
```