# Shipping Management System - Programming 3 Assignment

## 📋 Project Information

**University:** ORT Uruguay  
**Faculty:** Engineering  
**School:** Technology  
**Course:** Programming 3  
**Program:** Programming Analyst / Information Technology Analyst  
**Group:** M3C  
**Instructor:** Joaquín Rodríguez

### 👥 Team Members
- **Sebastián Hohl** - 327007
- **Matías Oreiro** - 239479

**Submission Date:** June 26, 2025

---

## 📝 Project Description

Comprehensive shipping management system developed with multi-layered architecture in .NET 8.0. The project implements a complete system for parcel shipping administration, including user management, employee management, shipment tracking, and comments.

The system consists of three main components:
1. **RESTful Web API** - Backend with layered architecture
2. **MVC Web Application** - Administration and management interface for staff
3. **HTTP Client** - Public interface for customers

---

## 🏗️ System Architecture

### Main Components

#### 1. **Obligatorio.WebApi**
RESTful API that exposes endpoints for all system operations.

**Technologies:**
- ASP.NET Core 8.0
- Entity Framework Core
- SQL Server
- JWT Authentication

#### 2. **Obligatorio.MVC**
Web application with MVC pattern for administrative management.

**Features:**
- Administrator and staff login
- Employee CRUD operations
- Shipment management
- Tracking visualization
- Comment system

#### 3. **ClienteHTTPObligatorio**
Web client that consumes the API for public functionalities.

**Features:**
- Create and finalize shipments
- Add comments
- Query shipments by tracking number
- Search own shipments
- Date range and keyword search
- Password change

### Architecture Layers

```
┌─────────────────────────────────┐
│   Presentation (MVC/HTTP)       │
├─────────────────────────────────┤
│   WebApi (Controllers)          │
├─────────────────────────────────┤
│   Application Logic             │
├─────────────────────────────────┤
│   Business Logic (Domain)       │
├─────────────────────────────────┤
│   Data Access (EF Core)         │
├─────────────────────────────────┤
│   Database (SQL Server)         │
└─────────────────────────────────┘
```

**Projects:**
- `Obligatorio.WebApi` - REST services layer
- `Obligatorio.MVC` - Web presentation layer
- `Obligatorio.LogicaAplicacion` - Use cases and coordination
- `Obligatorio.LogicaNegocio` - Domain entities and business rules
- `Obligatorio.LogicaAccesoDatos` - Repositories and EF context
- `Obligatorio.DTOs` - Data transfer objects
- `Obligatorio.Utilidades` - Common helpers and utilities

---

## 👤 Roles and Use Cases

### Administrator
- ✅ Login/Logout
- ✅ Create employees
- ✅ Edit employees
- ✅ Delete employees
- ✅ List employees
- ✅ Create shipments
- ✅ Finalize shipments
- ✅ Add comments
- ✅ View comments
- ✅ Get shipment details
- ✅ Change password
- ✅ Get shipment by tracking number
- ✅ Get own shipments
- ✅ Get shipments between dates
- ✅ Search shipments by keyword

### Staff Member
- ✅ Login/Logout
- ✅ Delete employees
- ✅ List employees
- ✅ Create shipments
- ✅ Finalize shipments
- ✅ Add comments
- ✅ View comments
- ✅ Get shipment details
- ✅ Change password
- ✅ Get shipment by tracking number
- ✅ Get own shipments
- ✅ Get shipments between dates
- ✅ Search shipments by keyword

### Customer (Public)
- ✅ Create shipments
- ✅ Finalize shipments
- ✅ Add comments
- ✅ View comments
- ✅ Get shipment details
- ✅ Change password
- ✅ Get shipment by tracking number
- ✅ Get own shipments
- ✅ Get shipments between dates
- ✅ Search shipments by keyword

---

## 🗄️ Database

### Connection Information (Azure)

**Database:** ObligatorioP3  
**Server:** obligatoriop3oreirohohl.database.windows.net  
**Port:** 1433  
**SQL User:** SfCGQFPV

**Connection String:**
```
Server=tcp:obligatoriop3oreirohohl.database.windows.net,1433;
Initial Catalog=ObligatorioP3;
Persist Security Info=False;
MultipleActiveResultSets=False;
Encrypt=True;
TrustServerCertificate=False;
Connection Timeout=30;
```

### Available SQL Scripts
- `ObligatorioDatabase.sql` - Script for local database
- `ObligatorioDatabaseAzure.sql` - Script for Azure SQL Database

---

## 🚀 Azure Deployment

### Production URLs

**Web API:**
```
https://webapiobligatoriop3oreirohohld6c6e0g6g0fedbgd.brazilsouth-01.azurewebsites.net/
```

**MVC Web Application:**
```
https://webappobligatoriop3-cghkfrgsg3a0cyex.brazilsouth-01.azurewebsites.net/
```

**HTTP Client:**
```
https://clientehttpobligatoriop3oreirohohlesd0hrf3c9dafnfr.brazilsouth-01.azurewebsites.net/
```

---

## 📚 API Documentation

### Postman Collections

**Azure Deployment:**
```
https://documenter.getpostman.com/view/42495957/2sB2xEAo4v
```

**Local Deployment:**
```
https://documenter.getpostman.com/view/42495957/2sB2xEAo4x
```

---

## 💻 Local Installation and Configuration

### Prerequisites

- .NET 8.0 SDK or higher
- SQL Server 2019 or higher (or SQL Server Express)
- Visual Studio 2022 or Visual Studio Code
- Git

### Installation Steps

#### 1. Clone the Repository
```bash
git clone [REPOSITORY_URL]
cd Obligatorio
```

#### 2. Configure Database

**Option A: Local SQL Server**
```bash
# Execute the script in SQL Server Management Studio
sqlcmd -S localhost -i ObligatorioDatabase.sql
```

**Option B: Azure SQL Database**
```bash
sqlcmd -S obligatoriop3oreirohohl.database.windows.net -U SfCGQFPV -i ObligatorioDatabaseAzure.sql
```

#### 3. Configure Connection Strings

**For Obligatorio.WebApi:**

Edit `Obligatorio.MVC/Obligatorio.WebApi/appsettings.json`:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=ObligatorioP3;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True"
  }
}
```

**For Obligatorio.MVC:**

Edit `Obligatorio.MVC/Obligatorio.MVC/appsettings.json`:
```json
{
  "ApiSettings": {
    "BaseUrl": "https://localhost:7001/api"
  }
}
```

**For ClienteHTTPObligatorio:**

Edit `ClienteHTTPObligatorio/ClienteHTTPObligatorio/appsettings.json`:
```json
{
  "ApiSettings": {
    "BaseUrl": "https://localhost:7001/api"
  }
}
```

#### 4. Restore Dependencies

```bash
# For the main project (MVC + API)
cd "Obligatorio.MVC"
dotnet restore

# For the HTTP client
cd "../ClienteHTTPObligatorio"
dotnet restore
```

#### 5. Run the Applications

**Terminal 1 - Web API:**
```bash
cd "Obligatorio.MVC/Obligatorio.WebApi"
dotnet run
```

**Terminal 2 - MVC Application:**
```bash
cd "Obligatorio.MVC/Obligatorio.MVC"
dotnet run
```

**Terminal 3 - HTTP Client:**
```bash
cd "ClienteHTTPObligatorio/ClienteHTTPObligatorio"
dotnet run
```

#### 6. Access the Applications

- **Web API Swagger:** https://localhost:7001/swagger
- **MVC Application:** https://localhost:7002
- **HTTP Client:** https://localhost:7003

---

## 🧪 Testing

### Running Tests

```bash
# Run all tests
cd "Obligatorio.MVC"
dotnet test

# Run with coverage
dotnet test --collect:"XPlat Code Coverage"
```

---

## 📦 Project Structure

### Obligatorio.MVC/
```
├── Obligatorio.DTOs/              # Data Transfer Objects
├── Obligatorio.LogicaAccesoDatos/ # Repositories and DbContext
├── Obligatorio.LogicaAplicacion/  # Use cases
├── Obligatorio.LogicaNegocio/     # Domain entities
├── Obligatorio.MVC/               # MVC web application
├── Obligatorio.Utilidades/        # Shared utilities
├── Obligatorio.WebApi/            # RESTful API
└── Obligatorio.sln                # Main solution
```

### ClienteHTTPObligatorio/
```
├── ClienteHTTPObligatorio/
│   ├── Controllers/               # MVC Controllers
│   ├── Models/                    # ViewModels
│   ├── Views/                     # Razor Views
│   ├── wwwroot/                   # Static files
│   └── Program.cs                 # Entry point
└── ClienteHTTPObligatorio.sln     # Client solution
```

---

## 📊 Diagrams

### Use Case Diagram
See file: `CasosDeUsoObligatorio.png`

### Class Diagram
See file: `DiagramaDeClases.png`

### Astah Model
See files:
- `Obligatorio2Astah.asta` - Astah source file
- `astahObligatorio2.pdf` - Exported diagram in PDF

---

## 📄 Additional Documentation

- **Complete Documentation:** `DocumentacionObligatorioP3.pdf`
- **MVC/API Source Code:** `CodigoFuenteMVCAPI.zip`
- **HTTP Client Source Code:** `CodigoFuenteClienteHTTP.zip`

---

## 🔐 Security

### Authentication and Authorization

- **JWT Tokens** for API authentication
- **ASP.NET Identity** for user management
- **Roles:** Administrator, Staff, Customer
- **Role-based authorization policies**

### Implemented Best Practices

- ✅ Input validation on all endpoints
- ✅ Hashed passwords with secure algorithms
- ✅ HTTPS mandatory in production
- ✅ Token expiration
- ✅ CSRF protection
- ✅ Data sanitization

---

## 🛠️ Technologies Used

### Backend
- ASP.NET Core 8.0
- Entity Framework Core 8.0
- SQL Server
- AutoMapper
- JWT Bearer Authentication

### Frontend
- ASP.NET MVC
- Razor Pages
- Bootstrap 5
- jQuery
- JavaScript

### DevOps
- Azure App Service
- Azure SQL Database
- GitHub Actions (CI/CD)
- Git

### Development Tools
- Visual Studio 2022
- Postman
- SQL Server Management Studio
- Astah UML

---

## 📞 Contact and Support

For project inquiries:

- **Sebastián Hohl:** [SH327007@fi.ort.edu.uy]
- **Matías Oreiro:** [MO239479@fi.ort.edu.uy]

---

## 📜 License

This project was developed as academic coursework for Universidad ORT Uruguay.  
All rights reserved © 2025

---

## 🙏 Acknowledgments

We thank Professor **Joaquín Rodríguez** for his guidance and support during the development of this project.

---

**Universidad ORT Uruguay - Faculty of Engineering - 2025**

---

## 🌐 Language / Idioma

- 🇺🇸 **English version:** You are reading it
- 🇪🇸 **Versión en español:** [README.es.md](README.es.md)
