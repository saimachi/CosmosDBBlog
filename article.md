# Designing a Cosmos DB solution for an IoT Workload

## Introduction

In this blog post, you will learn more about the considerations of planning a Cosmos DB deployment for an IoT solution. In this sample, an IoT Edge module running on a Linux VM will send simulated environmental data to Azure IoT Hub. The IoT Edge runtime on the VM runs containerized modules. In this post, a sample module will be used, but in a business deployment, module images are pulled from a container registry like Azure Container Registry. From there, Azure Stream Analytics will read data from IoT Hub using a *consumer group*. Stream Analytics will then write device data to Azure Cosmos DB using the *SQL API*. From there, a Power BI dashboard will be used for real-time visualization of device data.

### Implement the Solution

If you would like to follow the examples given in this post, refer to the instructions [here.]() The document will run through the process of creating a resource group, IoT Hub, and Cosmos DB account.