# API Advanced

This repo demonstrates advanced techniques for interacting with APIs, including reading API documentation, implementing pagination, parsing JSON results, making recursive API calls, and sorting dictionaries by value.

## Getting Started

To get started with this repository, clone it to your local machine and explore the code samples provided in the `examples` directory.

### Prerequisites

Ensure you have Python installed on your system. You'll also need the `requests` library for making HTTP requests. Install it using pip:

```bash
pip install requests
```

### Reading API Documentation

API documentation is crucial for understanding how to interact with an API effectively. Key steps include:

- Starting with the overview to grasp the API's purpose.
- Exploring the endpoints section for available URLs and methods.
- Reviewing detailed descriptions for specific endpoints.
- Checking for authentication requirements.

### Using an API with Pagination

Pagination is a technique to manage large datasets by dividing them into smaller, manageable chunks. Here's a basic example of how to implement pagination:

```python
import requests

def fetch_paginated_data(url):
    results = []
    page = 1
    while True:
        current_url = f"{url}?page={page}"
        response = requests.get(current_url)
        response.raise_for_status()
        data = response.json()
        results.extend(data["results"])
        if len(data["results"]) < data["per_page"]:
            break
        page += 1
    return results
```

### Parsing JSON Results from an API

Parsing JSON results allows you to work with structured data easily. Here's a simple example:

```python
import requests

response = requests.get('https://api.example.com/data')
data = response.json()
print(data)
```

### Making a Recursive API Call

Recursive API calls are useful for fetching nested data structures. Here's a conceptual example:

```python
def fetch_comments(comment_id):
    response = requests.get(f'https://api.example.com/comments/{comment_id}')
    data = response.json()
    print(data)
    for reply in data.get('replies', []):
        fetch_comments(reply['id'])
```

### Sorting a Dictionary by Value

Sorting a dictionary by its values can be achieved with the following approach:

```python
my_dict = {'apple': 10, 'banana': 15, 'cherry': 5}
sorted_dict = dict(sorted(my_dict.items(), key=lambda item: item[2]))
print(sorted_dict)
```
