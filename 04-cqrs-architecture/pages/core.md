# Core Components

<v-clicks>

- Command and Query Separation
- Operational vs. Analytical data
- Eventual consistency
</v-clicks>


<v-clicks>
<div>
<LightOrDark>
    <template #dark>
<div>
```mermaid
graph LR
    %% Operational Data
    subgraph "Operational Data"
    OD[Operational Data] -- Input/Update --> CMD[Command Model]
    CMD -- Update --> DS[Data Store]
    end

    %% Analytical Data
    subgraph "Analytical Data"
    DS -- Extract --> QM[Query Model]
    QM -- Analyze/Report --> AD[Analytical Data]
    end

    %% Description
    DS -.-> ETL[ETL Process]
    ETL -.-> AD

    %% Styling for Operational Data
    style OD fill:#8ab1c7,stroke:#627d8c,color:black
    style CMD fill:#8ab1c7,stroke:#627d8c,color:black
    style DS fill:#a7c7a9,stroke:#78997c,color:black

    %% Styling for Analytical Data
    style QM fill:#b18aab,stroke:#806a88,color:black
    style AD fill:#b18aab,stroke:#806a88,color:black
    style ETL fill:#b18aab,stroke:#806a88,color:black

    %% Descriptions
    linkStyle 0 stroke:#333,stroke-width:2px,fill:none;

```
</div>
    </template>
    <template #light>
<div>
```mermaid
graph LR
    %% Operational Data
    subgraph "Operational Data"
    OD[Operational Data] -- Input/Update --> CMD[Command Model]
    CMD -- Update --> DS[Data Store]
    end

    %% Analytical Data
    subgraph "Analytical Data"
    DS -- Extract --> QM[Query Model]
    QM -- Analyze/Report --> AD[Analytical Data]
    end

    %% Description
    DS -.-> ETL[ETL Process]
    ETL -.-> AD

    %% Styling for Operational Data
    style OD fill:#f9d5e5
    style CMD fill:#f4cccc
    style DS fill:#fce5cd

    %% Styling for Analytical Data
    style QM fill:#d9ead3
    style AD fill:#cfe2f3
    style ETL fill:#d9d2e9

    %% Descriptions
    linkStyle 0 stroke:#333,stroke-width:2px,fill:none;
```
</div>
    </template>
</LightOrDark>

</div>
</v-clicks>