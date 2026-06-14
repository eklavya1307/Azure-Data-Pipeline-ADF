# Azure Cloud Fundamentals and Data Pipeline Implementation using Azure Data Factory

## Project Overview

This project was completed as part of the **Celebal Technologies Internship – Week 4 Assignment**. The objective of the project was to understand Microsoft Azure cloud services and implement an end-to-end data pipeline using **Azure Blob Storage** and **Azure Data Factory (ADF)**.

The project demonstrates how data can be stored in Azure Blob Storage, validated using metadata checks, and copied from a source location to a destination location through a pipeline created in Azure Data Factory.

---

## Objective

The main objective of this project was to:

* Understand Azure cloud fundamentals.
* Create and manage Azure resources.
* Configure Azure Blob Storage for data storage.
* Create and configure Azure Data Factory.
* Establish connectivity using Linked Services.
* Create source and destination datasets.
* Retrieve file metadata using Get Metadata activity.
* Copy data using Copy Data activity.
* Monitor pipeline execution.
* Configure IAM roles for secure access.
* Implement a complete end-to-end data pipeline.

---

## Technologies and Services Used

* Microsoft Azure Portal
* Azure Resource Group
* Azure Storage Account
* Azure Blob Storage
* Azure Data Factory (ADF)
* Azure Identity and Access Management (IAM)
* CSV Dataset (Sample-Superstore.csv)

---

## Project Architecture

```text
Sample-Superstore.csv
          │
          ▼
 Azure Blob Storage
   (source-container)
          │
          ▼
   Get Metadata Activity
          │
          ▼
     Copy Data Activity
          │
          ▼
 Azure Blob Storage
(destination-container)
          │
          ▼
       output.csv
```

---

## Implementation Steps

### 1. Resource Group Creation

A Resource Group named **RG-Celebal-Week4** was created to manage all Azure resources associated with the project.

### 2. Storage Account Setup

A Storage Account named **eklavyaadfstorage2026** was created. Two Blob Containers were configured:

* source-container
* destination-container

### 3. Dataset Upload

The **Sample-Superstore.csv** file was uploaded into the source-container and used as the source dataset for the pipeline.

### 4. Azure Data Factory Creation

An Azure Data Factory instance named **ADF-Eklavya-Week4** was created for designing and executing the pipeline.

### 5. Linked Service Configuration

A Linked Service named **LS_Eklavya_Storage** was created to establish connectivity between Azure Data Factory and Azure Blob Storage.

### 6. Dataset Configuration

Two datasets were created:

#### Source Dataset

* DS_Superstore_Source
* Container: source-container

#### Destination Dataset

* DS_Superstore_Destination
* Container: destination-container

### 7. Metadata Validation

The Get Metadata activity was configured to retrieve:

* File Existence
* File Size
* Last Modified Date

This step ensured that the source file was available before initiating the copy process.

### 8. Pipeline Development

A pipeline named **PL_Eklavya_Superstore_Copy** was created.

Pipeline Activities:

1. Get Metadata Activity
2. Copy Data Activity

The pipeline validates the source file and then copies it to the destination container.

### 9. Pipeline Execution

The pipeline was executed using the Debug option available in Azure Data Factory.

Execution Status:

✅ Succeeded

### 10. Output Verification

After successful execution, the file **output.csv** was generated in the destination-container.

### 11. IAM Role Assignment

The following IAM roles were assigned:

* Reader
* Storage Blob Data Contributor

These permissions ensured secure access to Azure resources and storage services.

---

## Project Structure

```text
Azure-Data-Pipeline-ADF
│
├── Report
│   └── Week4_Report.pdf
│
├── Screenshots
│   ├── 01_Resource_Group_Created.png
│   ├── 02_Storage_Account_Created.png
│   ├── 03_Blob_Containers_Created.png
│   ├── 04_Source_Container_CSV_Uploaded.png
│   ├── 05_ADF_Created.png
│   ├── 06_ADF_Home_Page.png
│   ├── 07_Linked_Service_Creation.png
│   ├── 08_Linked_Service_Created.png
│   ├── 09_Source_Dataset.png
│   ├── 10_Destination_Dataset.png
│   ├── 11_Get_Metadata_Activity.png
│   ├── 12_Pipeline_Design_GetMetadata_CopyData.png
│   ├── 13_Pipeline_Validation_Success.png
│   ├── 14_Pipeline_Debug_Run_Success.png
│   ├── 15_Debug_Execution_Success.png
│   ├── 16_Destination_Container_Output_File.png
│   └── 17_IAM_Role_Assignments.png
│
├── Dataset
│   └── Sample-Superstore.csv
│
└── README.md
```

---

## Results

The project successfully demonstrated the implementation of an end-to-end Azure data pipeline. The source CSV file was validated using the Get Metadata activity and copied successfully to the destination container using the Copy Data activity.

Key achievements:

* Successfully configured Azure Storage Account and Blob Containers.
* Successfully established connectivity using Linked Services.
* Successfully created source and destination datasets.
* Successfully validated file metadata.
* Successfully copied data using Azure Data Factory.
* Successfully monitored pipeline execution.
* Successfully generated output file in destination container.
* Successfully configured IAM roles.

---

## Conclusion

This project provided practical experience with Azure cloud services and data engineering concepts. Through the implementation of Azure Blob Storage and Azure Data Factory, an end-to-end data pipeline was successfully created, executed, and monitored.

The project enhanced understanding of cloud resource management, storage services, linked services, datasets, metadata validation, data movement operations, access control mechanisms, and pipeline orchestration in Microsoft Azure.

