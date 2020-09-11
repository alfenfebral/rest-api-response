# rest-api-response
Rest API Response

## Rest API Popular Endpoint Formats

> https://example.com/api/items/v1
> https://example.com/v1/api/items
## Rest API Success Responses

1- GET - Get single item - HTTP Response Code: **200**
```javascript
    HTTP/1.1 200
    Content-Type: application/json

    {
        "success": true,
        "code": 200,
        "message": "Get Item",
        "data": {
            "name": "Item 1"
        }
    }
```
2- GET - Get item list pagination - HTTP Response Code: **200**
```javascript
    HTTP/1.1 200
    perPage: 2
    page: 1
    Content-Type: application/json
    
    {
        "success": true,
        "code": 200,
        "meta": {
            "perPage": 2,
            "page": 1,
            "pageCount" 10,
            "totalCount": 20
        },
        "message": "Get All User",
        "data": [
            {
                "name": "Item 1"
            },
            {
                "name": "Item 2"
            }
        ]
    }
```
3- POST - Create a new item - HTTP Response Code: **201**
```javascript
    HTTP/1.1  201
    Location: /v1/items/12
    Content-Type: application/json
 
    {
        "success": true,
        "code": 201,
        "message": "Create Item",
        "data": {
            "name": "Item 1"
        },
        "message": "The item was created successfully"
    }
```
4- PATCH - Update an item - HTTP Response Code: **200** 

> If updated entity is to be sent after the update

```javascript
    HTTP/1.1  200
    Content-Type: application/json
 
    {
        "success": true,
        "code": 200,
        "message": "Update Item",
        "data": {
            "name": "Item 1"
        }
    }
```
5- DELETE - Delete an item - HTTP Response Code: **200**
```javascript
    HTTP/1.1  200
    Content-Type: application/json
 
    {
        "success": true,
        "code": 200,
        "message": "Delete Item",
        "data": {
            "name": "Item 1"
        },
    }
```

## Rest API Error Responses
1- GET/POST/PATCH/DELETE - HTTP Response Code: **404**

```javascript
    HTTP/1.1  404
    Content-Type: application/json
 
    {
        "success": false,
        "code": 404,
        "data": "",
        "message": "The item does not exist"
    }
```
2- POST/PATCH -  HTTP Response Code: **400**
```javascript
    HTTP/1.1  400
    Content-Type: application/json
    
    {
        "success": false,
        "code": 400,
        "data": "",
        "message": "Validation errors in your request", /* skip or optional error message */
        "errors": {
            "name": "Name can't be blank"
        }
    }
```
3- VERB Unauthorized - HTTP Response Code: **401**
```javascript
    HTTP/1.1  401
    Content-Type: application/json
 
    {
        "success": false,
        "code": 401,
        "data": "",
        "message": "Authentication credentials were missing or incorrect"
    }
```
4- VERB Forbidden - HTTP Response Code: **403**
```javascript
    HTTP/1.1  403
    Content-Type: application/json
 
    {
        "success": false,
        "code": 403,
        "data": "",
        "message": "The request is understood, but it has been refused or access is not allowed"
    }
```
5- VERB Conflict - HTTP Response Code: **409**
```javascript
    HTTP/1.1  409
    Content-Type: application/json
 
    {
        "success": false,
        "code": 409,
        "data": "".
        "message": "Any message which should help the user to resolve the conflict"
    }
```
6- VERB Too Many Requests - HTTP Response Code: **429**
```javascript
    HTTP/1.1  429
    Content-Type: application/json
 
    {
        "success": false,
        "code": 429,
        "data": "".
        "message": "The request cannot be served due to the rate limit having been exhausted for the resource"
    }
```
7- VERB Internal Server Error - HTTP Response Code: **500**
```javascript
    HTTP/1.1  500
    Content-Type: application/json
 
    {
        "success": false,
        "code": 500,
        "data": "",
        "message": "Something is broken"
    }
```
8- VERB Service Unavailable - HTTP Response Code: **503**
```javascript
    HTTP/1.1  503
    Content-Type: application/json
 
    {
        "success": false,
        "code": 503,
        "data": "".
        "message": "The server is up, but overloaded with requests. Try again later!"
    }
```
