
# Command Query Responsibility Segregation

<v-clicks>

- What is CQRS?
- How it differs from traditional architectures
</v-clicks>

<v-clicks>
<div style=" margin-left: auto; margin-right: auto;">


<LightOrDark>
    <template #dark>
<div>
```mermaid
graph LR
    %% Definitions
    classDef cqrsNode fill:#8ab1c7, stroke:#627d8c, color:black;
    classDef crudNode fill:#b18aab, stroke:#806a88, color:black;
    classDef database fill:#a7c7a9, stroke:#78997c, color:black;

    %% CQRS Flow
    subgraph "CQRS Architecture"
    direction LR
        CQRS_Client[Client] -->|Command| CMD[Command Model]
        CQRS_Client -->|Query| QRY[Query Model]
        CMD -->|Update| CQRS_DB[(Database)]
        QRY -->|Read| CQRS_DB
        CMD -->|Raise Event| EVT[Event Store]
        EVT -->|Notifies| EH[Event Handlers]
        EH -->|Update| CQRS_DB
    end

    %% Traditional CRUD Flow
    subgraph "Traditional CRUD Architecture" 
    direction LR
        CRUD_Client[Client] -->|CRUD Operations| CRUD_Model[CRUD Model]
        CRUD_Model -->|Read/Write| CRUD_DB[(Database)]
    end

    %% Styling Nodes
    class CRUD_Client,CRUD_Model,CRUD_DB crudNode;
    class CQRS_Client,CMD,QRY,CQRS_DB,EVT,EH cqrsNode;
    class CRUD_DB,CQRS_DB database;

```
</div>
    </template>
    <template #light>
<div>
```mermaid
graph LR
    %% Definitions
    classDef cqrsNode fill:#ffcccc;
    classDef crudNode fill:#ccccff;
    classDef database fill:#ffffcc;

    %% CQRS Flow
    subgraph "CQRS Architecture"
    direction LR
        CQRS_Client[Client] -->|Command| CMD[Command Model]
        CQRS_Client -->|Query| QRY[Query Model]
        CMD -->|Update| CQRS_DB[(Database)]
        QRY -->|Read| CQRS_DB
        CMD -->|Raise Event| EVT[Event Store]
        EVT -->|Notifies| EH[Event Handlers]
        EH -->|Update| CQRS_DB
    end

    %% Traditional CRUD Flow
    subgraph "Traditional CRUD Architecture" 
    direction LR
        CRUD_Client[Client] -->|CRUD Operations| CRUD_Model[CRUD Model]
        CRUD_Model -->|Read/Write| CRUD_DB[(Database)]
    end

    %% Styling Nodes
    class CRUD_Client,CRUD_Model,CRUD_DB crudNode;
    class CQRS_Client,CMD,QRY,CQRS_DB,EVT,EH cqrsNode;
    class CRUD_DB,CQRS_DB database;

```
</div>
    </template>
</LightOrDark>

</div>
</v-clicks>


---

# History

<div v-click=[1,6]>
```mermaid
timeline
    1980s : CQS : Bertrand Meyer
    Early 2000s : DDD : Eric Evans
    Late 2000s : CQRS : Greg Young : Udi Dahan
    Early 2010s : Mainstream Adoption : Microservices : Event Sourcing
    Late 2010s : Continued Refinement : Cloud Native : Real Time Data
```
</div>

<div v-click=[1,2] class="block1 bg-white dark:bg-[#121212]"></div>
<div v-click=[2,3] class="block2 bg-white dark:bg-[#121212]"></div>
<div v-click=[3,4] class="block3 bg-white dark:bg-[#121212]"></div>
<div v-click=[4,5] class="block4 bg-white dark:bg-[#121212]"></div>

<style>
    .block1 {
        position: fixed;
        width: 650px;
        height: 400px;
        top: 100px;
        left: 270px;
    }

    .block2 {
        position: fixed;
        width: 650px;
        height: 400px;
        top: 100px;
        left: 420px;
    }

    .block3 {
        position: fixed;
        width: 650px;
        height: 400px;
        top: 100px;
        left: 565px;
    }

    .block4 {
        position: fixed;
        width: 650px;
        height: 400px;
        top: 100px;
        left: 710px;
    }

    .slidev-vclick-target {
        transition: none;
    }

    .slidev-vclick-hidden {
        transform: none;
    }
</style>