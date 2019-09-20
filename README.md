# AAtracking WebAPis
**Authenticate**
----

* **Server URL**

  /api/Authenticate

* **Method:**
  
  `POST`
*  **URL Params**

* **Data Params**

   `username=[string]`
   `password=[string]`

* **Success Response:**
  
  * **Code:** 200 <br />
    **Content:** `{
    "ID": _userid[integer],
    "UserName": "_username",
    "Password": null,
    "Company": "_companyname",
    "CompanyID": _companyid[integer],
    "Email": "_email[string]",
    "PIN": "_pin"[string],
    "ServiceURL": "_serviceurl[string]",
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE1Njg5MjQ4MjgsInVzZXIiOnsiSUQiOjgzMiwiVXNlck5hbWUiOiJ0ZWphcyIsIlBhc3N3b3JkIjpudWxsLCJDb21wYW55IjoiSHVwYSBBY2NvdW50IiwiQ29tcGFueUlEIjoxNTEsIkVtYWlsIjoidGVqYXNAYWF0cmFja2luZy5jb20iLCJQSU4iOiI4MzIiLCJTZXJ2aWNlVVJMIjoiaHR0cDovL3d3dy5hYXRyYWNraW5nLmNvbTo4MDgwL1NlcnZpY2UxLmFzbXgiLCJ0b2tlbiI6bnVsbH19.Sr3eMxEu4WZv5et50Jck0DFnhnfruJeWJ0oL-rvSPwk"
}`
 
* **Error Response:**

  * **Code:** 400 BADREQUEST <br />
    **Content:** `{ error : "Cannot process the request" }`
