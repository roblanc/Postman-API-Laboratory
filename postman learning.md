# Postman Learning Journey

## Section 1: Getting Started with Postman

### 1.1 Installation and Setup
- Downloaded and installed Postman Desktop App.
- Created a Postman account and logged in.
- Familiarized with the basic UI: sidebar, request builder, response viewer.

### 1.2 Making Your First Request
- **HTTP Method**: GET
- **URL**: `https://api.publicapis.org/entries`
- Sent the request and observed the JSON response.
- Understood status codes (e.g., 200 OK).

### 1.3 Understanding API Responses
- Explored different parts of the response: Body, Headers, Cookies.
- Learned about JSON format and how to navigate it.

## Section 2: Organizing Your Work

### 2.1 Collections
- Created a new collection named "Public APIs Exploration".
- Saved the "Get All Entries" request into this collection.
- Learned about folders within collections for better organization.

### 2.2 Environments and Variables
- Created an environment named "Development".
- Added an environment variable `baseUrl` with value `https://api.publicapis.org`.
- Modified the "Get All Entries" request to use `{{baseUrl}}/entries`.
- Understood the difference between environment, collection, and global variables.

## Section 3: Advanced Request Features

### 3.1 Query Parameters
- Added a query parameter `title=cat` to `{{baseUrl}}/entries` to filter results.
- Observed how the URL changes and the response is filtered.

### 3.2 Headers
- Added a custom header `X-My-Custom-Header: Postman-Learner`.
- Understood the purpose of common headers like `Content-Type`, `Authorization`.

### 3.3 Request Body (POST, PUT)
- **Goal**: Learn to send data in the request body.
- **Method**: POST
- **URL**: `https://jsonplaceholder.typicode.com/posts`
- **Body Type**: `raw` -> `JSON`
- **JSON Body**:
  ```json
  {
    "title": "foo",
    "body": "bar",
    "userId": 1
  }
  ```
- Sent the request and checked the response (e.g., new ID created).

## Section 4: Testing and Automation

### 4.1 Writing Basic Tests
- **Goal**: Add tests to requests to validate responses.
- Opened the "Tests" tab for the "Get All Entries" request.
- Wrote a test to check if the status code is 200.
  ```javascript
  pm.test("Status code is 200", function () {
      pm.response.to.have.status(200);
  });
  ```
- Wrote a test to check if the response body contains a specific string.
  ```javascript
  pm.test("Response body contains 'entries'", function () {
      pm.expect(pm.response.text()).to.include("entries");
  });
  ```
- **Next Step**: Learn to parse JSON response and assert specific values.

### 4.2 Pre-request Scripts
- **Goal**: Understand how to execute code before a request is sent.
- **Next Step**: Add a pre-request script to set a random variable.

### 4.3 Chaining Requests
- **Goal**: Learn to use data from one request in a subsequent request.
- **Next Step**: Create a workflow where the ID from a POST request is used in a GET/PUT/DELETE request.

## Section 5: Collaboration and Advanced Features

### 5.1 Mock Servers
- **Next Step**: Create a mock server for a collection.

### 5.2 Monitors
- **Next Step**: Set up a monitor for a collection.

### 5.3 Integrations
- **Next Step**: Explore Postman integrations with CI/CD tools.

---
