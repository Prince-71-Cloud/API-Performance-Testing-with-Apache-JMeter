# API Performance Testing with Apache JMeter

## Overview

This project demonstrates performance testing of the **Restful Booker API** using **Apache JMeter**. The goal is to evaluate the API's performance under load, analyzing key metrics such as **throughput**, **response times**, **error rates**, and **APDEX scores**. Results are visualized in a comprehensive **JMeter HTML dashboard**.

---

## Test Details

- **API Tested:** Restful Booker (a mock hotel booking REST API)

### Endpoints Tested

- `POST /auth` – Authenticate and retrieve a token  
- `GET /booking` – Retrieve all bookings  
- `POST /booking` – Create a new booking  
- `GET /booking/{id}` – Retrieve a specific booking  
- `PUT /booking/{id}` – Update a booking  
- `PATCH /booking/{id}` – Partially update a booking  
- `DELETE /booking/{id}` – Delete a booking  

### Test Configuration

- **Concurrent Users:** 10  
- **Test Duration:** ~1 minute  
  - Start: `07/27/25, 10:34 PM`  
  - End: `07/27/25, 10:35 PM`  
- **Ramp-up Period:** 10 seconds  

### Key Metrics

- **Throughput:** Refer to JMeter dashboard  
- **Average Response Time:** Refer to JMeter dashboard  
- **Error Rate:** See **Errors** section in dashboard  
- **APDEX Score:** See **APDEX** section in dashboard  

---

## Prerequisites

- [Apache JMeter](https://jmeter.apache.org/) (version 5.5 or later recommended)  
- Java Runtime Environment (JRE) or Java Development Kit (JDK) 8+  
- A CSV file (`users.csv`) with the following columns: `username`, `password`

---

## Project Structure
 .<br>
├── Restful-booker.jmx  [ JMeter test plan ] <br>
├── index.html   [ Generated JMeter HTML dashboard ] <br>
└── README.md

## Setup and Running the Tests

### 1. Install JMeter

- Download and install **Apache JMeter**
- Ensure **Java** is installed and configured in your system path

### 2. Prepare the CSV File

Create a `users.csv` file with the following structure:
`
username,password
user1,password1
user2,password2
`

> Place it in an accessible directory, e.g., `/home/prince/Documents/users.csv`

### 3. Run the Test

- Open JMeter using `jmeter.sh` (Linux/Mac) or `jmeter.bat` (Windows)
- Load the `Restful-booker.jmx` file
- Ensure the API is accessible: [https://restful-booker.herokuapp.com](https://restful-booker.herokuapp.com)

To run in **non-GUI mode**:

```bash
jmeter -n -t Restful-booker.jmx -l Restful_Booker.jtl -e -o dashboard
```
This generates Restful_Booker.jtl and a dashboard folder with the HTML report.

## Screenshots
<img width="1888" height="315" alt="Test_and_Report_Information" src="https://github.com/user-attachments/assets/7db57156-f058-4a77-b042-6c61043c3821" />
<img width="1888" height="292" alt="Request_Summery" src="https://github.com/user-attachments/assets/e5d85002-8e9f-4373-8533-1694b6dea8b7" />
<img width="1888" height="467" alt="Statistics" src="https://github.com/user-attachments/assets/f4d73977-c89a-48d1-8f81-8094f66f7fff" />
<img width="1888" height="396" alt="Apdex" src="https://github.com/user-attachments/assets/6ffe137a-73c9-4c80-84cc-390bb1a02b34" />
<img width="1888" height="542" alt="Hits_per_Second" src="https://github.com/user-attachments/assets/8c27ce23-249d-4f83-8047-7afbf212d1bd" />
<img width="1888" height="533" alt="Response_time_over_Time" src="https://github.com/user-attachments/assets/9f4547a8-9e31-45a9-97c2-94c44d734331" />

## View Results
Open dashboard/index.html in your browser to explore: <br>
✅ Throughput <br>
✅ Response Times <br>
✅ Error Rates <br>
✅ APDEX Scores <br>

## Test Plan Details
- Thread Group: 10 threads, 10s ramp-up, 300s total duration
## HTTP Requests
- POST /auth – uses CSV data for username/password
- Extracts token using JSON Extractor
- Subsequent booking operations use token-based auth
- Includes assertions for response codes (e.g., 200, 201)

## Notes
The plan reuses tokens for endpoints needing auth (PUT, PATCH, DELETE)
> The JMeter HTML dashboard provides deep insights via:
- Dashboard
- Charts
- Custom Graphs
> Ensure the users.csv path in the test plan is correctly configured
> Metrics like throughput, response time, error rate, and APDEX score are in the generated index.html


## Author
AMAN BHUIYAN <br>
[[LinkedIn Profile] ](https://www.linkedin.com/in/bhuiyanaman71/) <br>
[bhuiyanaman71@gmail.com]
