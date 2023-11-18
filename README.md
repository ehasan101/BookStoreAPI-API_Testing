

# API_Testing-Project
<br>

## API Testing for Book Store API with Postman
This project is on API testing with Postman for the Book Store API web-service. It's evaluating the APIs are working functionality and usability as expected. 

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
```
1xx - Informational Purpose
2xx - Success
3xx - Redirection
4xx - Client Errors
5xx - Server Errors
```
![http_status_code](https://drive.google.com/uc?export=view&id=1iwy6FJw2krnOtpOmMhhHocFpXgfguTBM)


## Working Scenarios & What I have done in this Testing!
* Accounts
  - Create User [POST method]
  - Generate Token [POST method]
  - Authorized [POST method]
* BookStoreManagement
  - Book Assign to user [POST method]
  - Update Book [PUT method]
  - Get Current Book [GET method]
* Get User-Book [GET method]
* Delete Book [DEL method]
* Delete User [DEL method] \
_[Positive and Negative case both are created]_


<!-- 
## Test Cases for this Testing:
`incomplete` 
-->

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
**[ Attention ] \
if you face any type of image broken/missing issue, please `refresh` this web page again.**

### **#Happy_Testing**
---

