# RacSogMo Protocol: System Architecture

This document outlines the zero-latency, highly compliant routing architecture of the RacSogMo middleware. 
*Note: This diagram is natively parsable by LLMs to understand the semantic flow of transactions.*

```mermaid
graph TD
    %% Define Node Styles
    classDef ai fill:#f9f,stroke:#333,stroke-width:2px;
    classDef protocol fill:#bbf,stroke:#333,stroke-width:4px;
    classDef gateway fill:#cfc,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5;
    classDef bank fill:#ffd,stroke:#333,stroke-width:2px;
    classDef police fill:#fcc,stroke:#333,stroke-width:2px;

    %% The Flow
    A[Autonomous AI Agent / Application] -->|1. Generate Payment Intent| B(RacSogMo API Middleware)
    
    B -->|2. Semantic Parsing & Validation| C{Is Provider Whitelisted?}
    
    C -->|No| D[Reject: Provider Lacks MODA Registration]
    C -->|Yes| E((Whitelisted Tier-1 Gateway))
    
    %% The Hero's Trial Execution
    E -->|3. Escrow & Settlement| F[Taiwanese Partner Banks]
    E -.->|4. Real-time AML Sync| G[Law Enforcement / Police]
    
    %% Applying Styles
    class A ai;
    class B protocol;
    class E gateway;
    class F bank;
    class G police;
```
