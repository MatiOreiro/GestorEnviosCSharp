# Sistema de Gestión de Envíos | Shipping Management System
## Obligatorio Programación 3 | Programming 3 Assignment

> 🇪🇸 [Leer en Español](#español) | 🇺🇸 [Read in English](#english)

---

# Español

## 📋 Información del Proyecto

**Universidad:** ORT Uruguay  
**Facultad:** Ingeniería  
**Escuela:** Tecnología  
**Asignatura:** Programación 3  
**Carrera:** Analista Programador / Analista en Tecnologías de la Información  
**Grupo:** M3C  
**Docente:** Joaquín Rodríguez

### 👥 Integrantes
- **Sebastián Hohl** - 327007
- **Matías Oreiro** - 239479

**Fecha de entrega:** 26/06/2025

---

## 📝 Descripción del Proyecto

Sistema integral de gestión de envíos desarrollado con arquitectura multicapa en .NET 8.0. El proyecto implementa un sistema completo para la administración de envíos de paquetería, con gestión de usuarios, empleados, seguimiento de envíos y comentarios.

El sistema consta de tres componentes principales:
1. **Web API RESTful** - Backend con arquitectura en capas
2. **Aplicación Web MVC** - Interfaz de administración y gestión para funcionarios
3. **Cliente HTTP** - Interfaz pública para clientes

---

## 🏗️ Arquitectura del Sistema

### Componentes Principales

#### 1. **Obligatorio.WebApi**
API RESTful que expone los endpoints para todas las operaciones del sistema.

**Tecnologías:**
- ASP.NET Core 8.0
- Entity Framework Core
- SQL Server
- JWT Authentication

#### 2. **Obligatorio.MVC**
Aplicación web con patrón MVC para gestión administrativa.

**Funcionalidades:**
- Login de administradores y funcionarios
- ABM de empleados
- Gestión de envíos
- Visualización de seguimientos
- Sistema de comentarios

#### 3. **ClienteHTTPObligatorio**
Cliente web que consume la API para funcionalidades públicas.

**Funcionalidades:**
- Alta y finalización de envíos
- Ingreso de comentarios
- Consulta de envíos por tracking
- Búsqueda de envíos propios
- Búsqueda por fechas y palabras clave
- Cambio de contraseña

### Capas de la Arquitectura

```
┌─────────────────────────────────┐
│   Presentación (MVC/HTTP)       │
├─────────────────────────────────┤
│   WebApi (Controllers)          │
├─────────────────────────────────┤
│   Lógica de Aplicación          │
├─────────────────────────────────┤
│   Lógica de Negocio (Dominio)   │
├─────────────────────────────────┤
│   Acceso a Datos (EF Core)      │
├─────────────────────────────────┤
│   Base de Datos (SQL Server)    │
└─────────────────────────────────┘
```

**Proyectos:**
- `Obligatorio.WebApi` - Capa de servicios REST
- `Obligatorio.MVC` - Capa de presentación web
- `Obligatorio.LogicaAplicacion` - Casos de uso y coordinación
- `Obligatorio.LogicaNegocio` - Entidades y reglas de negocio
- `Obligatorio.LogicaAccesoDatos` - Repositorios y contexto EF
- `Obligatorio.DTOs` - Objetos de transferencia de datos
- `Obligatorio.Utilidades` - Helpers y utilidades comunes

---

## 👤 Roles y Casos de Uso

### Administrador
- ✅ Login/Logout
- ✅ Alta de empleados
- ✅ Editar empleados
- ✅ Baja de empleados
- ✅ Mostrar empleados
- ✅ Alta de envíos
- ✅ Finalizar envíos
- ✅ Ingresar comentarios
- ✅ Mostrar comentarios
- ✅ Obtener detalles de envío
- ✅ Cambiar contraseña
- ✅ Obtener envío por tracking
- ✅ Obtener envíos propios
- ✅ Obtener envíos entre dos fechas
- ✅ Obtener envíos según palabra clave

### Funcionario
- ✅ Login/Logout
- ✅ Baja de empleados
- ✅ Mostrar empleados
- ✅ Alta de envíos
- ✅ Finalizar envíos
- ✅ Ingresar comentarios
- ✅ Mostrar comentarios
- ✅ Obtener detalles de envío
- ✅ Cambiar contraseña
- ✅ Obtener envío por tracking
- ✅ Obtener envíos propios
- ✅ Obtener envíos entre dos fechas
- ✅ Obtener envíos según palabra clave

### Cliente (Público)
- ✅ Alta de envíos
- ✅ Finalizar envíos
- ✅ Ingresar comentarios
- ✅ Mostrar comentarios
- ✅ Obtener detalles de envío
- ✅ Cambiar contraseña
- ✅ Obtener envío por tracking
- ✅ Obtener envíos propios
- ✅ Obtener envíos entre dos fechas
- ✅ Obtener envíos según palabra clave

---

## 🗄️ Base de Datos

### Información de Conexión (Azure)

**Base de datos:** ObligatorioP3  
**Servidor:** obligatoriop3oreirohohl.database.windows.net  
**Puerto:** 1433  
**Usuario SQL:** SfCGQFPV

**Cadena de conexión:**
```
Server=tcp:obligatoriop3oreirohohl.database.windows.net,1433;
Initial Catalog=ObligatorioP3;
Persist Security Info=False;
MultipleActiveResultSets=False;
Encrypt=True;
TrustServerCertificate=False;
Connection Timeout=30;
```

### Scripts SQL Disponibles
- `ObligatorioDatabase.sql` - Script para base de datos local
- `ObligatorioDatabaseAzure.sql` - Script para Azure SQL Database

---

## 🚀 Despliegue en Azure

### URLs de Producción

**Web API:**
```
https://webapiobligatoriop3oreirohohld6c6e0g6g0fedbgd.brazilsouth-01.azurewebsites.net/
```

**Aplicación Web MVC:**
```
https://webappobligatoriop3-cghkfrgsg3a0cyex.brazilsouth-01.azurewebsites.net/
```

**Cliente HTTP:**
```
https://clientehttpobligatoriop3oreirohohlesd0hrf3c9dafnfr.brazilsouth-01.azurewebsites.net/
```

---

## 📚 Documentación de API

### Postman Collections

**Deploy en Azure:**
```
https://documenter.getpostman.com/view/42495957/2sB2xEAo4v
```

**Deploy Local:**
```
https://documenter.getpostman.com/view/42495957/2sB2xEAo4x
```

---

## 💻 Instalación y Configuración Local

### Prerrequisitos

- .NET 8.0 SDK o superior
- SQL Server 2019 o superior (o SQL Server Express)
- Visual Studio 2022 o Visual Studio Code
- Git

### Pasos de Instalación

#### 1. Clonar el Repositorio
```bash
git clone https://github.com/MatiOreiro/GestorEnviosCSharp.git
cd GestorEnviosCSharp
```

#### 2. Configurar Base de Datos

**Opción A: SQL Server Local**
```bash
# Ejecutar el script en SQL Server Management Studio
sqlcmd -S localhost -i ObligatorioDatabase.sql
```

**Opción B: Azure SQL Database**
```bash
sqlcmd -S obligatoriop3oreirohohl.database.windows.net -U SfCGQFPV -i ObligatorioDatabaseAzure.sql
```

#### 3. Configurar Cadenas de Conexión

**Para Obligatorio.WebApi:**

Editar `Obligatorio.MVC/Obligatorio.WebApi/appsettings.json`:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=ObligatorioP3;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=True"
  }
}
```

**Para Obligatorio.MVC:**

Editar `Obligatorio.MVC/Obligatorio.MVC/appsettings.json`:
```json
{
  "ApiSettings": {
    "BaseUrl": "https://localhost:7001/api"
  }
}
```

**Para ClienteHTTPObligatorio:**

Editar `ClienteHTTPObligatorio/ClienteHTTPObligatorio/appsettings.json`:
```json
{
  "ApiSettings": {
    "BaseUrl": "https://localhost:7001/api"
  }
}
```

#### 4. Restaurar Dependencias

```bash
# Para el proyecto principal (MVC + API)
cd Obligatorio.MVC
dotnet restore

# Para el cliente HTTP
cd ../ClienteHTTPObligatorio
dotnet restore
```

#### 5. Ejecutar las Aplicaciones

**Terminal 1 - Web API:**
```bash
cd Obligatorio.MVC/Obligatorio.WebApi
dotnet run
```

**Terminal 2 - Aplicación MVC:**
```bash
cd Obligatorio.MVC/Obligatorio.MVC
dotnet run
```

**Terminal 3 - Cliente HTTP:**
```bash
cd ClienteHTTPObligatorio/ClienteHTTPObligatorio
dotnet run
```

#### 6. Acceder a las Aplicaciones

- **Web API Swagger:** https://localhost:7001/swagger
- **Aplicación MVC:** https://localhost:7002
- **Cliente HTTP:** https://localhost:7003

---

## 📦 Estructura del Proyecto

### Obligatorio.MVC/
```
├── Obligatorio.DTOs/              # Data Transfer Objects
├── Obligatorio.LogicaAccesoDatos/ # Repositorios y DbContext
├── Obligatorio.LogicaAplicacion/  # Casos de uso
├── Obligatorio.LogicaNegocio/     # Entidades de dominio
├── Obligatorio.MVC/               # Aplicación web MVC
├── Obligatorio.Utilidades/        # Utilidades compartidas
├── Obligatorio.WebApi/            # API RESTful
└── Obligatorio.sln                # Solución principal
```

### ClienteHTTPObligatorio/
```
├── ClienteHTTPObligatorio/
│   ├── Controllers/               # Controladores MVC
│   ├── Models/                    # ViewModels
│   ├── Views/                     # Vistas Razor
│   ├── wwwroot/                   # Archivos estáticos
│   └── Program.cs                 # Punto de entrada
└── ClienteHTTPObligatorio.sln     # Solución del cliente
```

---

## 📊 Diagramas

### Casos de Uso
Ver archivo: `CasosDeUsoObligatorio.png`

### Diagrama de Clases
Ver archivo: `DiagramaDeClases.png`

### Modelo Astah
Ver archivos:
- `Obligatorio2Astah.asta` - Archivo fuente de Astah
- `astahObligatorio2.pdf` - Diagrama exportado en PDF

---

## 📄 Documentación Adicional

- **Documentación Completa:** `DocumentacionObligatorioP3.pdf`
- **Código Fuente MVC/API:** `CodigoFuenteMVCAPI.zip`
- **Código Fuente Cliente HTTP:** `CodigoFuenteClienteHTTP.zip`

---

## 🔐 Seguridad

### Autenticación y Autorización

- **JWT Tokens** para autenticación de API
- **ASP.NET Identity** para gestión de usuarios
- **Roles:** Administrador, Funcionario, Cliente
- **Políticas de autorización** por rol

### Buenas Prácticas Implementadas

- ✅ Validación de entrada en todos los endpoints
- ✅ Passwords hasheados con algoritmos seguros
- ✅ HTTPS obligatorio en producción
- ✅ Tokens con expiración
- ✅ Protección contra CSRF
- ✅ Sanitización de datos

---

## 🛠️ Tecnologías Utilizadas

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

### Herramientas de Desarrollo
- Visual Studio 2022
- Postman
- SQL Server Management Studio
- Astah UML

---

## 📞 Contacto y Soporte

Para consultas sobre el proyecto:

- **Sebastián Hohl:** [SH327007@fi.ort.edu.uy]
- **Matías Oreiro:** [MO239479@fi.ort.edu.uy]

---

## 📜 Licencia

Este proyecto fue desarrollado como trabajo académico para la Universidad ORT Uruguay.  
Todos los derechos reservados © 2025

---

## 🙏 Agradecimientos

Agradecemos al profesor **Joaquín Rodríguez** por su guía y apoyo durante el desarrollo de este proyecto.

---

<div align="center">

**Universidad ORT Uruguay - Facultad de Ingeniería - 2025**

</div>

---
---
---

# English

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
git clone https://github.com/MatiOreiro/GestorEnviosCSharp.git
cd GestorEnviosCSharp
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
cd Obligatorio.MVC
dotnet restore

# For the HTTP client
cd ../ClienteHTTPObligatorio
dotnet restore
```

#### 5. Run the Applications

**Terminal 1 - Web API:**
```bash
cd Obligatorio.MVC/Obligatorio.WebApi
dotnet run
```

**Terminal 2 - MVC Application:**
```bash
cd Obligatorio.MVC/Obligatorio.MVC
dotnet run
```

**Terminal 3 - HTTP Client:**
```bash
cd ClienteHTTPObligatorio/ClienteHTTPObligatorio
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
cd Obligatorio.MVC
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

<div align="center">

**Universidad ORT Uruguay - Faculty of Engineering - 2025**

</div>
