# Spring Boot To-Do Application

A robust task management application built with Spring Boot, MySQL, and Docker.

## 🚀 Features

- Task Management (Create, Read, Update, Delete)
- Docker Containerization
- RESTful API Design
- MySQL Database Integration

## 🛠️ Technologies

- **Backend:** Spring Boot 3.x, Java 21
- **Database:** MySQL
- **Build Tool:** Maven
- **Containerization:** Docker
- **API Documentation:** SpringDoc OpenAPI (Swagger)

## 📋 Prerequisites

- Java Development Kit (JDK) 21
- Docker and Docker Compose
- Maven 3.x
- MySQL (if running locally)

## 🚀 Running the Application

### 💻 Local Development Setup

1. **Clone the repository**
   ```bash
    git clone https://github.com/LastCoderBoy/To_Do_List.git
   # Navigate to the project directory
   ```

2. **Configure Environment**
   ```bash
   cp .env.template .env
   ```
   Edit `.env` file with your local configurations:
   - Change `SPRING_DATASOURCE_URL` to `jdbc:mysql://localhost:3307/your_database_name`
   - Set database credentials
   - Keep port as 3307 (mapped from Docker MySQL)
  
3. **Set up application.properties**
   ```bash
   # Navigate to src/main/resources
   cp application.properties.template application.properties
   ```
   **Update Credentials**
   - Open `application.properties`
   - Fill in your database credentials and other configurations
   - Save the file

4. **Start MySQL Database**
   ```bash
   docker-compose up mysql-database -d
   ```
   Wait a few seconds for the database to initialize.

5. **Build the Application**
   ```bash
   mvn clean install
   ```

6. **Run the Application**
   ```bash
   mvn spring-boot:run
   ```

Your application will be available at:
- Application: http://localhost:8080/api/v1/hometask/
- Swagger UI: http://localhost:8080/swagger-ui.html
- MySQL Database: localhost:3307

### 🐳 Docker Deployment

1. **Clone the repository**
   ```bash
   git clone https://github.com/LastCoderBoy/To_Do_List.git
   # Navigate to the project directory
   ```

2. **Configure Environment**
   ```bash
   cp .env.template .env
   ```
   
   Edit `.env` file:
   - Keep `SPRING_DATASOURCE_URL` as `jdbc:mysql://mysql-database:3306/your_database_name`
   - Set secure passwords for both MySQL root and user
   - Configure other environment variables as needed
  
3. **Set up application.properties**
   ```bash
   # Navigate to src/main/resources
   cp application.properties.template application.properties
   ```
  **Update Credentials**
   - Open `application.properties`
   - Fill in your database credentials and other configurations
   - Save the file

That's it! The template contains all necessary configurations with comments explaining each setting.

4. **Build the Application**
   ```bash
   mvn clean install
   ```

5. **Build and Start Docker Containers**
   ```bash
   docker-compose up
   ```

   This will:
   - Build the Spring Boot application image
   - Create a MySQL container
   - Set up the network between containers
   - Configure volumes for data persistence

6. **Verify Deployment**
   ```bash
   # Check running containers
   docker-compose ps
   
   # View logs
   docker-compose logs -f
   ```

Your dockerized application will be available at:
- Application: http://localhost:8080/api/v1/hometask/
- Swagger UI: http://localhost:8080/swagger-ui.html
- MySQL Database: localhost:3307 (external port)

### Stopping the Application

**For Local Development:**
1. Stop the Spring Boot application (Ctrl+C)
2. Stop the MySQL container:
   ```bash
   docker-compose stop mysql-database
   ```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 👥 Authors

- Jasurbek Khamroev - Learn More - [LastCoderBoy](https://github.com/LastCoderBoy)

## 🙏 Acknowledgments

- Spring Boot Documentation
- Docker Documentation
- Any other resources or people you'd like to thank
