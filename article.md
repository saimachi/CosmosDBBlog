# Designing a Cosmos DB solution for an IoT Workload

## Introduction

In this blog post, you will learn more about the considerations of planning a Cosmos DB deployment for an IoT solution. In this sample, an IoT Edge module running on a Linux VM will send simulated environmental data to Azure IoT Hub. The IoT Edge runtime on the VM runs containerized modules. In this post, a sample module will be used, but in a business deployment, module images are pulled from a container registry like Azure Container Registry. From there, Azure Stream Analytics will read data from IoT Hub using a *consumer group*. Stream Analytics will then write device data to Azure Cosmos DB using the *SQL API*. From there, a Power BI dashboard will be used for real-time visualization of device data.

### Implement the Solution

If you would like to follow the examples given in this post, refer to the instructions [here.]() The document will run through the process of creating a resource group, IoT Hub, and Cosmos DB account.

## Cosmos DB Specifics

Now that an IoT Edge module is transmitting data (potentially acting as an edge device transmitting data from multiple connected sensors), and the solution incorporates Stream Analytics to write the data to Cosmos DB, the solution must be designed to effectively take advantage of Cosmos DB's featureset. The features most critical to our scenario include:

    - Predictable performance
    - High availability

With these considerations in mind, we must review the Cosmos DB features that enable us to meet these objectives.

### Provisioned Throughput

Azure Cosmos DB uses *request units* to abstract database throughput on a relative scale. Technically, a single request unit is defined as the cost of fetching a 1 KB document by its document **id** and partition key (this process is also known as a *point read*). Do not worry if these concepts sound difficult; our goal is to understand them using a real-world IoT solution. Those familiar with Cosmos DB also know that it supports multiple APIs; however, irrespective of the API choice, database or container throughput is measured in RU/s. This measure simply means the number of request units consumed by all the entity's clients in a one second period. Let's explore what this means in practice.

Here's a sample document writen by the IoT Edge module to a Cosmos DB container:

```json
```

