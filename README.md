### Automated-The-Testing-World-Api-Testing-(API-Testing-Exam)-with-Newman-Report

This project showcases API testing with Postman, featuring a comprehensive set of tests to ensure the accuracy and reliability of different API endpoints.

Project: API-Testing-Exam 

### **Features**

- Tests for GET, POST, PUT, DELETE requests
- Collection of tests covering different API endpoints
- Environment setup for easy switching between environments
- Pre-request scripts for data setup
- Test scripts for assertions and validations

## API Documentation:
https://documenter.getpostman.com/view/37041522/2sAXjSxoFh

### **Technology used:**

- Postman
- Newman

### **Prerequisite:**
- Node Js
- Newman
- Newman Html Report Library

## Installation

1. Postman: If you haven't already, [download and install Postman.](https://www.postman.com/downloads/)
2. Clone the repository:

```bash
 git clone https://github.com/md-abutalha/Automated-REST-Booking-API-Testing-with-Newman-Report.git
```
3. Import the Postman collection:
- Open Postman.
- Click on the Import button.
- Select the file from the repository.
4. Import the Postman environment:
- In Postman, click on the gear icon in the top right corner.
- Select **Import** and choose the file.
5. Newman and Report Installation Process:
- Newman Install Command:  
```bash
 npm install -g newman
```
- Newman Html Report Install Command:
```bash
 npm install -g newman-reporter-htmlextra
```

### **Usage**
1. Select Environment:
    -   In Postman, select the appropriate environment (e.g., Development, Production) from the top-right dropdown.
3. Run Collection:
    -   Select the imported collection from the Collections sidebar.
    -   Click on the Runner button to open the collection runner.
    -   Select the desired environment.
    -   Click Start Test to run the collection.
8. View Results:
 -   Once the tests are complete, view the results in the Runner tab.
- Detailed test results can be viewed for each request.

## **Testing**
## **URL:{{baseUrl}}** 
https://thetestingworldapi.com
## Test Case Scenarios:

## _**1. Retrieve Students from server**_

### Request URL: {{baseUrl}}/api/studentsDetails

### Request Method: GET
### Post-request Script:

```javascript
pm.test("Status Code is 200", function () {
    pm.response.to.have.status(200);  // Check if the status code is 200
});

// Test Case for Checking the Length of the Response

var responseData = pm.response.json();
pm.test("Response length is greater than 0", function () {
    pm.expect(responseData.length).to.be.above(0);
});

pm.test("Verify Content-Length", function () {
    pm.expect(pm.response.headers.get('Content-Length')).to.exist;
});

```
 **Response Body:**

```javascript
[
    {
        "id": 10389120,
        "first_name": "Eyasen",
        "middle_name": "Chowdhury",
        "last_name": "Shaon",
        "date_of_birth": "11/30/1993"
    },
    {
        "id": 10389119,
        "first_name": "Eyasen",
        "middle_name": "Chowdhury",
        "last_name": "Shaon",
        "date_of_birth": "11/30/1993"
    },
    {
        "id": 10389118,
        "first_name": "Eyasen",
        "middle_name": "Chowdhury",
        "last_name": "Shaon",
        "date_of_birth": "11/30/1993"
    },
    {
        "id": 10389117,
        "first_name": "Eyasen",
        "middle_name": "Chowdhury",
        "last_name": "Shaon",
        "date_of_birth": "11/30/1993"
    },
    
    {
        "id": 10389097,
        "first_name": "sample string 2",
        "middle_name": "sample string 3",
        "last_name": "sample string 4",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389096,
        "first_name": "Anna",
        "middle_name": "Banana",
        "last_name": "null",
        "date_of_birth": "12/23/1990"
    },
   
    {
        "id": 10389091,
        "first_name": "Keshawn",
        "middle_name": "Stephany",
        "last_name": "Metz",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389090,
        "first_name": "Rashad",
        "middle_name": "Malika",
        "last_name": "Volkman",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389089,
        "first_name": "Spencer",
        "middle_name": "Madeline",
        "last_name": "Parker",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389088,
        "first_name": "Lourdes",
        "middle_name": "Angelica",
        "last_name": "Glover",
        "date_of_birth": "sample string 5"
    },
    
    {
        "id": 10389077,
        "first_name": "sample string 2",
        "middle_name": "sample string 3",
        "last_name": "sample string 4",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389075,
        "first_name": "sample string 2",
        "middle_name": "sample string 3",
        "last_name": "sample string 4",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389074,
        "first_name": "Noor",
        "middle_name": "E",
        "last_name": "Lamia",
        "date_of_birth": "1999-02-07"
    },
    {
        "id": 10389073,
        "first_name": "sample string 2",
        "middle_name": "sample string 3",
        "last_name": "sample string 4",
        "date_of_birth": "sample string 5"
    },
    {
        "id": 10389072,
        "first_name": "Noor",
        "middle_name": "E",
        "last_name": "Lamia",
        "date_of_birth": "1999-02-07"
    },
    {
        "id": 10389071,
        "first_name": "Miss",
        "middle_name": "Kade",
        "last_name": "Mitchell",
        "date_of_birth": "2024-09-09"
    },
    {
        "id": 10389070,
        "first_name": "Alexandro",
        "middle_name": "Von",
        "last_name": "Waelchi",
        "date_of_birth": "04/03/2004"
    }
]
```
## _**2. Create Students Details **_
### Request URL:
{{baseUrl}}/api/studentsDetails
### Request Method: POST
### Request Body:
```javascript
{
  "first_name": "{{first_name}}",
  "middle_name": "{{middle_name}}",
  "last_name": "{{last_name}}",
  "date_of_birth": "{{date}}"
}

```
### Pre-Test Script:
```javascript
var firstname = pm.variables.replaceIn("{{$randomFirstName}}");
pm.environment.set("first_name", firstname);

var middlename = pm.variables.replaceIn("{{$randomLastName}}")
pm.environment.set("middle_name", middlename);

var lastname = pm.variables.replaceIn("{{$randomLastName}}");
pm.environment.set("last_name", lastname);

const moment = require('moment');
const today= moment();
console.log(today.format("YYYY-MM-DD"));
pm.environment.set("date",today.format("YYYY-MM-DD"));
```
### Post-Test Script:
```javascript
pm.test("Status Code is 201", function () {
    pm.response.to.have.status(201);  // Check if the status code is 200
});
var jsonData = pm.response.json();

pm.environment.set("id", jsonData.id);
```
### Response Body:
```javascript
pm.test("Status Code is 201", function () {
    pm.response.to.have.status(201);  // Check if the status code is 200
});
var jsonData = pm.response.json();

pm.environment.set("id", jsonData.id);
```
## _**3. Get Specific Student By ID.**_
### Request URL: 
{{baseUrl}}/api/studentsDetails/{{id}}
### Request Method: GET
### Pre-request Script: None
### Post-Request Script:
```javascript
// Parse the response body to JSON format
var jsonData = pm.response.json();

// Verify the status code is 200
pm.test("Verify the status code is 200", function () {
    pm.response.to.have.status(200);
});

// Retrieve expected values from environment variables
var expectedId = pm.environment.get("id");
var expectedFirstName = pm.environment.get("first_name");
var expectedMiddleName = pm.environment.get("middle_name");
var expectedLastName = pm.environment.get("last_name");
var expectedDateOfBirth = pm.environment.get("date");

// Validate ID
pm.test("ID validation", function(){
    pm.expect(jsonData.data.id).to.eql(expectedId);  // Convert id to string if needed
});

// Validate First Name
pm.test("First Name validation", function(){
    pm.expect(jsonData.data.first_name).to.eql(expectedFirstName);
});

// Validate Middle Name
pm.test("Middle Name validation", function(){
    pm.expect(jsonData.data.middle_name).to.eql(expectedMiddleName);
});

// Validate Last Name
pm.test("Last Name validation", function(){
    pm.expect(jsonData.data.last_name).to.eql(expectedLastName);
});

// Validate Date of Birth
pm.test("Date of Birth validation", function(){
    pm.expect(jsonData.data.date_of_birth).to.eql(expectedDateOfBirth);
});

```
### Response:
```javascript
{
    "status": "true",
    "data": {
        "id": 10389171,
        "first_name": "Donnell",
        "middle_name": "Corwin",
        "last_name": "Pfeffer",
        "date_of_birth": "2024-09-09"
    }
}
```
## _**4. Create Technical Skills**_
### Request URL: {{baseUrl}}/api/technicalskills
### Request Method: POST
### Pre-request Script:
```javascript
var language = pm.variables.replaceIn("{{$randomLocale}}");
pm.environment.set("expected_languages", language);

var year = pm.variables.replaceIn("{{$randomLocale}}");
pm.environment.set("expected_yearexp", year);

var lastusdt = pm.variables.replaceIn("{{$randomUUID}}");
pm.environment.set("expected_usdt", lastusdt);
```

### Post-request Script:
```javascript
pm.test("validate Status code", function() {
pm.response.to.have.status(200);
});
```

### Response:
```javascript
{
    "status": "true",
    "msg": "Add  data success"
}
```
## _**5. Create Student Address**_
### Request URL: {{baseUrl}}/api/addresses
### Request Method: POST
### Body:
```javascript
{
  "Permanent_Address": {
    "House_Number": "{{houseNumber}}",
    "City": "{{city}}",
    "State": "{{street}}",
    "Country": "{{country}}",
    "PhoneNumber": [
      {
        "Std_Code": "001",
        "Home": "123456",
        "Mobile": "9876543210"
      },
      {
        "Std_Code": "002",
        "Home": "654321",
        "Mobile": "{{mobile}}"
      }
    ]
  },
  "stId": {{id}}
}

```

### Pre-request Script:
```javascript
var houseNumber = pm.variables.replaceIn("{{$randomInt}}");
pm.environment.set("houseNumber", houseNumber);

var city = pm.variables.replaceIn("{{$randomCity}}");
pm.environment.set("city", city);

var street = pm.variables.replaceIn("{{$randomStreetName}}");
pm.environment.set("street", street);

var country = pm.variables.replaceIn("{{$randomCountry}}");
pm.environment.set("country", country);

var mobile = pm.variables.replaceIn("{{$randomPhoneNumber}}");
pm.environment.set("mobile", mobile);
```
### Post-request Script:
```javascript
pm.test("Verify the status code is 200", function () {
    pm.response.to.have.status(200);
});

var jsonData = pm.response.json();
pm.test("Status Field Value Validation", function(){
pm.expect(jsonData.status).to.eql("true");
});

pm.test("Message Field Value Validation", function(){
pm.expect(jsonData.msg).to.eql("Add  data success");
});
```

### Response-Body:
```javascript
{
    "status": "true",
    "msg": "Add  data success"
}
```
## _**6. FINAL STUDENT DETAILS**_
### Request URL: {{baseUrl}}/api/FinalStudentDetails/{{id}}
### Request Method: GET
### Post-Script:
```javascript
pm.test("Status Code Validation", function () {
    pm.response.to.have.status(200);
});

// Get environment variables
var expectedMiddleName = pm.environment.get("middle_name");
var expectedLastName = pm.environment.get("last_name");
var expectedDateOfBirth = pm.environment.get("date");
var expectedLanguages = pm.environment.get("expected_languages").split(","); 
var expectedYearExp = pm.environment.get("expected_yearexp");
var expectedHouseNumber = pm.environment.get("houseNumber");
var expectedCity = pm.environment.get("city");
var expectedCountry = pm.environment.get("country");
var expectedMobile = pm.environment.get("mobile");

// Parse response JSON
var jsonData = pm.response.json();

// Validate middle_name, last_name, date_of_birth
pm.test("Validate middle_name, last_name, and date_of_birth", function () {
    pm.expect(jsonData.data.middle_name).to.eql(expectedMiddleName);
    pm.expect(jsonData.data.last_name).to.eql(expectedLastName);
    pm.expect(jsonData.data.date_of_birth).to.eql(expectedDateOfBirth);
});

// Validate languages and year of experience
pm.test("Validate languages and year of experience", function () {
    var technicalDetails = jsonData.data.TechnicalDetails[0]; 
    pm.expect(technicalDetails.language[0]).to.eql(expectedLanguages[0]);
    pm.expect(technicalDetails.yearexp).to.eql(expectedYearExp);
});


// Validate Permanent_Address details
pm.test("Validate House Number, City, Country, and Mobile", function () {
    var address = jsonData.data.Address[0].Permanent_Address; 
    pm.expect(address.House_Number).to.eql(expectedHouseNumber);
    pm.expect(address.City).to.eql(expectedCity);
    pm.expect(address.Country).to.eql(expectedCountry);
    
    // Check Mobile Number
    var mobileNumbers = address.PhoneNumber.map(phone => phone.Mobile);
    pm.expect(mobileNumbers).to.include(expectedMobile); 
});

```
### Response-Body:
```javascript
{
    "status": "true",
    "data": {
        "first_name": "Donnell",
        "middle_name": "Corwin",
        "last_name": "Pfeffer",
        "date_of_birth": "2024-09-09",
        "TechnicalDetails": [
            {
                "id": 798560,
                "language": [
                    "da",
                    "da"
                ],
                "yearexp": "eo",
                "lastused": "1b743cf5-0e09-4b69-9b34-596a3141b2fe",
                "st_id": "10389171"
            }
        ],
        "Address": [
            {
                "Permanent_Address": {
                    "House_Number": "97",
                    "City": "New Angelina",
                    "State": "Shakira Knolls",
                    "Country": "Macedonia",
                    "PhoneNumber": [
                        {
                            "Std_Code": "001",
                            "Home": "123456",
                            "Mobile": "9876543210"
                        },
                        {
                            "Std_Code": "002",
                            "Home": "654321",
                            "Mobile": "243-251-0406"
                        }
                    ]
                },
                "Current_Address": null,
                "stId": "10389171"
            }
        ]
    }
}
```

## _**Summary of This Project**

The Automated-The-Testing-World-API-Testing (API-Testing-Exam) with Newman Report project demonstrates API testing using Postman and Newman, covering various endpoints with GET, POST, PUT, and DELETE requests. The tests validate API responses, status codes, and data fields across different scenarios like retrieving student details, and creating student profiles, technical skills, and addresses. It includes environment setup, pre-request scripts for dynamic data, and detailed test reports generated using Newman. The project is designed for seamless environment switching and comprehensive API validation. Full API documentation is available here.


## Authors

- [@abutalha](https://github.com/md-abutalha)


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://github.com/md-abutalha)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abu-talha1/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://x.com/abu_talha0x)
