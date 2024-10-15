---
config:
  layout: dagre
  theme: base
---
graph TB
    classDef default fill:#f9f9f9,stroke:#333,stroke-width:2px;
    classDef highlight fill:#e1f5fe,stroke:#01579b,stroke-width:3px;

    subgraph ClientLayer["<div style='font-size:24px'>Client Layer</div>"]
        WebApp["<div style='font-size:18px'>Web Application</div><div style='font-size:14px'>(User interface for web browsers)</div>"]
        MobileApp["<div style='font-size:18px'>Mobile Application</div><div style='font-size:14px'>(User interface for mobile devices)</div>"]
    end

    API["<div style='font-size:18px'>API Gateway</div><div style='font-size:14px'>(Manages and routes all incoming requests)</div>"]

    subgraph CoreServices["<div style='font-size:24px'>Core Services</div>"]
        Auth["<div style='font-size:18px'>Authentication</div><div style='font-size:14px'>(Verifies user identities and manages access)</div>"]
        UserMgmt["<div style='font-size:18px'>User Management</div><div style='font-size:14px'>(Handles user accounts and profiles)</div>"]
        EnergyTrading["<div style='font-size:18px'>Energy Trading</div><div style='font-size:14px'>(Facilitates P2P energy transactions)</div>"]
        Billing["<div style='font-size:18px'>Billing & Payments</div><div style='font-size:14px'>(Manages financial transactions and invoicing)</div>"]
        AssetMgmt["<div style='font-size:18px'>Asset Management</div><div style='font-size:14px'>(Tracks energy assets and their performance)</div>"]
        Reporting["<div style='font-size:18px'>Analytics</div><div style='font-size:14px'>(Generates insights and reports)</div>"]
    end

    subgraph BlockchainLayer["<div style='font-size:24px'>Blockchain Layer</div>"]
        BC["<div style='font-size:18px'>Blockchain Service</div><div style='font-size:14px'>(Ensures transparent and secure transactions)</div>"]
        SC["<div style='font-size:18px'>Smart Contracts</div><div style='font-size:14px'>(Automates trading agreements and settlements)</div>"]
        Tokens["<div style='font-size:18px'>POWR & Sparkz Tokens</div><div style='font-size:14px'>(Digital assets for platform operations)</div>"]
    end

    subgraph DataLayer["<div style='font-size:24px'>Data Layer</div>"]
        KafkaStreams["<div style='font-size:18px'>Kafka Streams</div><div style='font-size:14px'>(Handles real-time data streaming)</div>"]
        DataProcessing["<div style='font-size:18px'>Data Processing</div><div style='font-size:14px'>(Analyzes and transforms data)</div>"]
        MongoDB["<div style='font-size:18px'>MongoDB Atlas</div><div style='font-size:14px'>(Stores flexible, document-based data)</div>"]
        TimeSeriesDB["<div style='font-size:18px'>Time Series DB</div><div style='font-size:14px'>(Stores time-stamped energy data)</div>"]
    end

    subgraph ExternalIntegrations["<div style='font-size:24px'>External Integrations</div>"]
        SmartMeters["<div style='font-size:18px'>Smart Meters</div><div style='font-size:14px'>(Collects energy consumption data)</div>"]
        IoTGateway["<div style='font-size:18px'>IoT Gateway</div><div style='font-size:14px'>(Manages communication with IoT devices)</div>"]
        EnergyGrid["<div style='font-size:18px'>Energy Grid</div><div style='font-size:14px'>(Interfaces with existing power infrastructure)</div>"]
    end

    subgraph PlatformProducts["<div style='font-size:24px'>Platform Products</div>"]
        xGrid["<div style='font-size:18px'>xGrid P2P Trading</div><div style='font-size:14px'>(Enables peer-to-peer energy trading)</div>"]
        uGrid["<div style='font-size:18px'>uGrid Microgrid Trading</div><div style='font-size:14px'>(Facilitates trading within microgrids)</div>"]
        Vision["<div style='font-size:18px'>Vision Energy Traceability</div><div style='font-size:14px'>(Tracks energy from source to consumption)</div>"]
        PPA["<div style='font-size:18px'>PPA Vision</div><div style='font-size:14px'>(Manages power purchase agreements)</div>"]
        MODE["<div style='font-size:18px'>MODE Flex Trading</div><div style='font-size:14px'>(Trades energy flexibility)</div>"]
        TraceX["<div style='font-size:18px'>TraceX Environmental Commodities</div><div style='font-size:14px'>(Trades renewable energy certificates)</div>"]
    end

    subgraph DevOps["<div style='font-size:24px'>DevOps</div>"]
        CICD["<div style='font-size:18px'>CI/CD Pipeline</div><div style='font-size:14px'>(Automates software delivery and deployment)</div>"]
        K8s["<div style='font-size:18px'>Kubernetes Cluster</div><div style='font-size:14px'>(Orchestrates containerized applications)</div>"]
        Monitoring["<div style='font-size:18px'>Monitoring & Logging</div><div style='font-size:14px'>(Tracks system health and performance)</div>"]
    end

    subgraph GCP["<div style='font-size:24px'>Google Cloud Platform</div>"]
        GKE["<div style='font-size:18px'>Google Kubernetes Engine</div><div style='font-size:14px'>(Manages containerized applications)</div>"]
        CloudSQL["<div style='font-size:18px'>Cloud SQL</div><div style='font-size:14px'>(Managed relational database service)</div>"]
        PubSub["<div style='font-size:18px'>Pub/Sub</div><div style='font-size:14px'>(Handles messaging and event streaming)</div>"]
        CloudFunctions["<div style='font-size:18px'>Cloud Functions</div><div style='font-size:14px'>(Runs serverless code in response to events)</div>"]
        CloudStorage["<div style='font-size:18px'>Cloud Storage</div><div style='font-size:14px'>(Stores and retrieves any amount of data)</div>"]
    end

    ClientLayer --> API
    API --> Auth
    API --> CoreServices
    CoreServices <--> BlockchainLayer
    CoreServices <--> DataLayer
    ExternalIntegrations --> DataLayer
    PlatformProducts --> CoreServices
    DevOps --> GCP
    GCP --> CoreServices
    GCP --> DataLayer

    class API,BlockchainLayer,DataLayer highlight;