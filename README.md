# Sql2Json
a simple library to convert queries into Json format directly

**If you like it and feel like to donate I would really appreciate it as I am unemployed at the moment due to the pandemic.**

[Buy Me a Coffee or More](https://www.buymeacoffee.com/AsmG)

 
#**SAMPLE USAGE**

** Install-Package Microsoft.Data.SqlClient -Version 2.0.0**
* Note: Create a static variable in startup.cs 
you also need to install SqlDataClient from nuget for the library to work *


 
```csharp
public void ConfigureServices(IServiceCollection services)
        {
            ....

            connectionString = Configuration.GetConnectionString("YourContextName");

            .....
        }
 ```
 
 Then in the controllers
```csharp
public void YourFunction()
        {
           var a = new Sql2Json.Sql2Json();
            
            return  await a.ConvertFromSql2JsonAsync(Startup.connectionString, "SELECT * FROM Players");
            //or
            return  await a.ConvertFromSql2JsonAsync("YourcontextName", "SELECT * FROM Players");
        }
 ```
