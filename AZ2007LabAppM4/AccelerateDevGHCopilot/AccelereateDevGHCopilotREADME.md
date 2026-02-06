# AccelerateDevGHCopilot - Library Management System

## Project Purpose

The AccelerateDevGHCopilot project is a comprehensive library management system designed to demonstrate modern .NET development practices and GitHub Copilot's capabilities in accelerated development. This application serves as a learning platform for exploring clean architecture, dependency injection, unit testing, and automated code generation techniques.

## Project Overview

This library management system implements core library operations including:
- **Patron Management**: Member registration, membership renewal, and patron information tracking
- **Book Inventory**: Managing books, authors, and book items
- **Loan Operations**: Checking out books, returning loans, and tracking loan history
- **Data Persistence**: JSON-based data storage with repository pattern implementation

## Architecture & Design

The project follows **Clean Architecture** principles with clear separation of concerns:

### Project Structure

```
AccelerateDevGHCopilot/
├── src/
│   ├── Library.ApplicationCore/     # Domain layer
│   ├── Library.Infrastructure/      # Data access layer
│   └── Library.Console/            # Presentation layer
└── tests/
    └── UnitTests/                  # Test suite
```

### Core Components

#### **Library.ApplicationCore** (Domain Layer)
- **Entities/**: Domain models representing core business objects
  - `Author.cs` - Book author information
  - `Book.cs` - Book catalog entries
  - `BookItem.cs` - Individual book copies
  - `Loan.cs` - Loan transaction records
  - `Patron.cs` - Library member information

- **Enums/**: Business logic enumerations
  - `LoanExtensionStatus.cs` - Loan extension results
  - `LoanReturnStatus.cs` - Return operation outcomes
  - `MembershipRenewalStatus.cs` - Membership renewal states

- **Interfaces/**: Repository and service contracts
  - `ILoanRepository.cs` - Loan data access contract
  - `ILoanService.cs` - Loan business logic contract
  - `IPatronRepository.cs` - Patron data access contract
  - `IPatronService.cs` - Patron business logic contract

- **Services/**: Business logic implementation
  - `LoanService.cs` - Loan operations and validation
  - `PatronService.cs` - Patron membership and renewal logic

#### **Library.Infrastructure** (Data Access Layer)
- **Data/**: Repository pattern implementations
  - `JsonData.cs` - JSON data loading and caching
  - `JsonLoanRepository.cs` - Loan data persistence
  - `JsonPatronRepository.cs` - Patron data persistence

#### **Library.Console** (Presentation Layer)
- **Application Files**:
  - `Program.cs` - Application entry point and DI configuration
  - `ConsoleApp.cs` - Main application logic
  - `ConsoleState.cs` - Application state management
  - `CommonActions.cs` - Reusable UI actions
  - `appSettings.json` - Configuration settings

- **Json/**: Data storage files
  - `Authors.json` - Author catalog
  - `Books.json` - Book catalog
  - `BookItems.json` - Physical book inventory
  - `Loans.json` - Loan transaction history
  - `Patrons.json` - Member database

## Key Functionality

### 🏛️ Patron Management
- **Membership Renewal**: Automated validation of renewal eligibility
  - Prevents early renewal (1+ month remaining)
  - Blocks renewal for patrons with overdue loans
  - Extends membership by 1 year upon successful renewal

### 📚 Loan Operations
- **Loan Processing**: Complete loan lifecycle management
  - Book checkout validation
  - Return processing with status tracking
  - Overdue loan detection
  - Loan extension capabilities

### 📊 Data Management
- **JSON-Based Storage**: Lightweight data persistence
  - Relational data modeling in JSON format
  - Lazy loading and caching mechanisms
  - Cross-reference population for entity relationships

### 🔧 Dependency Injection
- **Service Container**: Microsoft.Extensions.DependencyInjection
  - Repository pattern registration
  - Service layer abstraction
  - Configuration management integration

## Unit Testing Strategy

The project includes comprehensive unit tests organized by architectural layers:

### Test Structure
```
tests/UnitTests/
├── ApplicationCore/
│   ├── LoanService/              # Business logic tests
│   └── PatronService/            # Service layer tests
├── Infrastructure/
│   └── JsonLoanRepository/       # Data access tests
├── LoanFactory.cs                # Test data factory
├── PatronFactory.cs             # Test data factory
└── UnitTests.csproj             # Test project configuration
```

### Testing Frameworks
- **xUnit**: Primary testing framework
- **NSubstitute**: Mocking framework for dependencies
- **Microsoft.Extensions.Configuration**: Configuration testing

### Test Categories

#### **Service Layer Tests**
- **LoanService Tests**:
  - Return loan validation
  - Loan status management
  - Business rule enforcement
  
- **PatronService Tests**:
  - Membership renewal eligibility
  - Overdue loan validation
  - Patron status management

#### **Repository Layer Tests**
- **JsonLoanRepository Tests**:
  - Data retrieval operations
  - Entity relationship population
  - Error handling scenarios

#### **Test Data Management**
- **Factory Pattern**: Consistent test data creation
  - `LoanFactory.cs` - Loan entity builders
  - `PatronFactory.cs` - Patron entity builders

### Example Test Implementation

```csharp
[Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when ID exists")]
public async Task GetLoan_ReturnsLoanWhenIdExists()
{
    // Arrange
    var expectedLoanId = 1;
    
    // Act
    var actualLoan = await _jsonLoanRepository.GetLoan(expectedLoanId);
    
    // Assert
    Assert.NotNull(actualLoan);
    Assert.Equal(expectedLoanId, actualLoan.Id);
    Assert.NotNull(actualLoan.BookItem);
    Assert.NotNull(actualLoan.Patron);
}
```

## Getting Started

### Prerequisites
- .NET 9.0 SDK or later
- Visual Studio 2022 or Visual Studio Code
- Git for version control

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd AccelerateDevGHCopilot
   ```

2. **Restore dependencies**:
   ```bash
   dotnet restore
   ```

3. **Build the solution**:
   ```bash
   dotnet build
   ```

### Running the Application

#### Console Application
```bash
dotnet run --project src/Library.Console/Library.Console.csproj
```

#### Unit Tests
```bash
# Run all tests
dotnet test tests/UnitTests/UnitTests.csproj

# Run tests with detailed output
dotnet test tests/UnitTests/UnitTests.csproj --verbosity normal

# Run specific test category
dotnet test tests/UnitTests/UnitTests.csproj --filter "DisplayName~LoanService"
```

### Configuration

The application uses `appSettings.json` for configuration:

```json
{
  "JsonPaths": {
    "Authors": "Json/Authors.json",
    "Books": "Json/Books.json",
    "BookItems": "Json/BookItems.json",
    "Loans": "Json/Loans.json",
    "Patrons": "Json/Patrons.json"
  }
}
```

## Development Workflow

### GitHub Copilot Integration
This project demonstrates effective GitHub Copilot usage patterns:
- **Code Generation**: Service and repository implementations
- **Test Creation**: Comprehensive unit test coverage
- **Documentation**: Inline comments and README generation
- **Refactoring**: Code improvement suggestions

### Best Practices Demonstrated
- ✅ Clean Architecture separation
- ✅ Dependency injection patterns
- ✅ Repository pattern implementation
- ✅ Comprehensive unit testing
- ✅ Factory pattern for test data
- ✅ Async/await programming model
- ✅ SOLID principles adherence

## Contributing

1. Follow the established architecture patterns
2. Maintain comprehensive test coverage
3. Use meaningful commit messages
4. Leverage GitHub Copilot for code generation
5. Update documentation for new features

## Technology Stack

- **.NET 9.0**: Core framework
- **C# 11**: Programming language
- **Microsoft.Extensions.DependencyInjection**: IoC container
- **Microsoft.Extensions.Configuration**: Configuration management
- **xUnit**: Unit testing framework
- **NSubstitute**: Mocking framework
- **JSON**: Data persistence format

## Project Outcomes

This project demonstrates:
- **Accelerated Development**: GitHub Copilot-assisted coding
- **Clean Code Practices**: Maintainable and testable architecture
- **Modern .NET Patterns**: Current development methodologies
- **Comprehensive Testing**: Robust quality assurance practices

---

*This project serves as a practical example of modern .NET development with GitHub Copilot integration, showcasing automated development workflows and best practices.*