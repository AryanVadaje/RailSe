# RailSe

# 📦 Rate Calculator - Spring Boot Interview Assignment

## 🚀 Objective
This project demonstrates integration with an external API, processes a request, returns the response to the client, and stores the response using a structured, layered Spring Boot application.

---

## 🌐 External API Used
POST https://appapinew.bigship.in/api/RateCalculate

This endpoint calculates shipping rates based on source/destination pincodes, box details, invoice value, etc.

---

## 🧱 Application Layers

| Layer       | Responsibility                                  |
|------------|--------------------------------------------------|
| `Controller` | Handles incoming HTTP requests                 |
| `Service`    | Contains business logic & external API call    |
| `DTO`        | Models request and response data               |
| `Entity`     | Represents database structure                  |
| `Repository` | Mocked JPA repository for saving responses     |

---

## 📄 Technologies Used
- Spring Boot
- Spring Web (`RestTemplate`)
- Spring Data JPA (mocked in-memory)
- Java 11+
- Maven

---

## 📥 Sample Request (POST `/api/rates`)

**Endpoint**
http://localhost:8083/api/rates


**Headers**
Content-Type: application/json


**Body**
```json
{
  "sourcePincode": 560001,
  "destPincode": 600118,
  "boxes": [
    {
      "noofbox": "5",
      "boxlength": "10",
      "boxwidth": "10",
      "boxheight": "10",
      "boxdeadweight": "20"
    }
  ],
  "paymentModeId": 2,
  "invoiceValue": 50000,
  "codAmount": 0,
  "riskTypeId": 0
}
✅ Features Implemented
 Accepts POST request with required JSON input

 Makes a call to external rate calculation API

 Returns full response to client

 Saves response data (raw JSON) in a mock database entity

 Clean, modular layered architecture

 Ready to expand with real database or validation logic

🧪 Optional GET Endpoint
For browser testing:


GET http://localhost:8083/api/rates
Returns a simple text response: "Rate Calculator is running!"

📝 Notes
No actual MySQL database is required — JPA repository is mocked.

Focus is on structure, API integration, and clean separation of concerns.

📂 Project Structure

src
└── main
    └── java
        └── com.example.ratecalculator
            ├── controller
            ├── dto
            ├── entity
            ├── repository
            ├── service
            └── RateCalculatorApplication.java
👨‍💻 Author
Developed as part of a Spring Boot interview assignment.

Code is clean, testable, and ready to be extended further.


---

NOTE the localhost used is 8083 in my project in "application.properties"







