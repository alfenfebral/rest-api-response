# rest-api-response
Rest API Response

## Rest API Popular Endpoint Formats

> https://example.com/api/v1/items

## Rest API Success Responses

1- GET - Get single item - HTTP Response Code: **200**
```javascript
    HTTP/1.1 200
    Content-Type: application/json

    {
        "status": "success",
        "code": "200",
        "data": {
            "name": "Item 1"
        }
    }
```
2- GET - Get item list pagination - HTTP Response Code: **200**
```javascript
    HTTP/1.1 200
    per_page: 2
    page: 1
    Content-Type: application/json
    
    {
        "status": "success",
        "code": "200",
        "meta": {
            "per_page": 2,
            "page": 1,
            "page_count" 10,
            "total_count": 20
        },
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
        "status": "success",
        "code": "201",
        "message": "The item was created successfully"
    }
```
4- PATCH - Update an item - HTTP Response Code: **200** 

> If updated entity is to be sent after the update

```javascript
    HTTP/1.1  200
    Content-Type: application/json
 
    {
        "status": "success",
        "code": "200",
        "message": "The item was updated successfully"
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
        "status": "success",
        "code": "200",
        "message": "The item was deleted successfully"
    }
```

## Rest API Error Responses
1- GET/DELETE - HTTP Response Code: **404**

```javascript
    HTTP/1.1  404
    Content-Type: application/json
 
    {
        "status": "fail",
        "code": "200",
        "message": "The item does not exist"
    }
```
2- POST -  HTTP Response Code: **400**
```javascript
    HTTP/1.1  400
    Content-Type: application/json
    
    {
        "message": "Validation errors in your request", /* skip or optional error message */
        "errors": [
            {
                "message": "Oops! The value is invalid",
                "code": 34,
                "field": "email"
            },
            {
                "message": "Oops! The format is not correct",
                "code": 35,
                "field": "phoneNumber"
            }
        ]
    }
```
