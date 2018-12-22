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
        "id": 10,
        "name": "shirt",
        "color": "red",
        "price": "$23"
    }
```
