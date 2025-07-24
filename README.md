# API Performance Testing with Apache JMeter

## Overview
This project demonstrates performance testing of the **Restful Booker API** using **Apache JMeter**. The goal was to evaluate the API's performance under load, analyzing metrics like throughput, response times, and error rates. The test results are visualized in a JMeter HTML dashboard.

## Test Details
- **API Tested**: Restful Booker (a mock hotel booking REST API)
- **Endpoints Tested**: `/booking`, `/auth`, `/booking/{id}` (GET, POST, PUT, DELETE)
- **Test Configuration**:
  - 50 concurrent users
  - 5-minute test duration
  - Ramp-up period: 10 seconds
- **Key Metrics**:
  - Throughput: 100 requests/sec
  - Average Response Time: 200ms
  - Error Rate: 0.5%
  - APDEX Score: 0.95 (Satisfactory)

## Repository Contents
- `RestfulBooker.jmx`: JMeter test plan
- `RestfulBooker.jtl`: Raw test results
- `dashboard/`: HTML dashboard report
- `screenshots/`: Visuals of key metrics

## How to Run
1. Install [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi) and Java.
2. Run the test: `jmeter -n -t RestfulBooker.jmx -l RestfulBooker.jtl -e -o dashboard`
3. Run the test: `jmeter -g report/RestfulBooker.jtl -o report/RestfulBooker.html` for creating HTML file
4. Open `dashboard/index.html` in a browser to view the report.

## Screenshots
(<img width="1600" height="465" alt="Top_5_Errors" src="https://github.com/user-attachments/assets/4d0fba67-a037-47c7-b15b-d54cca276c78" />
<img width="1626" height="418" alt="Statistics" src="https://github.com/user-attachments/assets/996f8aa8-471d-456f-a3f4-245889a2d391" />
<img width="1656" height="567" alt="Response_over_TIme" src="https://github.com/user-attachments/assets/6957ddea-24ad-446e-9a71-b30441e3a907" />
<img width="1659" height="727" alt="Request Summery" src="https://github.com/user-attachments/assets/934c4034-ba64-438d-a106-4c3bdff926f2" />
<img width="1643" height="542" alt="Hits_per_second" src="https://github.com/user-attachments/assets/323a99cd-e7ac-4b6a-8721-00e59157a117" />
<img width="1606" height="352" alt="Errors" src="https://github.com/user-attachments/assets/bb08824a-c2e4-4554-ba10-b306aeb3393f" />

## Technologies Used
- Apache JMeter
- REST API
- HTML, Bootstrap, JavaScript (for dashboard)

## Learnings
- Configured JMeter thread groups and samplers for API testing.
- Analyzed performance metrics like APDEX and throughput.
- Identified and resolved bottlenecks in API endpoints.

## Future Improvements
- Test additional APIs for comparison.
- Automate test execution with CI/CD (e.g., GitHub Actions).
- Add custom JMeter plugins for enhanced reporting.

## Author
AMAN BHUIYAN <br>
[[LinkedIn Profile] ](https://www.linkedin.com/in/bhuiyanaman71/) <br>
[bhuiyanaman71@gmail.com]
