# AATracking WebAPi's
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
    
    
**Get Vehicles**
----
  Fetch all the vehicles for user

* **URL**

  /api/GetVehicles

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   None

* **Header Params**

  `token=[string]- Received on the authentication api`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `[
    {
        "VEH_ID": 2576,
        "VEH_NAME": "Vespa",
        "VEH_EVENT_LATITUDE": 47.5688016775,
        "VEH_EVENT_LONGITUDE": -79.51928
    },
    {
        "VEH_ID": 4617,
        "VEH_NAME": "Test-HOS",
        "VEH_EVENT_LATITUDE": null,
        "VEH_EVENT_LONGITUDE": null
    }]`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/api/GetVehicles",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```    

**Get Vehicle**
----
  Fetch single vehicle for user by id

* **URL**

  /api/GetVehicles/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   None

* **Header Params**

  `token=[string]- Received on the authentication api`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `[
    {
        "VEH_ID": 2576,
        "VEH_NAME": "Vespa",
        "VEH_EVENT_LATITUDE": 47.5688016775,
        "VEH_EVENT_LONGITUDE": -79.51928
    }
    ]`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/api/GetVehicles/2576",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```    
