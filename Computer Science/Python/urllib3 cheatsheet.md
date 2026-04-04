Installation

`urllib3` is a third-party library and needs to be installed using pip. 

bash

```
python -m pip install urllib3
```

Basic Usage

The primary entry point for most functionality is the `PoolManager` instance, which handles connection pooling and thread safety automatically. 

python

```
import urllib3
import json

# Create a PoolManager instance
# It's recommended to reuse this instance across your application
http = urllib3.PoolManager()
```

Making a GET Request

python

```
# Make a GET request
response = http.request('GET', 'https://httpbin.org')

# Get the HTTP status code (e.g., 200, 404, 500)
print(f"Status Code: {response.status}")

# Read the response data (bytes)
# The data needs to be decoded for use as a string
data = response.data.decode('utf-8')
print(data)
```

Making a POST Request

`urllib3` can automatically form-encode data provided in the `fields` argument. 

python

```
# POST with form data
response = http.request(
    'POST',
    'https://httpbin.org',
    fields={'field': 'value', 'another_field': 'another_value'}
)

print(f"Status Code: {response.status}")
print(response.data.decode('utf-8'))
```

Sending JSON Data

For sending JSON, encode the data manually and set the `Content-Type` header. 

python

```
data = {'attribute': 'value'}
encoded_data = json.dumps(data).encode('utf-8')

response = http.request(
    'POST',
    'https://httpbin.org',
    body=encoded_data,
    headers={'Content-Type': 'application/json'}
)

print(f"Status Code: {response.status}")
print(response.data.decode('utf-8'))
```

Advanced Features

Timeouts

You can set default timeouts at the `PoolManager` level or override them per request. 

python

```
# Set a default timeout for all requests using this manager
http_with_timeout = urllib3.PoolManager(timeout=3.0)

# Override the timeout for a specific request
# Use urllib3.Timeout for granular control over connect and read timeouts
response = http_with_timeout.request(
    'GET',
    'https://example.com',
    timeout=urllib3.Timeout(connect=1.0, read=2.0)
)
```

Retries and Redirects

By default, `urllib3` will retry requests a few times and follow redirects. You can control this behavior with the `retries` parameter. 

python

```
# Disable all retry and redirect logic for a specific request
response = http.request('GET', 'https://example.com', retries=False)

# For more granular control, use a Retry instance
from urllib3.util.retry import Retry

# Only retry specific status codes, e.g., 503
custom_retry = Retry(total=3, status_forcelist=[503], backoff_factor=0.1)

response = http.request(
    'GET',
    'https://example.com',
    retries=custom_retry
)
```

Error and Exception Handling

`urllib3` wraps lower-level exceptions for easier handling. 

python

```
try:
    http.request('GET', 'https://nx.example.com', retries=False)
except urllib3.exceptions.NewConnectionError:
    print('Connection failed.')
except urllib3.exceptions.HTTPError as e:
    print(f"HTTP error: {e}")
```

Key Links

- urllib3 Official Documentation
- [urllib3 PyPI Page](https://pypi.org/project/urllib3/)