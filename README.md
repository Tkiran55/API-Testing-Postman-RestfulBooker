
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
