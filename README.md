API-toolkit
===========

Opinionated information about RESTful API best practices

Endpoints
=========

Crud matrix
-----------

|Method|`/cars`                                              |`/cars/:id`                                     |
|------|-----------------------------------------------------|------------------------------------------------|
|POST  |`201` Created - Return created car with identifier   |`405` Method not allowed - Return `Allow` header|
|GET   |`200` Ok - Return all cars                           |`200` Ok - Return single car                    |
|PUT   |`200` Ok - Bulk update and return all cars           |`200` Ok - Update and return single car         |
|PATCH |`200` Ok - Bulk partial update and return all cars   |`200` Ok - Partial update and return single car |
|DELETE|`204` No content - Delete all cars and return nothing|`204` No content - Delete car and return nothing|

Usefull status codes
--------------------

|Code                       |Description                       |Body                                                |
|---------------------------|----------------------------------|----------------------------------------------------|
|`404` Not found            |Resource or endpoint not found    |_Nothing_                                           |
|`403` Bad request          |Bad request body		               |Explain the problem                                 |
|`422` Unprocessable entity |Validation error		               |Provide details that can be handled programmatically|
|`500` Internal server error|Unexpected error                  |Error message explaining the error is reported      |
|`501` Not implemented      |Unknown request method            |Error message explaining the method is not supported|
|`503` Service unavailable  |Temporary unable to handle request|Error message explaining a retry is suggested       |


Rules
-----
- Use plural resource names
- Return meaningful status codes
- Use the correct HTTP methods
- Return a useful body
- Always return JSON

