# API-Testing-Postman-RestfulBooker
Comprehensive API testing project using Postman for Restful-Booker API - 15 test cases with automation


# API Testing Project - Restful-Booker

## 📋 Project Overview
Comprehensive API testing project demonstrating functional and automation testing skills using Postman on the Restful-Booker API.

**Tested API:** [Restful-Booker](https://restful-booker.herokuapp.com/)  
**Testing Tool:** Postman  
**Test Cases:** 15  

## 🎯 Test Coverage

### Endpoints Tested
- `GET /booking` - Retrieve all booking IDs
- `GET /booking/:id` - Get specific booking details
- `POST /booking` - Create new booking
- `PUT /booking/:id` - Update booking (requires auth)
- `PATCH /booking/:id` - Partial update (requires auth)
- `DELETE /booking/:id` - Delete booking (requires auth)
- `POST /auth` - Generate authentication token

### Test Types
- ✅ Positive Testing (Happy path scenarios)
- ✅ Negative Testing (Invalid data, missing fields)
- ✅ Authentication Testing
- ✅ Data Validation Testing
- ✅ Boundary Testing

## 🐛 Bugs Found

**Bug #1: Server Error on Missing Required Field**
- **Severity:** High
- **TC_007:** API returns 500 Internal Server Error when firstname is missing
- **Expected:** 400 Bad Request
- **Actual:** 500 Internal Server Error

**Bug #2: Negative Price Accepted**
- **Severity:** Medium
- **TC_010:** API accepts negative totalprice values
- **Expected:** 400 Bad Request with validation error
- **Actual:** 200 OK, booking created with negative price

**Bug #3: Incorrect Status Code for Invalid Resource**
- **Severity:** Low
- **TC_009, TC_015:** Returns 405 Method Not Allowed instead of 404 Not Found

---

## 📂 Project Structure
```
├── Restful-Booker-API-Tests.postman_collection.json
├── Test-Cases-Documentation.xlsx
├── Bug-Reports.md
├── Screenshots/
│   ├── collection-runner-results.png
│   └── test-execution-sample.png
└── README.md
```







## 📝 License

This project is for educational and portfolio purposes.
