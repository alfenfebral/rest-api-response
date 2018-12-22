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
        "status": 'success',
        "code": "200",
        "data": {
            "name": "John Doe"
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
        "status": 'success',
        "code": "200",
        "meta": {
            "current_page": 1,
            "per_page": 2,
            "total_page" 10,
        },
        "data": [
            {
                "name": "John Doe"
            },
            {
                "name": "John Smith"
            }
        ]
    }
```
