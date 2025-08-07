# *SCENARIO*

-The Company is Storing all the Billing data in Cosmos DB
-The app reads a lot of old billing records (called read-heavy).
-Each record is large (>300 KB).
*There are millions of records.
*Most old records (older than 3 months) are rarely accessed.
*if someone wants to see them later theyacess this data from DB
*This Creates Load and costs on Azure


# *SOLUTION*


*To reduce costs,
I would move older billing records (3+ months) from Cosmos DB to Blob Storage using an Azure Function,
and update the API to fallback to Blob Storage when data is not found in Cosmos DB. This keeps the system simple, 
cost-effective, and maintains all data access and uptime with no changes to existing API contracts.


