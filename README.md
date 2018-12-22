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
4- PATCH - Update an item - HTTP Response Code: **200/204** 

> If updated entity is to be sent after the update

```javascript
    HTTP/1.1  200
    Content-Type: application/json
 
    {
        "status": "success",
        "code": "200",
        "data": {
            "name": "Item 1"
        }
    }
```
