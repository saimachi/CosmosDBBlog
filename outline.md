# Designing a Cosmos DB solution for an IoT Workload

## Introduction

1. Brief discussion of the sample architecture

    - IoT Edge module
    - IoT Hub
    - Stream Analytics
    - Cosmos DB warm path storage

2. Explanation of how readers can replicate the sample project (likely just a link to a page in this repository)

    - ARM template
    - Deploying IoT Edge solution

## Cosmos DB Specifics

1. Overview of container throughput and *request units*

    - Explanation of how indexing affects a write-heavy workload, like an IoT solution
    - Calculation of RU/s from this IoT solution

2. Overview of Cosmos DB partitions and the importance of choosing a partition key well

## Proposed Replacement

1. Quick overview of the `TemperatureEvents` container

2. Explanation of how an Azure Function App uses change feed notifications to write to Azure SignalR (not part of the solution though)

3. Azure Synapse Analytics

    - HTAP explained
    - Query Comos DB OLTP/OLAP