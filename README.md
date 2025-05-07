# Spring Boot JUnit 5 + Mockito Example

This project demonstrates a layered Spring Boot application with JUnit 5 + Mockito tests, Flyway for database migrations, and Docker integration.

## Prerequisites

- JDK 17 or higher
- Maven
- Docker and Docker Compose (for containerized environment)

## Project Structure

```
src/
  main/
    java/com/example/demo/
      controller/UserController.java
      model/User.java
      repository/UserRepository.java
      service/UserService.java
  resources/
    db/migration/V1__init.sql (Flyway migration)
    application.yml (Flyway and DB config)
```

## Running the Application

### 1. Running Locally without Docker

To run the application locally:

1. Clone or download the repository.
2. Navigate to the root folder in your terminal.
3. Build the application with Maven:

   ```
   mvn clean install
   ```

4. Run the application:

   ```
   mvn spring-boot:run
   ```

5. The application should be available at `http://localhost:8080`.

### 2. Running with Docker and Docker Compose

You can run the application using Docker and Docker Compose for a containerized environment.

1. Clone or download the repository.
2. Navigate to the root folder in your terminal.
3. Build the Docker images:

   ```
   docker-compose build
   ```

4. Start the containers:

   ```
   docker-compose up
   ```

5. The application should now be running on `http://localhost:8080`.

### 3. Database Migration

Flyway is used to manage database migrations. The migration script (`V1__init.sql`) creates the necessary tables in the database.

Flyway will automatically apply the migration when the application starts.

### 4. Running Tests

To run unit tests and integration tests:

```
mvn test
```

This will execute the tests and ensure the correctness of the code.

### 5. Testing Endpoints

#### GET /users/{email}

Retrieve a user by email.

Example:

```
GET http://localhost:8080/users/alice@example.com
```

#### POST /users

Create a new user.

Example body:

```json
{
  "name": "Alice",
  "email": "alice@example.com"
}
```

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.# springboot-mockito-demo
