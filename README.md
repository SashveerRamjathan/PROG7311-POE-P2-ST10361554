# Agri-Energy Connect Prototype

Welcome to the **Agri-Energy Connect Platform** – a prototype showcasing a scalable and secure solution for connecting farmers and energy providers in South Africa. This readme will guide you through the setup, architecture, and key features of the system.

---

## 🌱 Project Overview

### What the App Does

The Agri-Energy Connect platform enables:

- **Farmers** to manage their product listings.
- **Employees** to add new farmers, manage their profiles and products, and view/filter product lists.

The app includes **advanced filtering** features to enhance product management.

### Who It's Intended For

This platform is designed for:

- **Farmers** aiming to showcase their produce.
- **Energy providers** and stakeholders in **sustainable agriculture and green energy**.

It creates a marketplace to encourage **collaboration and innovation** around food and energy sustainability in South Africa.

---

## 🏗️ Architecture and Design

### System Architecture

The system follows a **microservices-based architecture** using:

- **ASP.NET Core Web API**: Handles authentication, data storage, and business logic.
- **ASP.NET Core MVC Web App**: Acts as the user interface.
- **Shared Class Library**: Used to share models and contracts between the API and MVC projects.

This modular setup ensures **scalability**, **flexibility**, and **maintainability**.

#### 🧱 Microservice Layout

- **MVC Client**
  - Located in `/AgriEnergyConnect.MVC`
  - Lightweight frontend with no direct DB/auth setup.
  - Uses `Program.cs` to configure services and set up JWT-based authentication.

- **API Service**
  - Located in `/AgriEnergyConnect.API`
  - Manages the **SQLite database**, **authentication**, and **business logic**.
  - Uses JWT tokens for stateless security.
  
- **Shared Class Library**
  - Located in `/AgriEnergyConnect.Shared`
  - Contains models (DTOs), validation attributes, and shared logic across API and MVC.

---

### 🧩 Design Pattern: Layered Architecture

- **MVC Controllers** handle business logic, service calls, and data mapping.
- **Views** (Razor `.cshtml`) manage data presentation.
- This separation improves **code organization**, **testability**, and **maintainability**.

---

## 🗃️ Database Usage

- **SQLite** is used for lightweight, persistent storage.
- It is portable and doesn’t require server configuration.
- Offers **data persistence**, unlike in-memory databases.
- Pre-populated with:
  - Users (Employees & Farmers)
  - Products
  - Product Categories

---

## 🧪 Feature Demonstration (Based on Rubric)

| Feature | Description |
|--------|-------------|
| 🔐 Authentication Required | Employees and Farmers **must log in** to view or manage data. |
| 👩‍🌾 Add Farmer | Employees can **add new farmers** after logging in. |
| 🧺 Add Product | Farmers can **add new products** to their profile post-login. |
| 📋 View Product Lists | Employees can **view a list of products** supplied by a specific farmer. |
| 🧼 Filter Products | Employee views can be filtered by **date range** and **product type**. |
| 📦 Farmer Product View | Farmers can **view all products** associated with their profile. |
| 🧾 Preloaded Data | Database is **preloaded** with demo users, products, and categories. |
| ➕ Product Creation | Farmers can easily create products using a simple form interface. |
| 🏷️ Categories | Products are linked to **categories** to simplify browsing/filtering. |

---

## ⚙️ Project Setup Instructions

### ✅ Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download)
- [Visual Studio 2022+](https://visualstudio.microsoft.com/)
- Git

---

### 📥 Clone and Open the Project

```bash
git clone https://github.com/your-username/agri-energy-connect.git
cd agri-energy-connect
Open the solution in Visual Studio.

Identify the following folders:

/AgriEnergyConnect.API – Backend Web API

🔧 Configure and Run the System
Important: Run the API first, then the MVC Web App.

🛠 API Project Setup
Set AgriEnergyConnect.API as the startup project.

No need to update the connection string in appsettings.json.

Run the API (F5 or Ctrl + F5).

🛠 MVC Project Setup
Set AgriEnergyConnect.MVC as the startup project.

Open appsettings.json and confirm the BaseUrl matches the running API address.

/AgriEnergyConnect.MVC – Frontend MVC Web App

Run the MVC App.

/AgriEnergyConnect.Shared – Shared project for DTOs and models

