# Department Management REST API - Spring Boot Project

> 📆 Class Work – Day 11-12

A Spring Boot REST API that provides a robust solution for managing departments and employee count data. This application includes features for creating departments, retrieving information, and enhanced views with error handling.

---

## 🚀 Features

- 🔧 **Department CRUD**: Create and view departments
- 🔍 **Search**: Lookup departments by name
- 👥 **Employee Count**: Get total employees in a department
- 📊 **Department View**: View department + employee count
- 🛡️ **Exception Handling**: Clean JSON error responses
- ✅ **Validation**: Prevent duplicate department IDs

---

## 🧰 Tech Stack

- **Backend Framework**: Spring Boot
- **Persistence**: JPA + Hibernate
- **Language**: Java
- **Design**: REST API

---

## 🗂️ Project Structure

```
src/
└── main/java/lk/ac/vau/fas/ict/
    ├── controller/
    │   └── DepartmentController.java
    ├── service/
    │   └── DepartmentService.java
    ├── model/
    │   ├── Department.java
    │   ├── ViewDepartment.java
    │   └── ErrorResponse.java
    ├── repo/
    │   └── DepartmentRepo.java
    └── exceptionHandler/
        └── GenericExceptionHandler.java
```

---

## 🧩 Data Models

### `Department.java`
| Field       | Description                         |
|-------------|-------------------------------------|
| `id`        | Primary key (unique department ID)  |
| `name`      | Name of the department              |
| `established` | Establishment date               |
| `employees` | List of employee objects (One-to-Many) |

### `ViewDepartment.java`
Extends `Department` with:
- `empcount`: Number of employees in the department

---

## 🌐 API Reference

### 🔗 Base URL
```
http://localhost:8080/dept
```

| Method | Endpoint             | Description                             | Response Type       |
|--------|----------------------|-----------------------------------------|---------------------|
| GET    | `/ {id}`             | Get department by ID                    | `Department`        |
| GET    | `/names`             | List all department names               | `List<String>`      |
| GET    | `/search/{name}`     | Search departments by name              | `List<Department>`  |
| GET    | `/empcount/{id}`     | Get number of employees in a department| `Integer`           |
| GET    | `/vempcount/{id}`    | Get department + employee count         | `ViewDepartment`    |

---

## 🧪 Example API Usage (Screenshots)

1. **Get Department by ID**  
![Get Department](https://github.com/user-attachments/assets/9e275740-6856-4369-8792-49cb527b9fe2)

2. **Get All Department Names**  
![All Names](https://github.com/user-attachments/assets/a17f8085-336a-4d30-9e98-8156ec195582)

3. **Search Department by Name**  
![Search Dept](https://github.com/user-attachments/assets/87a2998d-f1a3-4bc3-9317-a0cc3f9e8107)

4. **Get Employee Count**  
![Emp Count](https://github.com/user-attachments/assets/2d7ff944-e4df-42b3-9da4-26b0b8e83aad)

5. **ViewDepartment with Count**  
![ViewDept](https://github.com/user-attachments/assets/67c59a58-a3fa-4dbc-9d1c-13d920dd0749)

---

## ❗ Error Handling Example

### 404 - Department Not Found

When requesting a non-existent ID:  
![404 Error](https://github.com/user-attachments/assets/b48627e1-26ff-4bd2-8279-c75c1aa42f2e)

---

## ⚙️ Database Configuration

Ensure the following properties are set in `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/employee
spring.datasource.username=root
spring.datasource.password=y
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 🧪 Testing with Postman

To test the API:

1. Create a collection named **Department API**
2. Add requests matching the endpoints above
3. Use `http://localhost:8080/dept` as the base URL
4. Provide test data and verify all responses

---

## 📌 Notes

- Use JPA for entity mapping and database interactions
- Use `@RestController` and `@Service` for clean architecture
- Exception handler class ensures client-friendly error messages

---


