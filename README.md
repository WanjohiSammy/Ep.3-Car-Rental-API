
## Ep.3: CarRental API - Project Structure and Code Setup

Project follows a layered architecture, which is a good practice for building scalable and maintainable applications. Each layer has its specific responsibilities. This structure promotes separation of concerns, making it easier to maintain and test each layer independently. 

### Layers Overview
1.	Api Layer (ASP.NET Core Web API):
-	This layer is the gateway to our system, handling incoming HTTP requests and delivering well-structured responses.
-	Contains controllers, program.cs and appsettings JSON file for our application configurations
-	Project dependencies: Reference Application and Data Layers

2.	Application Layer:
-	Encompasses business rules and logic.
-	Contains components to implement these rules, and profiles for AutoMapper, which helps in mapping DTOs to domain entities and vice versa.
-	Project dependencies: Reference Domain Layer

3.	Data Layer:
-	Manages the interaction with the database.
-	Includes DbContext, Migrations, and Repository implementations.
-	Project dependencies: Reference Domain Layer

4.	Domain Layer:
-	Defines entities that represent the business objects like User and Car entities.
-	Contains repository interfaces, which define the contract for data access.
-	Project dependencies: Utility Layer

5.	Utility Layer:
-	Houses helper methods and internal/external services.
-	Provides utility functions that can be shared across different layers.
-	Project dependencies: Reference Contracts Layer

6.	Contracts Layer:
-	Includes DTOs (Data Transfer Objects), API Requests, API Responses, App Settings Configurations, and validations (using FluentValidation).
-	Defines the communication contracts between API and outside world.
-	Project dependencies: Reference Commons Layer

7.	Commons Layer:
-	Contains constants and enums that are shared across the application.
-	Provides a centralized place for maintaining commonly used elements.
-	No project reference, indicating it's a standalone layer.


## Get Started
1. Clone the repo
```sh
git clone https://github.com/WanjohiSammy/Ep.3-Car-Rental-API.git
```

2. Add `appsettings.Development.json` file in CarRental.Api layer:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=(localdb)\\MSSQLLocalDB;Initial Catalog=CarRentalStore;Integrated Security=True;Connect Timeout=30;Encrypt=True;Trust Server Certificate=False;Application Intent=ReadWrite;Multi Subnet Failover=False"
  }
}
```

3. Build the project to restore packages and ensure it follows the Project Structure.


![Project-Structure-Diagram](https://github.com/WanjohiSammy/Ep.3-Car-Rental-API/assets/12447806/fe5712c4-5016-48d6-8d26-baf8201033f4)

