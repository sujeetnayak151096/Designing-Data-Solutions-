# Project: Designing Data Solutions for Different Data-Related Challenges

## Table of Contents
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Solutions Implemented](#solutions-implemented)
   - [Azure Dedicated SQL Pool](#azure-dedicated-sql-pool)
   - [Azure Synapse Spark Pool](#azure-synapse-spark-pool)
   - [Azure Cosmos DB with Synapse Link](#azure-cosmos-db-with-synapse-link)
   - [Real-Time Data Processing with Event Hub and Stream Analytics](#real-time-data-processing-with-event-hub-and-stream-analytics)
4. [Conclusion](#conclusion)
5. [Author](#author)

---

## Project Overview <a name="project-overview"></a>
The purpose of this assignment is to understand and design data solutions for various challenges encountered in real-world scenarios. Each solution must address specific requirements based on the characteristics of the problem, such as data streaming, near-real-time processing, and high computing demands.

## Technologies Used <a name="technologies-used"></a>
- **Azure Dedicated SQL Pool**: Data warehousing for structured data
- **Azure Synapse Spark Pool**: Large-scale data processing with Spark
- **Azure Cosmos DB**: NoSQL database for real-time data storage
- **Azure Event Hub and Stream Analytics**:To process real time data

## Solutions Implemented <a name="solutions-implemented"></a>

### Azure Dedicated SQL Pool <a name="azure-dedicated-sql-pool"></a>

    - I began the process by creating a dedicated SQL pool.

    
![image](https://github.com/user-attachments/assets/affbd500-f52e-45aa-a952-55d216c408f9)
      

    - I then stored the data in my Azure Data Lake Storage (ADLS) account. Within my dedicated SQL pool, I created a table named dbo.NYCtaxiTripSmall, where I defined the schema and data types for each column. I 
     utilized Round Robin Distribution and implemented a Clustered Columnstore index to efficiently store the data.
      
![image](https://github.com/user-attachments/assets/a56e70f5-58d2-4859-b5d2-8e18a909d21a)

![image](https://github.com/user-attachments/assets/287d62aa-99d6-434d-a4c2-be3e71dcbc7b)

![image](https://github.com/user-attachments/assets/537a3728-eb7f-4ca4-a893-b5346e19fb7d)

  - We can see our Table Created below.

    ![image](https://github.com/user-attachments/assets/772140ca-27ec-4ad6-bc3b-91745a2c1458)

    ![image](https://github.com/user-attachments/assets/84224bd7-e3f1-4059-bac9-ad92d05a87f7)

    ![image](https://github.com/user-attachments/assets/77a0b801-8ca9-480f-a3f3-7a06408834d8)

  
 1. **Basic Descriptive Statistics:**
   - Calculated basic statistics like average, minimum, maximum, and sum to understand the data distribution.

![image](https://github.com/user-attachments/assets/523ad845-d3cc-4e34-b737-b17f562f6702)

![image](https://github.com/user-attachments/assets/6eea6e9c-18fe-4ccc-9722-b7adec3ae1b6)

2. **Popular Pickup and Drop-off Locations**:
   - Analyze the most common pickup (PULocationID) and drop-off (DOLocationID) locations.

    ![image](https://github.com/user-attachments/assets/b5ea397b-baeb-435f-8252-3ba5ae0258df)
    ![image](https://github.com/user-attachments/assets/f3d3b76d-372f-4b2f-b351-27ff436a60be) ![image](https://github.com/user-attachments/assets/53516a0d-c313-4fbb-adb6-e1a3cbdc57c8)

3. **Payment Method Breakdown:**
   - Understand how passengers pay by analyzing payment_type.
   ![image](https://github.com/user-attachments/assets/d316100f-7aa8-4b72-b81e-23b0356d43be)

   ![image](https://github.com/user-attachments/assets/e6cd7d1c-01f9-4a66-99d7-5df566ae88de)

   - This could help you determine which payment methods are most popular among taxi users.
  
 4. **Distribution of Extra Charges:**
    - Analyze the extra charges like tip_amount, tolls_amount, congestion_surcharge to understand how they impact the total fare.

      ![image](https://github.com/user-attachments/assets/5e6d6a7e-253f-48a4-b60e-e584f5cc5976)

      ![image](https://github.com/user-attachments/assets/3d19e857-8fbd-4232-84d2-87e87b6fa257)

5.  **Ratecode Analysis:**
     - Analyze the RatecodeID to see how different rate codes are used across trips.
  
      ![image](https://github.com/user-attachments/assets/ba4f5515-9173-43ba-a37a-efc01bea436b)
   
      ![image](https://github.com/user-attachments/assets/5a356b8d-4cf2-460f-9e20-a373b1c7ff96)


6. **Vendor Comparison:**
   - Compare different taxi vendors (VendorID) in terms of trip count and total revenue.
     ![image](https://github.com/user-attachments/assets/95ae549e-9b9c-496c-b933-5d02841df025)

     ![image](https://github.com/user-attachments/assets/78d06bfb-0780-472b-84e9-47cbc6d67a06)

   - By utilizing a dedicated SQL pool, I can analyze the data systematically and store my data in a permanent table within the dedicated pool, which is not possible with a serverless SQL pool. The computing power of the dedicated pool enables me to achieve faster query results.
  
     ## Advantages of Dedicated SQL Pool

| Azure Dedicated SQL Pool |
|--------------------------|
| - Optimized for large-scale data warehousing. |
| - Supports complex queries with high performance. |
| - Provides dedicated resources for consistent performance. |
| - Allows for advanced analytics capabilities. |  


### Reading Data on Azure Synapse Spark Pool <a name="azure-synapse-spark-pool"></a>
   
   -  Created an Azure Synapse Spark pool to process large datasets efficiently.

      ![image](https://github.com/user-attachments/assets/295a1aa2-affc-41fc-bdb1-73f4fe9588ff)


1. **Data Storage in ADLS Containerg** 
   •	**Step:** Stored the dataset in an Azure Data Lake Storage (ADLS) container.
   •	**Dataset Used:** Google Play Store data in .csv format

   ![image](https://github.com/user-attachments/assets/ea0b836e-c2bc-41bd-bdbb-8bec99db9c33)


                           ![image](https://github.com/user-attachments/assets/5d7efde3-1943-4c3e-97eb-30b60975cf9e)


                                                                          ![image](https://github.com/user-attachments/assets/09a77798-36e9-4dbd-a5c2-e69dc5298285)

   -  Reading Data on Azure Synapse Spark Pool. Connect to Spark pool and select the Language to Python.
  
                      ![image](https://github.com/user-attachments/assets/3e083dc6-364c-4dfb-b195-a48af823f4fa)


   - Imported Pandas and NumPy library for data Analysis using a Python Notebook and read the data by using a head command.
  
        ![image](https://github.com/user-attachments/assets/c7ec5a36-3afc-4934-a3f8-7119b33de8ed)


        ![image](https://github.com/user-attachments/assets/bd92f03b-2e0f-4c9e-b068-6c2b21af1821)

   - Generating few common commands to know about the datasets.
  
     ![image](https://github.com/user-attachments/assets/ed72c505-2372-4b7f-8752-fa77138c9f20)

     ![image](https://github.com/user-attachments/assets/b6438c96-c796-4392-8654-5755d2bee5bc)

     ![image](https://github.com/user-attachments/assets/dc376b5c-f6ad-4d0a-9a62-13565477ae0f)


2. **Data Cleaning** 
   - Checking for Null Values in the dataset.
  
     ![image](https://github.com/user-attachments/assets/03e8b018-bd2a-4391-91ef-e97d394f3a2f)


     ![image](https://github.com/user-attachments/assets/6fa65698-1673-4172-9d2a-0420963fc266)



3. **Removing Inconsistent Rows:** 
   - Identify and remove rows with string values in the Review column that should be integers.

   ![image](https://github.com/user-attachments/assets/d89ac61d-8b27-46c9-8fce-834a13800f04)


   ![image](https://github.com/user-attachments/assets/495f4a86-4f57-45b0-9451-802ac9833ed7)


   ![image](https://github.com/user-attachments/assets/5ac526af-ad5b-45cb-ac77-379b4ffe7c8c)


  - The Review column contains a row with a string value. Since the goal is to convert the Review column to an integer type, I have decided to remove this specific row from the dataset to ensure consistent data types.

   ![image](https://github.com/user-attachments/assets/eb077a2b-c610-4a27-9e21-c5340dedfd0e)

   ![image](https://github.com/user-attachments/assets/cb59f9d3-0b92-4b46-b311-81f3ab980c2c)

- Converted the Review column to integer type to maintain consistency in the dataset.

   ![image](https://github.com/user-attachments/assets/b0f732e2-541f-4dde-bc8f-4ae314b8068e)


  ![image](https://github.com/user-attachments/assets/7d883907-7239-4a16-9dd0-3e9498695bbb)


  ![image](https://github.com/user-attachments/assets/3dafdfe4-79a9-426c-994d-d3eb79930554)


4. **Standardizing Size Values:**

   - Convert all size values to a uniform format (e.g., converting millions to thousands).
  
     ![image](https://github.com/user-attachments/assets/d6c337ac-8596-4982-a847-e6a1c1b66c1f)


    ![image](https://github.com/user-attachments/assets/4907c9a3-2ec7-4fc9-8c60-451df0b723aa)

  - Checking for Null Values in Size Column .

    ![image](https://github.com/user-attachments/assets/4529a531-c92c-41ff-8a8b-c3da94d697a4)

    ![image](https://github.com/user-attachments/assets/a2b3d3b9-608e-41e1-9975-53b6f0dc6612)

  - We replaced all occurrences of "M" with "000" to represent millions and removed the "k" suffix. Additionally, one row contained the value "Varies with device," which was converted to a NaN value. Finally, we converted the column type from string to float for accurate numerical representation.

5 .**Date Formatting:**

   - Split the Last Updated column into separate Year, Month, and Day columns.

      ![image](https://github.com/user-attachments/assets/6bcfa01a-e059-4f76-959e-db6a14b1ece2)

      ![image](https://github.com/user-attachments/assets/f7893b3b-cf6b-489e-b105-19456215c589)

      ![image](https://github.com/user-attachments/assets/9b0f1b6e-f263-4a36-8b8a-44948974635d)

      ![image](https://github.com/user-attachments/assets/bb95f09f-a4f0-450f-aaef-2efb51cdd668)

  - As seen above, three additional columns—Day, Month, and Year—have been added to the dataset to break down the date information for more granular analysis.

     ![image](https://github.com/user-attachments/assets/0e0282f3-e427-4253-8ccc-0360163c5eb8)

    ![image](https://github.com/user-attachments/assets/c9abbac4-bae0-4cc6-8899-dbb3df6e853b)

  - After performing several data cleaning processes, our dataset is now properly structured. I will proceed to save this cleaned data into my Azure Data Lake Storage (ADLS) account for future use.

    ![image](https://github.com/user-attachments/assets/16c9d573-0741-4091-9cec-3b6af7def5fa)

    ![image](https://github.com/user-attachments/assets/a7eeb627-3a13-4fc4-be40-ac25d7e3fba5)

  - I utilized the to_csv function to store my data by specifying the desired storage location and providing the access key for my Storage Container.

 ## Advantages of using a Spark Pool.

| Azure Synapse Spark Pool |
|--------------------------|
| - High-speed data processing with Spark. |
| - Supports multiple programming languages (Python, SQL, Scala, R). |
| - Enables big data processing on large datasets. |
| - Seamless integration with other Azure services. |  






### Azure Cosmos DB integrating with Synapse link <a name="azure-cosmos-db-with-synapse-link"></a> 
   - I created a Cosmos DB account using a shell script executed in the Azure Cloud Shell environment, streamlining the process within the Azure platform..

       ![image](https://github.com/user-attachments/assets/722663e0-88c9-436d-978b-9a1a423a2a3f)

       ![image](https://github.com/user-attachments/assets/9d75ab31-dfbe-4803-8e19-0794177c8f65)

       ![image](https://github.com/user-attachments/assets/140bf805-dec9-4a26-b211-3b22a945f6ef)

     - We can view all the resources contained within the Cosmos DB Resource Group.

       ![image](https://github.com/user-attachments/assets/9c22fa54-fa93-4ec2-a6c8-421e220f8753)

     - We will navigate to the Data Explorer section in Cosmos DB to enable the Azure Synapse Link.
    
       ![image](https://github.com/user-attachments/assets/5c455a4a-1960-4fa7-bad1-1e60d2f1290f)

     - Next, we will navigate to Azure Synapse to integrate it with Cosmos DB. Specifically, we will create a new linked service that connects to Cosmos DB account.
     - Next, we will navigate to Azure Synapse to integrate it with Cosmos DB. Specifically, we will create a new linked service that connects to Cosmos DB account.
    
         ![image](https://github.com/user-attachments/assets/9a6640d2-8a85-416b-99fe-b4a1217399c8)

     - We can view our linked service in the Data section of Azure Synapse.
    
       ![image](https://github.com/user-attachments/assets/c57b8f52-b60c-47ee-a1a0-f6a903d20709)

      - After integrating the linked service with Cosmos DB, we can now query our data within Azure Synapse. It is now time to load data into Cosmos DB by creating a new container.
    
          ![image](https://github.com/user-attachments/assets/f827ce6a-b843-4bd6-9e53-f5ee41b70074)

     - I created a container named AdventureWorks and uploaded a new dataset into it. To do this, I navigated to the Items section, uploaded the data in JSON format, and clicked on Save Item to save the dataset.
     - Similarly, I uploaded three datasets into the Sales items.
    
       ![image](https://github.com/user-attachments/assets/2271191a-01d1-440c-99f3-4c14e43caf5a)

       ![image](https://github.com/user-attachments/assets/1b5bc944-a652-44c0-ae7d-89cafc5bc74f)

    - We can see the three datasets in our Sales items. Now, we can query our data in Azure Synapse.
    - To do this, we navigate to our linked services in Azure Synapse. When we hover over Sales, we have the option to query our data using either SQL or a Notebook. I chose to use a Notebook, loaded the data into a DataFrame, and queried it using a Spark pool.

     ![image](https://github.com/user-attachments/assets/718d53e7-02eb-4fb8-970a-f07acd39ce30)

     ![image](https://github.com/user-attachments/assets/77e3c9c7-d884-4b5a-a929-182699f60ebb)

     ![image](https://github.com/user-attachments/assets/ccd9547f-e814-4884-9e62-329396061309)

  - The results include three records, with one corresponding to each item we added to the Cosmos DB database. Each record contains the fields we specified during item creation, along with several automatically generated metadata fields.

    ![image](https://github.com/user-attachments/assets/945ec06b-d2fd-401a-84cc-79bec018eaf0)

- This query created a new dataframe containing only the customerid and customerdetails columns.  We can Observe that the customerdetails column contains the JSON structure for the nested data in the source item.

    ![image](https://github.com/user-attachments/assets/c9d1d3fd-97cb-4ad7-9456-62907afe4381)

   ![image](https://github.com/user-attachments/assets/dcb25692-ebad-4e8c-9552-d4e2f4e34f18)

  - Above Query include the customername and customeremail from the customerdetails value as columns.
 
    ![image](https://github.com/user-attachments/assets/a9f47107-a1eb-46a2-a813-8ef0420e5180)

  - Our objective now is to add data to our existing datasets in Cosmos DB and execute a query in the Serverless SQL Pool to verify if the data has been updated and if the additional data appears in the query results.
 
    ![image](https://github.com/user-attachments/assets/f57ca2ac-5a53-490b-a343-7d21369e7223)

  - As we can see, our new data has been added to Sales.Items. Now, we need to query this dataset using Azure Synapse's Serverless SQL Pool to determine whether the additional column has been successfully included.
 
    ![image](https://github.com/user-attachments/assets/6348afae-9e18-4f70-9c0d-189a9b5df3c9)

    ![image](https://github.com/user-attachments/assets/ef6d14b2-0bbd-4ed7-85cf-5a50a2a1852f)

 - The SQL query returns an output with four columns, including the column names defined in the query. This practical exercise demonstrates that Cosmos DB can be utilized to query near real-time data effectively.


 ## Advantages of using a Cosmos DB .

| Azure Cosmos DB          |
|--------------------------|
| - Global distribution and multi-model capabilities. |
| - Supports real-time data processing. |
| - Automatic indexing for fast queries. |
| - High availability with SLA guarantees. |  


### Processing Real-Time Data Using Azure Event Hub and Storing It in Azure Synapse via Stream Analytics <a name="real-time-data-processing-with-event-hub-and-stream-analytics"></a>
**Steps:**
•	Create an Azure Event Hub Namespace and Event Hub Instance.
•	Create a Stream Analytics Job to Query the Data.
•	Create Input and Output Connections.
•	Create a Synapse Workspace and Create a Table
•	Send Real-Time Data from Event Hub
•	Query the Data Using Stream Analytics and Start the Job
•	Verify Data in Azure Synapse Analytics

- Begin by creating an Event Hub Namespace, which acts as a container for Event Hubs. Inside the namespace, create an Event Hub instance to act as the entry point for real-time data streams

    ![image](https://github.com/user-attachments/assets/f80d11f6-f614-403a-9374-8395c349db03)

    ![image](https://github.com/user-attachments/assets/e9e1737e-b0f9-4c20-b2c7-9b8bb113476f)

-  A Stream Analytics Job is needed to process real-time data received from Event Hub. Navigate to Stream Analytics Jobs in Azure and create a new job.
-  The job will take input from Event Hub and send the processed data to Azure Synapse.

  ![image](https://github.com/user-attachments/assets/d10fdf3c-2005-4b39-95fa-535084c61877)

- After creating the job, define the input from Azure Event Hub. This will ensure that the job receives real-time data streams. Next, define the output destination as Azure Synapse Analytics. This step ensures that the processed data is sent to the Synapse table

  ![image](https://github.com/user-attachments/assets/de4060c1-f689-4111-b32c-ea073f929340)     ![image](https://github.com/user-attachments/assets/19eb9810-47a3-4463-9c6c-d6c1fe7509ef)


- Now, send the real-time data to Event Hub. For this project, we are using a vehicle toll booth dataset from Azure Data Explorer.

  ![image](https://github.com/user-attachments/assets/ec0452f4-e45f-45c5-aa51-81d068e5f4ce)

-  As the dataset contains numerous columns, the next step is to write a query in Stream Analytics to filter and clean the data.
-  After writing the query, run a Test Query to validate if the output meets the desired format. You can view the test results to confirm the expected data structure.

  ![image](https://github.com/user-attachments/assets/968d2918-2e9b-4551-9de8-ef965c609fc2)


  ![image](https://github.com/user-attachments/assets/10b68c5d-9cce-43e8-b594-29bb31c629af)


  ![image](https://github.com/user-attachments/assets/c1bce6d0-527e-43f4-afef-035943bdfb86)


  ![image](https://github.com/user-attachments/assets/e4324b6b-6dbf-4d0e-b5d1-d85ac27daadf)

  - In order to store the processed data, create a table in Azure Synapse Analytics with the required schema and data types. In this case, the table is named "VehicleTollBooth."

     ![image](https://github.com/user-attachments/assets/f11539c2-95b2-4b63-a560-fbeae34c0ccd)

    ![image](https://github.com/user-attachments/assets/cff35dc3-31e1-475e-9be4-e5f19f59399c)


  - Once the query is validated, start the Stream Analytics job. The job will now process the incoming data from Event Hub, clean it using the query, and store it in the Synapse table.

     ![image](https://github.com/user-attachments/assets/77f47fb7-3fda-46b4-80ce-24037bb82ffd)

  - Before we Start the Job we can see there is 0 records inside our table.

     ![image](https://github.com/user-attachments/assets/37eeef28-062a-4e9c-8791-bbfcec77bee5)

  - Before starting the job, the Synapse table should be empty. After the job starts, the processed data will flow into the table.
  - Upon completion, verify the data in the Synapse table to ensure the records are correctly inserted.

       ![image](https://github.com/user-attachments/assets/7b7f3371-64a1-45f9-a4db-b121076076bb)

      ![image](https://github.com/user-attachments/assets/7ba0a440-9bab-4759-9565-2e0dbc540953)


     # Advantages of Event Hub and Stream Analytics

| Features                | Azure Event Hub                                                                 | Azure Stream Analytics                                                                                  |
|-------------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Real-Time Data Ingestion** | Enables large-scale real-time data ingestion from multiple sources.                    | Processes data in real time, allowing for instant actions based on live data streams.                   |
| **Scalability**          | Handles millions of events per second, highly scalable.                                 | Automatically scales based on data stream size.                                                         |
| **Integration**          | Seamlessly integrates with Azure services like Stream Analytics, Synapse, and Data Lake. | Integrates well with Event Hub and can output data to Synapse, SQL DB, Data Lake, etc.                  |




## Conclusion <a name="conclusion"></a>
This project successfully demonstrated various data solution designs and techniques for addressing real-world challenges involving data streaming, large-scale processing, and data warehousing. Each Azure service provided unique capabilities to meet specific requirements:
1.	**Azure Synapse Spark Pool** facilitated efficient processing of large datasets, highlighting the power of distributed computing and Python-based data manipulation.
2.	**Azure Cosmos DB** demonstrated seamless integration with Azure Synapse using Synapse Link, enabling near real-time querying and data analysis for NoSQL databases.
3.	**Azure Dedicated SQL Pool** showcased its strengths in handling structured data warehousing tasks with optimized query performance, making it ideal for large-scale, high-performance analytical workloads.
4.	** Event Hub and Azure Stream Analytics** provided robust solutions for real-time data ingestion and processing, which were effectively integrated with Azure Synapse to store and analyze real-time data.

Through this project, I gained deeper insights into how different Azure components can be leveraged for building scalable, reliable, and efficient data solutions. The combination of services such as Synapse Spark Pools, Cosmos DB, Dedicated SQL Pools, Event Hub, and Stream Analytics allows organizations to meet various data challenges from batch processing to real-time analytics. These solutions ensure data is processed, stored, and analyzed efficiently, enabling businesses to make data-driven decisions in real time.



## Author <a name="author"></a>
**Sujeet Nayak** 
**Role**: Data Engineering
