# Test Cases Specification - JSONPlaceholder

## TC_001: Verify retrieving all posts (GET)
* **Preconditions:** The API service is running and available.
* **Steps:**
1. Send a "GET" request to "https://jsonplaceholder.typicode.com/posts".
* **Expected Result:**
1. Response status code is "200 OK". 
2. Response body contains an array of posts. 
3. Each post item has fields: "userId", "id", "title" and "body".

## TC_002: Verify retrieving an existing post ID (GET)
* **Preconditions:** The API service is running and available.
* **Steps:**
1. Send a "GET" request to "https://jsonplaceholder.typicode.com/posts/1".
* **Expected Result:**
1. Response status code is "200 OK". 
2. Response body contains an object with keys: "userId", "id", "title" and "body". 
3. The value of the "id" field is exactly "1".

## TC_003: Verify retrieving a non-existing post by ID (GET - Negative)
* **Preconditions:** The API service is running and available.
* **Steps:**
1. Send a "GET" request to "https://jsonplaceholder.typicode.com/posts/9999".
* **Expected Result:**
1. Response status code is "404 Not Found".

## TC_004: Verify retrieving a post with invalid ID format (GET - Negative)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "GET" request to "https://jsonplaceholder.typicode.com/posts/abc".
* **Expected Result:**
1. Response status code is "404 Not Found".

## TC_005: Verify creating a new post with valid data (POST)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "POST" request to "https://jsonplaceholder.typicode.com/posts". 
2. Include the following JSON payload in the request body:
```json
{
	"title": "New Test POST",
	"body": "This is a test post body.",
	"userId": 1
}
```
* **Expected Result:**
1. Response status code is "201 Created". 
2. Response body contains the created object with "title", "body", and "userId". 
3. The response contains an automatically assigned "id" (e.g., "101").

## TC_006: Verify creating a new post with empty data (POST - Negative)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "POST" request to "https://jsonplaceholder.typicode.com/posts". 
2. Include an empty JSON payload "{}" in the request body.
* **Expected Result:**
<!-- In a commercial environment, a 400 Bad Request error would be expected here, but for this specific case, I adapt the test to match the behavior of this test application. -->
1. Response status code is "201 Created". 
2. Response body contains an object with an automatically assigned "id".
3. Response body contains undefined fields: "body", "title" and "userId".

## TC_007: Verify updating an existing post entirely (PUT)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "PUT" request to "https://jsonplaceholder.typicode.com/posts/1". 
2. Include the updated JSON payload in the request body:
```json
{
  "id": 1,
  "title": "Updated Title",
  "body": "Updated body",
  "userId": 1
}
```
* **Expected Result:**
1. Response status code is "200 OK".
2. Response body reflects the updated values for "title" and "body".

## TC_008: Verify updating an existing post partially (PATCH)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "PATCH" request to "https://jsonplaceholder.typicode.com/posts/1". 
2. Include a partial JSON payload in the request body:
```json
{
  "title": "Partially Updated Title"
}
```
* **Expected Result:**
1. Response status code is "200 OK".
2. The "title" field is updated, while original fields "body" and "userId" remain unchanged.

## TC_009: Verify deleting an existing post (DELETE)
* **Preconditions:** The API service is running and available. 
* **Steps:**
1. Send a "DELETE" request to "https://jsonplaceholder.typicode.com/posts/1".
* **Expected Result:**
1. Response status code is "200 OK".
2. Response body is an empty object {}.