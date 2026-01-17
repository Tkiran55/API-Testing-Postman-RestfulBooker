# Bug Reports - Restful-Booker API

## Bug #1: Server Error on Missing Required Field

**Bug ID:** BUG-001  
**Test Case:** TC_007  
**Severity:** High  
**Priority:** High  
**Status:** Open  

### Description
API returns 500 Internal Server Error when creating a booking without the `firstname` field instead of proper validation error.

### Steps to Reproduce
1. Send POST request to `/booking`
2. Include all fields EXCEPT `firstname` in request body
3. Observe response

### Expected Result
- Status Code: `400 Bad Request`
- Response: Validation error message indicating firstname is required

### Actual Result
- Status Code: `500 Internal Server Error`
- Response: "Internal Server Error"

---

## Bug #2: API Accepts Negative Price

**Bug ID:** BUG-002  
**Test Case:** TC_010  
**Severity:** Medium  
**Priority:** Medium  
**Status:** Open  

### Description
API accepts negative values for `totalprice` field without validation.

### Steps to Reproduce
1. Send POST request to `/booking`
2. Set `totalprice` to `-111`
3. Observe response

### Expected Result
- Status Code: `400 Bad Request`
- Response: Validation error for invalid price

### Actual Result
- Status Code: `200 OK`
- Booking created successfully with negative price

---

## Bug #3: Incorrect Status Code for Invalid Resource ID

**Bug ID:** BUG-003  
**Test Cases:** TC_009, TC_015  
**Severity:** Low  
**Priority:** Low  
**Status:** Open  

### Description
API returns `405 Method Not Allowed` instead of `404 Not Found` when attempting to update/delete a non-existent booking ID.

### Steps to Reproduce
1. Send DELETE or PUT request to `/booking/99999` (non-existent ID)
2. Include valid authentication token
3. Observe response

### Expected Result
- Status Code: `404 Not Found`
- Response: Resource not found message

### Actual Result
- Status Code: `405 Method Not Allowed`
- Response: "Method Not Allowed"

---

## Bug #4: Invalid Date Format Auto-Corrected

**Bug ID:** BUG-004  
**Test Case:** TC_013  
**Severity:** Low  
**Priority:** Low  
**Status:** Open  

### Description
API accepts invalid date format (`DD-MM-YYYY`) and auto-corrects it to `YYYY-MM-DD` instead of rejecting the request.

### Steps to Reproduce
1. Send POST request to `/booking`
2. Set checkin date as `"01-01-2024"` (DD-MM-YYYY format)
3. Observe response

### Expected Result
- Status Code: `400 Bad Request`
- Response: Date format validation error

### Actual Result
- Status Code: `200 OK`
- Date automatically converted to correct format

---

## Summary

| Bug ID  | Severity | Priority | Test Case | Status |
|---------|----------|----------|-----------|--------|
| BUG-001 | High     | High     | TC_007    | Open   |
| BUG-002 | Medium   | Medium   | TC_010    | Open   |
| BUG-003 | Low      | Low      | TC_009/015| Open   |
| BUG-004 | Low      | Low      | TC_013    | Open   |

**Total Bugs Found:** 4  
**Critical/High:** 1  
**Medium:** 1  
**Low:** 2
