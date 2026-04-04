Installation & Import

python

```python
# Install the library
pip install requests

# Import it in your Python script
import requests


### Making Requests

You can use shorthand methods for different HTTP actions.

*   **GET:** Retrieve data from a server.

    response = requests.get('https://api.example.com/data')


*   **POST:** Send data to a server (e.g., submitting forms).
    
    payload = {'key1': 'value1', 'key2': 'value2'}
    response = requests.post('https://api.example.com', json=payload)
    # Use 'data' for form-encoded data, 'json' for JSON data
    

*   **Other Methods:**
    
    requests.put(url, data=data)    # Update a resource
    requests.delete(url) # Delete a resource
    requests.patch(url, data=data)   # Partial update
    requests.head(url)   # Retrieve headers only
    requests.options(url) # Retrieve supported HTTP methods
    

### Handling Responses

The request methods return a `Response` object, which has several useful attributes and methods.

*   **Status Codes:**
     
    print(response.status_code) # e.g., 200, 404
    if response.status_code == 200:
        print("Request successful!")
    # or use the built-in check
    response.raise_for_status() # Raises an HTTPError if the status is bad
 
*   **Response Content:**

    print(response.text)    # Returns the response body as a string
    print(response.content) # Returns the response as raw bytes
    print(response.json())  # Converts JSON response to a Python dictionary

*   **Headers:**

    print(response.headers) # A dictionary of response headers


### Advanced Usage

*   **Query Parameters:** Pass parameters in the URL using the `params` dictionary.

    params = {'userId': 1, 'sort': 'asc'}
    response = requests.get('https://api.example.com', params=params)
    print(response.url) # The final URL with the query string


*   **Custom Headers:** Send custom HTTP headers in your request.
    headers = {'User-Agent': 'MyCustomApp', 'Authorization': 'Bearer <token>'}
    response = requests.get(url, headers=headers)


*   **Timeouts:** Set a timeout to stop waiting for a response after a specified number of seconds.

    response = requests.get(url, timeout=5) # wait max 5 seconds


*   **Sessions:** Use a `Session` object to persist certain parameters across requests, such as cookies and headers, improving performance and managing connection reuse.

    with requests.Session() as session:
        session.headers.update({'Authorization': 'Bearer <token>'})
        session.get('https://api.example.com')
        session.get('https://api.example.com')
```
