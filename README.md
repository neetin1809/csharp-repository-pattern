# Repository Pattern in c# and Entity Framework
This is an example of Repository Pattern using _Entity Framework_

Specail Type of Facade Pattern.

In Entity Framework in MVC, controllers are directly interacting with the Entity Framework data context class and execute the queries to retrieve the data from the database. They also perform the INSERT, UPDATE, and DELETE operations using the data context and DbSet. The Entity Framework in turn talks with the underlying SQL Server database.

# Drawback
If two controller modify the same table, the information will be duplicated. Future Modification will be needed at two places

File structure (the most relevant):
* models
* repositories
    * IRepository
    * IMyRepository
    * Repository
    * MyRepository
* MyContext.cs
* MyContextFactory.cs
* UnitOfWork.cs

## Run

### Step 1
To run this example, you must have a database (remember to adapt the connection 
string from the file _global.json_) and a table with the follow structure:

```sql
create table treatment
(
    treatmentid int identity primary key,
    treatmenttext varchar(100),
    -- description of the treatment
    price int,
)
```

### Step 2
Intstall dependencies:
```bash
dotnet restore
```

### Step 3
Compile and run _(from the root path of the project)_:
```bash
dotnet run
```
