# Benefits of CQRS

<v-clicks>

- Improved performance
- Scalability
- Simplified query logic
- Security benefits

</v-clicks>

<v-clicks>
<div>
<LightOrDark>
    <template #dark>
```mermaid
graph LR
    %% Definitions
    classDef commandNode fill:#8ab1c7, stroke:#627d8c, color:black;
    classDef queryNode fill:#b18aab, stroke:#806a88, color:black;
    classDef databaseNode fill:#a7c7a9, stroke:#78997c, color:black;
    classDef securityNode fill:#ffd966, stroke:#d9d2e9, color:black;
    classDef textNode color:black;

    subgraph Command Model [Command Side]
    A[User Commands] -->|Send Command| B[Command Validation]
    B --> C[Command Handlers]
    C --> D[Data Store Update]
    D --> E[Event Store]
    E --> F[Event Handlers]
    end

    subgraph Query Model [Query Side]
    G[User Queries] -->|Request Data| H[Query Handlers]
    H --> I[Read Model]
    end

    %% Adding locks to symbolize security
    class B,C,D commandNode;
    class H queryNode;
    class E securityNode;
    class B1,C1,D1,H1 securityNode;

    %% Adding text to locks to indicate security
    B -->|Security Layer| B1[Authorization, Validation]
    C -->|Security Layer| C1[Business Rule Enforcement]
    D -->|Security Layer| D1[Audit Logging]
    H -->|Security Layer| H1[Access Control]

    %% Descriptions
    linkStyle 0 stroke:#333,stroke-width:2px,fill:none;

```
<div>
</div>
    </template>
    <template #light>
<div>
```mermaid
graph LR
    subgraph Command Model [Command Side]
    A[User Commands] -->|Send Command| B[Command Validation]
    B --> C[Command Handlers]
    C --> D[Data Store Update]
    D --> E[Event Store]
    E --> F[Event Handlers]
    end

    subgraph Query Model [Query Side]
    G[User Queries] -->|Request Data| H[Query Handlers]
    H --> I[Read Model]
    end

    %% Adding locks to symbolize security
    style B fill:#f9d5e5,stroke:#f66,stroke-width:2px
    style C fill:#f9d5e5,stroke:#f66,stroke-width:2px
    style D fill:#f9d5e5,stroke:#f66,stroke-width:2px
    style H fill:#e3eaa7,stroke:#b5dd88,stroke-width:2px

    %% Adding text to locks to indicate security
    B -->|Security Layer| B1[Authorization, Validation]
    C -->|Security Layer| C1[Business Rule Enforcement]
    D -->|Security Layer| D1[Audit Logging]
    H -->|Security Layer| H1[Access Control]

    %% Styling for the Security Layers
    style B1 fill:#fcf3cf,stroke:#f9e79f,stroke-dasharray: 5 5
    style C1 fill:#fcf3cf,stroke:#f9e79f,stroke-dasharray: 5 5
    style D1 fill:#fcf3cf,stroke:#f9e79f,stroke-dasharray: 5 5
    style H1 fill:#e8daef,stroke:#d7bde2,stroke-dasharray: 5 5

    %% Descriptions
    linkStyle 0 stroke:#333,stroke-width:2px,fill:none;
```
</div>
    </template>
</LightOrDark>

</div>
</v-clicks>