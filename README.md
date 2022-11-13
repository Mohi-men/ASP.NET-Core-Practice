# ASP.NET-Core-Practice


1. ***Create a ASP.NET Web API project***
2. Create Two Folder. Namely- **Data** & **Models**. Download ["Microsoft.EntityFraeworkCore.InMemory(for inmemory database)", "Microsoft.EntityFraeworkCore.SqlServer", "Microsoft.EntityFraeworkCore.Tools"]
3. Create a DbContext Class & Inherit DbContext Class(Create constructor with Paramete DBContextOptions). 
4. Inside the DbContext Class. Create a property for Model that you have (e.g. DbSet<student> Students).
5. Dependency Injection-> Go to program.cs class and add DbContext (AddDbContext<your_dbcontext>(options => options.UseInMemoryDatabase("name_of_the_database")))
6. Add a MVC empty controller and Annotate it with [ApiController],[Route("api/[controller]")]

For database - SqlServer
1. appsettings.json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionStrings": {
    "TestConnectionStrings": "Server=server_name; Database=databse_name; Trusted_Connection= true"
  }
}
2. Go to program.cs class and add DbContext (AddDbContext<your_dbcontext>(options => options.UseSqlServer(builder.Configuration.GetConnectionString("TestConnectionStrings"))))

3. Open Tools -> Package Manager
4. Add-migration "Initial"
5. Update-Database
