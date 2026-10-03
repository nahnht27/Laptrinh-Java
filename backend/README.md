# Backend — Spring Boot

## Tech Stack

| Component   | Version / Tool      |
|-------------|---------------------|
| Language    | Java 17             |
| Framework   | Spring Boot 3.2.5   |
| Build Tool  | Maven 3.9.6         |
| Database    | PostgreSQL          |

## Dependencies (Sprint 1)

- `spring-boot-starter-web` — REST API
- `spring-boot-starter-data-jpa` — ORM / Repository pattern
- `spring-boot-starter-validation` — Bean Validation (Jakarta)
- `postgresql` — JDBC driver

## Project Structure

```
backend/
├── .mvn/wrapper/          # Maven Wrapper
├── src/
│   ├── main/
│   │   ├── java/com/university/backend/
│   │   │   ├── controller/     # REST Controllers
│   │   │   ├── service/        # Business Logic (tạo sau)
│   │   │   ├── repository/     # JPA Repositories (tạo sau)
│   │   │   ├── model/          # Entity classes (tạo sau)
│   │   │   ├── dto/            # Data Transfer Objects (tạo sau)
│   │   │   ├── exception/      # Custom exceptions (tạo sau)
│   │   │   └── BackendApplication.java
│   │   └── resources/
│   │       └── application.yml
│   └── test/
├── mvnw                   # Maven Wrapper script
├── pom.xml
└── .gitignore
```

## Quick Start

```bash
# Đảm bảo PostgreSQL đang chạy, database 'university_db' đã tồn tại
# Sửa username/password trong application.yml nếu cần

# Chạy app (tự download Maven nếu chưa có)
./mvnw spring-boot:run

# Hoặc nếu đã cài Maven global
mvn spring-boot:run

# Health check
curl http://localhost:8080/api/health
```

## Cấu hình Database

Sửa file `src/main/resources/application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/university_db
    username: postgres
    password: postgres
```

## Chưa cần thêm ngay (để Sprint sau)

- Spring Security / JWT
- Swagger / OpenAPI
- Lombok
- MapStruct
- Redis
- Docker Compose
