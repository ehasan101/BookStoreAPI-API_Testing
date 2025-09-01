

# API_Testing-Project
<br>

## API Testing: Book Store API with Postman
The Book Store API allows users to manage user accounts and book collections. This Postman project automates the testing of its core functionalities, including user creation, token generation, and CRUD (Create, Read, Update, Delete) operations for books.
The testing process involves sending HTTP requests to various endpoints and using Postman's scripting capabilities to assert that the API responses are correct. It's evaluating the APIs are working functionality and usability as expected. 


## How to run this project!
1. Install [Postman](https://www.postman.com/).
2. Install [Node.js](https://nodejs.org/en/).
3. Download [Project file](https://drive.google.com/drive/folders/1hCYHS0JpTDOfTgHciJg2AcSoSOjlgw5D?usp=drive_link).
4. Now Import collection & environment file into Postman: \
`file > import > choose the method > press 'import'`
5. Run Desired API request.

Run on cmd
1. Open cmd on project folder or move to project folder `cd Downloads/project_file`
2. Run the follwing command 
Install newman `npm install -g newman`
3. Now 
`newman run "Book Store API.postman_collection.json" -e BookStoreAPI.postman_environment.json`
4. **If want to export test results** \
   first install them \
   `npm install -g newman-reporter-html` \
 and `npm install -g newman-reporter-htmlextra`
6. Now run follwing command for report \
`newman run "Book Store API.postman_collection.json" -e BookStoreAPI.postman_environment.json -r cli,htmlextra`

## HTTP Status Codes
HTTP status code are 3 digit number which a server response to a browser’s request.
Those are divided into 5 categories.
```ruby
1xx - Informational Purpose
2xx - Success
3xx - Redirection
4xx - Client Errors
5xx - Server Errors
```
![http_status_code](https://drive.google.com/uc?export=view&id=1iwy6FJw2krnOtpOmMhhHocFpXgfguTBM)


## Working Scenarios & What I have done in this Testing!
This project is designed to test the complete user and book management lifecycle. The requests are structured to run in a specific sequence, allowing for a comprehensive end-to-end test scenario.
The collection simulates a real user's journey through the application:
* User Registration: A new user account is created using the POST /Account/v1/User endpoint.
* Authentication: A POST /Account/v1/GenerateToken request is sent to get an authentication token for the newly created user.
* Book Management: The token and userId are then used to perform a series of book-related operations:
   * Add a book to the user's collection (POST /BookStore/v1/Books).
   * Update a book in the collection (PUT /BookStore/v1/Books/{ISBN}).
   * Delete a book from the collection (DELETE /BookStore/v1/Book).
* Data Cleanup: Finally, the DELETE /Account/v1/User/{UUID} request is called to remove the user account, ensuring that the test environment is left clean after the run.

**Essential Testing Strategies:**
* Dynamic Data Chaining: I wrote scripts in the "Tests" tab to dynamically handle data flow between requests. The userID from the "Create User" response and the Token from the "Generate Token" response are automatically captured and saved as environment variables. These variables are then used in the headers and bodies of subsequent requests, creating a seamless and automated test flow.
* Bearer Token Authentication: I configured the collection to use Bearer Token authentication, automatically including the captured Token in the authorization headers for protected endpoints.
* Comprehensive Assertions: For each API request, I implemented multiple tests to validate the correctness of the response. These tests include:
* Status Code Verification: Checking for expected HTTP status codes (e.g., 201 Created, 200 OK, 204 No Content).
* Response Time: Ensuring the API responds within an acceptable performance threshold (e.g., under 1000ms).
* Response Body Validation: Verifying that the JSON response body contains the correct data, such as matching the username and userID after user creation.


## Test Report with Newman :
A Newman report has been generated for the API test
1. HTML [Report Link](https://drive.google.com/file/d/1794W1L0uiT9apGCwAq2MdxYEkj3KhbaZ/view?usp=drive_link)

2. Snapshots:
> * *Summary Report*
![Summary_1](https://drive.google.com/uc?export=view&id=14HdYjkfEaPRc_rqHAoBOZUacDZyUQg6V)
![Summary-2](https://drive.google.com/uc?export=view&id=1skl2J-Z9jh3ewYNUh96nWixJ51w6MhwB)

> * *Total Requests*
![Total](https://drive.google.com/uc?export=view&id=1LHt450wfD8k6KhoX8Dqu-639RffVdvuG)


> * *Failed Requests*
![Failed](https://drive.google.com/uc?export=view&id=1nkKnx_Oct2FuAL52KhIcdS77fz3Cnkw-)

---
|:warning: **if you face any type of image broken/missing issue, please `refresh` this web page again.**|
| --- |

### **#Happy_Testing**
---

