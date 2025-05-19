# 🏢 Employee Management System - Day09 (2025-05-16)

A Spring Boot-based application to manage employees, departments, and project assignments within an organization.

---

## 📝 Overview

The **Employee & Department Management System** is designed to handle internal organizational structures. It provides RESTful APIs for managing:

* 🏢 Departments
* 👨‍💼 Employees
* 🛠️ Projects

It includes entity relationships and CRUD operations for core resources such as employees and departments.

---

## 🛠️ Technical Stack

| Component    | Technology      |
| ------------ | --------------- |
| 💻 Framework | Spring Boot     |
| ☕ Language   | Java            |
| 🗄️ Database | MySQL           |
| 🧬 ORM       | Hibernate / JPA |
| 🌐 API Type  | RESTful APIs    |

---

## ⚙️ Database Configuration

Ensure your MySQL server is running and configure your connection in `application.properties`:

```properties
spring.application.name=day9
spring.datasource.url=jdbc:mysql://localhost:3306/employeedb
spring.datasource.username=root
spring.datasource.password=
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
```

---

## 🧩 Data Model

### 🏢 Department

Represents a department within the organization:

* `DepId` (Primary Key)
* `DName` – Department Name
* `Location` – Department Location
* 👥 `employees` – One-to-Many relationship with Employee

---

### 👨‍💼 Employee

Represents an employee:

* `EmpId` (Primary Key)
* `EmpName` – Name of the employee
* `Job` – Job title
* `Salary` – Salary in double
* `DOB` – Date of birth
* 🔁 `department` – Many-to-One relationship with Department

---

### 👥 Person *(Mapped Superclass)*

A base class used for shared attributes (used by other potential entities):

* `name`
* `age`
* `gender`

---

### 🛠️ Project

Represents a project employees work on:

* `id` – Primary key
* `name` – Name of the project
* `totalCost` – Total cost of the project
* 🔗 `employees` – Many-to-Many relationship with Employee

---

## 📡 REST API Endpoints

### `/dept`

| Method | Endpoint          | Description                |
| ------ | ----------------- | -------------------------- |
| GET    | `/all`            | Get all departments        |
| GET    | `/{depId}`        | Get department by ID       |
| POST   | `/add`            | Create new department      |
| PUT    | `/update/{depId}` | Update existing department |
| DELETE | `/delete/{depId}` | Delete department by ID    |

---

## 🚀 Setup Instructions

### ✅ Prerequisites

* Java 17+
* MySQL Server
* Maven

### ▶️ Run the Application

```bash
mvn spring-boot:run
```

Or build and run:

```bash
mvn clean install
java -jar target/day9-0.0.1-SNAPSHOT.jar
```

---

## 🏁 Sample Output (UI or API Clients)

📸 *screenshots of Postman*

![1 getall](https://github.com/user-attachments/assets/92dcb297-a9a2-44b7-b28e-f045acdd15be)

![2 getById](https://github.com/user-attachments/assets/482871ca-ba29-4e15-ba6b-7e8fdf4fc527)

![3 add](https://github.com/user-attachments/assets/85da3395-6904-489e-85ef-0ab6836de9e7)

![4 update](https://github.com/user-attachments/assets/eb0a3102-db6d-4a62-96a5-9d60ae6ced0c)

![5 update error](https://github.com/user-attachments/assets/74517432-f98d-4762-83cf-89385ef1a811)

![6 delete](https://github.com/user-attachments/assets/c131c5ba-4d21-4a1c-9f6c-a866c6de96d3)

---

## 📃 License

This project is intended for **educational and academic purposes** only. 📚
