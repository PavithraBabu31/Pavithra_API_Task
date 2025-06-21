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
api-automation-framework/
│── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── com/api/testing/RestAssuredTest/ (Test Cases)
│   │   │   ├── com/api/testing/RestAssuredTest/base/ (Base Test Class)
│   │   │   ├── com/api/testing/RestAssuredTest/utils/ (Utilities - ConfigReader, ReportManager)
│   ├── test/
│── test-output/ (Generated Reports)
│── config.properties (Configuration Settings)
│── pom.xml (Maven Dependencies)
│── README.md (This File)
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
cd RestAssuredTest
```
```

### 3️⃣ Configure the API Base URL
Open `src/test/resources/config.properties` and update the base URL:
```
# Default environment (local or ci)
env=local

# Base URLs for different environments

base.url.local=http://127.0.0.1:8000
base.url.ci=http://localhost:8000 # Change if using cloud deployment

```

### 4️⃣ Run API Tests
To execute all tests using Maven, run:
```sh
mvn test
```
Or, you can run them using TestNG in IntelliJ/Eclipse.

**View Reports**:

After test execution, test reports are generated automatically.

Open test-output/ExtentReport.html in a browser to view detailed test execution results.

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
📝 Test Scenarios Covered
#	Test Case	Endpoint	Expected Status Code
+----+----------------------------------+---------------------------+-------------------+
| #  | Test Case                        | Endpoint                  | Expected Status  |
+----+----------------------------------+---------------------------+-------------------+
| 1️⃣  | User Signup                     | POST /signup              | 200 ✅            |
| 2️⃣  | User Login                      | POST /login               | 200 ✅            |
| 3️⃣  | Create a Book                   | POST /books/              | 200 ✅            |
| 4️⃣  | Get Book by ID                  | GET /books/{id}           | 200 ✅            |
| 5️⃣  | Delete Book                     | DELETE /books/{id}        | 200 ✅            |
| 6️⃣  | Login with Invalid Credentials  | POST /login               | 400 ❌            |
| 7️⃣  | Unauthorized Access to Books    | GET /books/1              | 403 ❌            |
| 8️⃣  | Create Multiple Books (DP)      | POST /books/              | 200 ✅            |
| 9️⃣  | Signup with Existing Email      | POST /signup              | 200 ✅            |
| 🔟  | Login with Incorrect Password   | POST /login               | 400 ❌            |
| 1️⃣1️⃣ | Get Book with Invalid ID         | GET /books/999999         | 404 ❌            |
+----+----------------------------------+---------------------------+-------------------+



## 📝 Running API Requests Manually
Want to test the API outside of the framework? Use the following **cURL commands**:

### Create a New User (Signup)
```sh
curl -X POST http://127.0.0.1:8000/signup \
     -H "Content-Type: application/json" \
     -d '{"email":"dummy1@example.com","password":"dummy123"}'
```

### Login to Get Token
```sh
curl -X POST http://127.0.0.1:8000/login \
     -H "Content-Type: application/json" \
     -d '{"email":"dummy1@example.com","password":"dummy123"}'

```

### Create a New Book
```sh
curl -X POST http://127.0.0.1:8000/books/ \
     -H "Authorization: Bearer <ACCESS_TOKEN>" \
     -H "Content-Type: application/json" \
     -d '{"name":"The Catcher in the Rye","author":"J.D. Salinger","published_year":1951,"book_summary":"A story about teenage angst."}'

```

### Get Book by ID
```sh
curl -X GET http://127.0.0.1:8000/books/1 \
     -H "Authorization: Bearer <ACCESS_TOKEN>"

```
### Delete a Book
```sh
curl -X DELETE http://127.0.0.1:8000/books/1 \
     -H "Authorization: Bearer <ACCESS_TOKEN>"

```

### Test Reporting & Logging

Extent Reports: Test execution results are saved in test-output/ExtentReport.html

Surefire Reports: Run mvn surefire-report:report to generate test reports in target/surefire-reports/

Logging: Detailed logs available in target/logs/


### 🛠️ Troubleshooting
- If the API is not running, try starting it with:
  ```sh
  mvn test
  ```
- If tests fail, check the logs in:
  ```
  target/surefire-reports/
  ```



