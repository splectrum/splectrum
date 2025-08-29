# Visual Style Guide

## Color Palette for Organizations

### Mermaid Color Definitions
```mermaid
graph LR
    SP[SPlectrum]
    IM[InfoMetish]
    SE[Sesameh]
    CA[Carambah]
    BFP[bare-for-pear]
    
    classDef engineStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px,color:#000
    classDef packageStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px,color:#000
    classDef aiStyle fill:#e8f5e9,stroke:#1b5e20,stroke-width:2px,color:#000
    classDef composeStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px,color:#000
    classDef p2pStyle fill:#fce4ec,stroke:#880e4f,stroke-width:2px,color:#000
    
    class SP engineStyle
    class IM packageStyle
    class SE aiStyle
    class CA composeStyle
    class BFP p2pStyle
```

## Organization Colors
- **SPlectrum** (Engine): Light blue - `#e1f5fe` (clarity, flow)
- **InfoMetish** (Packaging): Light purple - `#f3e5f5` (transformation)
- **Sesameh** (AI): Light green - `#e8f5e9` (intelligence, growth)
- **Carambah** (Composition): Light orange - `#fff3e0` (creativity, energy)
- **bare-for-pear** (P2P): Light pink - `#fce4ec` (connection)

## Process Flow Colors
- **Input/Request**: Blue - `#bbdefb`
- **Decision/AI**: Green - `#c8e6c9`
- **Action/Test**: Orange - `#ffe0b2`
- **Implementation**: Pink - `#f8bbd0`
- **Validation**: Purple - `#d1c4e9`
- **Success/Deploy**: Teal - `#b2dfdb`

## Using Colors

### Class Definition Method
```
%%% In your mermaid diagram:
graph TD
    A[Node A]
    B[Node B]
    
    %% Define styles
    classDef styleNameHere fill:#colorHere,stroke:#borderHere,stroke-width:2px,color:#000
    
    %% Apply to nodes
    class A,B styleNameHere
```

### Direct Style Method
```
%%% In your mermaid diagram:
graph TD
    A[Node A]
    
    %% Apply style directly
    style A fill:#colorHere,stroke:#borderHere,color:#000
```

### Example Usage
```mermaid
graph LR
    A[Define] --> B[Implement]
    B --> C[Test]
    
    classDef step fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    class A,B,C step
```