# Workspace Utilization API

A lightweight **.NET 8 Web API** for tracking meeting room utilization. This project demonstrates clean architecture, Entity Framework Core usage with SQL Server (and an in-memory database for tests), structured logging, and xUnit tests with a shared test helper.

## Features

- **Utilization Tracking:** Retrieve total booked hours per room within a specified date range
- **Data Persistence:** Uses a SQL Server database for persistence, with LocalDB as the default
- **Validation:** Includes built-in validation for invalid date ranges
- **Structured Logging:** Implements structured logging using `ILogger`
- **Testing:** Comprehensive unit tests with xUnit and Moq
- **Test Helper:** A shared test helper is included for creating clean, isolated tests
- **API Exploration:** The Swagger UI is available for easy API exploration and testing

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/workspace-utilization.git
cd workspace-utilization
```

### 2. Run the API

```bash
cd WorkspaceUtilization.Api
dotnet run
```

The API will be available at `https://localhost:5001` or `http://localhost:5000`. The Swagger UI can be accessed at `https://localhost:5001/swagger`.

### 3. Example API Usage

**Get utilization between two dates**

```http
GET /api/utilization?startDate=2025-08-01T00:00:00&endDate=2025-08-31T23:59:59
```

**Example Response**

```json
[
  { "roomId": 101, "totalBookedHours": 2 },
  { "roomId": 102, "totalBookedHours": 1 }
]
```

## Running Tests

Navigate to the test project and run the following command:

```bash
cd WorkspaceUtilization.Tests
dotnet test
```

## Project Structure

```
WorkspaceUtilization.Api/      → Main Web API project
 ├── Controllers/              → API controllers
 ├── Models/                   → Domain models (Booking)
 ├── Data/                     → EF Core DbContext
 ├── Program.cs                → App startup

WorkspaceUtilization.Tests/    → Unit test project
 ├── Helpers/                  → TestDbContextFactory for seeding
 ├── UtilizationControllerTests.cs
```

## Technologies Used

- .NET 8
- ASP.NET Core Web API
- Entity Framework Core (SQL Server + InMemory for tests)
- xUnit (Unit Testing)
- Moq (Mocking)
- Microsoft.Extensions.Logging
- Swagger / OpenAPI

## Next Steps

- Add authentication and authorization
- Add integration tests
- Deploy to Azure or AWS
- Extend utilization to user-level and building-level metrics

## License

This project is licensed under the MIT License. Feel free to use and modify it.
