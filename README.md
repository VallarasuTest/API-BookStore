# API-BookStore
# 📚 Bookstore API Automation Framework

## 🚀 Introduction
 **Bookstore API Automation Framework**! This project is designed to test a Bookstore REST API efficiently using **RestAssured** and **TestNG**. It ensures all the API functionalities work as expected.

## 🛠️ Technologies Used
- **Java 11+** – Core programming language
- **RestAssured** – For API testing
- **TestNG** – To manage and execute tests
- **Maven** – For dependency management
- **JSON** – To handle request and response data

## 📂 Project Structure
```
BookstoreAPIAutomation/
│── src/
│   ├── test/
│   │   ├── java/tests/
│   │   │   ├── BookStoreAPITest.java
│   │   │   ├── APIUtils.java
│   │   │   ├── EndPoints.java
│   │   │   ├── BaseAPI.java
│   │   ├── resources/
│   │   │   ├── config.properties
│── pom.xml
│── README.md
```

## 🔧 How to Set Up & Run the Project
### 1️⃣ Prerequisites
Before you start, make sure you have:
- **Java 11+** installed
- **Maven** installed
- **Postman** (Optional, for manual testing)

### 2️⃣ Clone or Create the Project
If you are **cloning an existing repository**:
```sh
git clone <repository-url>
cd BookstoreAPIAutomation
```
If you need to **set up a new project from scratch**:
```sh
mkdir BookstoreAPIAutomation
cd BookstoreAPIAutomation
mvn archetype:generate -DgroupId=com.example -DartifactId=bookstore -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

### 3️⃣ Configure the API Base URL
Open `src/test/resources/config.properties` and update the base URL:
```
base.url=http://localhost:8000
```

### 4️⃣ Run API Tests
To execute all tests using Maven, run:
```sh
mvn test
```
Or, you can run them using TestNG in IntelliJ/Eclipse.

### 5️⃣ Generate & View Test Reports
To generate a detailed test report, run:
```sh
mvn surefire-report:report
```
Once completed, reports will be available in:
```
target/surefire-reports
```

## 🔗 API Endpoints
Here are the API endpoints tested in this framework:

| Method | Endpoint       | Description               |
|--------|---------------|---------------------------|
| GET    | /books        | Fetch all books           |
| GET    | /books/{id}   | Fetch a book by ID        |
| POST   | /books        | Create a new book         |
| PUT    | /books/{id}   | Update an existing book   |
| DELETE | /books/{id}   | Delete a book             |

## 📝 Running API Requests Manually
Want to test the API outside of the framework? Use the following **cURL commands**:

### Create a New Book
```sh
curl -X POST http://localhost:8000/books \
     -H "Content-Type: application/json" \
     -d '{"title":"Test Book","author":"John Doe","price":19.99}'
```

### Get a Book by ID
```sh
curl -X GET http://localhost:8000/books/1
```

### Update a Book
```sh
curl -X PUT http://localhost:8000/books/1 \
     -H "Content-Type: application/json" \
     -d '{"title":"Updated Book","author":"John Doe","price":25.99}'
```

### Delete a Book
```sh
curl -X DELETE http://localhost:8000/books/1
```

## 🛠️ Troubleshooting
- If the API is not running, try starting it with:
  ```sh
  mvn spring-boot:run
  ```
- If tests fail, check the logs in:
  ```
  target/surefire-reports/
  ```



