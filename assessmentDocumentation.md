# HTTP Method & URL
**Method:** POST  
**URL:** /assessment

## Headers
- **Content-Type:** application/json - Indicates that the body of the request contains a JSON object.
- **x-api-key:** Use `SFVHRUNPQ0tIVUdFQ09DS0hVR0VDT0NLSFVHRUNPQ0tIVUdFQ09DSw==` for this assessment

## Request Body
The request body must be a JSON object that contains the following fields:

- `country` [string] - The country from which the device is accessing. For example: "United States".
- `device_type` [string] - The type of device being used. For example: "Mobile", "Desktop".
- `browser_type` [string] - The type of browser through which the access occurs. For example: "Chrome", "Firefox".

An example request body would look like this:

```json
{
  "country": "United States",
  "device_type": "Mobile",
  "browser_type": "Chrome"
}
```

## Responses
### Success Response
- **Status Code:** 200 OK
- **Content:**
  ```json
  {
    "success": true,
    "message": "Assessment received and validated successfully."
  }
  ```

### Error Responses
#### Missing Required Fields:
- **Status Code:** 400 Bad Request
- **Content:**
  ```json
  {
    "success": false,
    "message": "Error: Missing required field(s). Please ensure all fields - country, device_type, and browser_type are provided."
  }
  ```

#### Invalid API Key:
- **Status Code:** 401 Unauthorized
- **Content:** Plain Text
  ```
  Invalid API key
  ```

#### Server Error (e.g., issue in processing the request):
- **Status Code:** 500 Internal Server Error
- **Content:** Plain Text
  ```
  An error occurred
  ```
