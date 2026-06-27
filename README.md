# Logon APP – C# WinForms Application

<img width="942" height="577" alt="image" src="https://github.com/user-attachments/assets/a5a4b2da-ff20-4287-9b02-292cbe4b70b4" />
<img width="936" height="560" alt="image" src="https://github.com/user-attachments/assets/bccc5091-a6a0-4556-8184-de7e031af606" />

<img width="1108" height="521" alt="image" src="https://github.com/user-attachments/assets/0b8fd533-d2a0-4212-a746-5d078e8a3678" />
<img width="1112" height="510" alt="image" src="https://github.com/user-attachments/assets/cd85a485-73fb-40ef-9c4a-3c1bd6b01635" />

## Overview

**Logon APP** is a desktop application developed in **C# WinForms**, designed for a tech shop in the municipality of **Lebane, Serbia**.

The application provides an interactive interface for:

* user authentication
* managing personal notes
* monitoring live weather data
* customizing application themes

Originally designed for internal use, the application can be adapted for any user by configuring the **database connection** and **API key**.

---

## Features

| Feature                  | Description                                                                   |
| ------------------------ | ----------------------------------------------------------------------------- |
|  Authentication        | User registration and login system with SHA256 password hashing               |
|  Quick Notes           | Add, update, delete, and view notes stored in a Microsoft SQL Server database |
|  Weather Information  | Displays real-time weather data for Lebane using OpenWeather API              |
|  Theming               | Light, Dark, and Default themes for UI customization                          |
|  Animated Logo        | Dynamic logo animation for improved UI experience                             |
|  Clock & Date           | Live time and date display                                                    |
|  Database Integration | Full CRUD operations using SQL Server and stored procedures                   |

---

## 🛠️ Technologies Used

| Technology              | Purpose                   |
| ----------------------- | ------------------------- |
| C#                      | Core programming language |
| WinForms                | Desktop GUI framework     |
| .NET 8                  | Application runtime       |
| Microsoft SQL Server    | Database (Users & Notes)  |
| ADO.NET                 | Database communication    |
| OpenWeather API         | Weather data              |
| JSON                    | API response parsing      |
| Microsoft Visual Studio | Development environment   |
| Git & GitHub            | Version control           |

---

##  Database Structure

### Users

* Id (Primary Key)
* Username (Unique)
* PasswordHash
* CreatedAt

### Notes

* Id (Primary Key)
* Content
* UserId (Foreign Key)
* CreatedAt

**Relationship:**

* One user → many notes
* Foreign key constraint ensures data integrity

---

## Database Setup

1. Open **SQL Server Management Studio (SSMS)**
2. Run the script located in:

   ```
   Database/DatabaseSetup.sql
   ```
3. Make sure your connection string in `app.config` matches your SQL Server instance:

```xml
Data Source=LOCALHOST\SQLEXPRESS;
Initial Catalog=LogonDB;
Integrated Security=True;
```

---

## OpenWeather API Integration

The application integrates with the OpenWeather API to display live weather data.

### Data Displayed

* Temperature
* Feels Like
* Humidity
* Wind Speed
* Cloud Coverage
* Weather Description

---

### API Key Setup

1. Create a free account at:
   https://openweathermap.org/api

2. Generate your API key

3. Set it as an environment variable:

#### Windows (PowerShell)

```powershell
setx MY_API_KEY "your_api_key_here"
```

---

##  Installation

```bash
git clone https://github.com/MIhajloS07/Logon-FullStack-App.git
```

1. Open project in Visual Studio
2. Setup database (see above)
3. Set API key
4. Run the application

---

##  Security

* Passwords are hashed using **SHA256**
* No sensitive data is stored in the repository
* API key is stored using environment variables
* Uses Windows Authentication for database access

---

##  Author

**Mihajlo Stoiljkovic**

---

## License

This project is licensed under the MIT License.
![license](https://img.shields.io/badge/license-MIT-green?style=flat)
