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

2. Explanation of how an Azure Function App uses change feed notifications to write to Azure SignalR

3. Demo app that shows notifications
    - If an event is logged to the `TemperatureEvents` container, the time shown in the app will be updated and the current temperature shown on the app will be updated
    - [Similar example based on Cosmos DB, but not involving IoT](https://anthonychu.ca/post/cosmosdb-real-time-azure-functions-signalr-service/)