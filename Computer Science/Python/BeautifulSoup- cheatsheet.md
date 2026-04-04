Installation and Setup

- **Install** the library and a parser (like `lxml`) using `pip`:
    
    bash
   
- ```
    pip install beautifulsoup4 lxml
    ```
    
- **Import** the library in your Python script:
    
    python
    
- ```
    from bs4 import BeautifulSoup
    import requests # Used for fetching the webpage content
    ```
    
- **Create a BeautifulSoup object** to parse HTML content:
    
    python
    

```
url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.content, 'lxml') # 'lxml' is generally faster than 'html.parser'
```

 

Object Types

When navigating the parse tree, you will primarily encounter two object types: 

- **`Tag`**: Corresponds to an HTML or XML tag (e.g., `<a>`, `<div>`, `<p>`) and its contents.
- **`NavigableString`**: Represents the text content within a tag, without any nested tags. 

Searching the Tree

These methods are used to find elements within the parsed document: 

|Method|
|---|

||Purpose|Example|
|---|---|---|
|`find()`|Finds the first occurrence of a tag.|`first_link = soup.find('a')`|
|`find_all()`|Finds all occurrences of a tag.|`all_links = soup.find_all('a')`|
|`select()`|Finds elements using CSS selectors.|`header_elements = soup.select('.header')`|

You can filter searches by attributes like `class` or `id`: 

python

```
element_by_id = soup.find(id='main')
elements_by_class = soup.find_all('div', class_='my_class')
```

Navigating the Tree

You can traverse the relationships between elements: 

- **Parent**: Access the parent of a tag: `tag.parent`
- **Children**: Access children as a list or generator: `tag.contents` (list) or `tag.children` (generator)
- **Siblings**: Access elements at the same level: `tag.next_sibling`, `tag.previous_sibling`
- **Descendants**: Access all descendants: `tag.descendants` 

Extracting Data

Once you have a tag, you can extract its data: 

- **Get text content**:
    
    python
    

- ```
    text = tag.get_text()
    # Or simply tag.string for NavigableStrings
    ```
    
- **Get an attribute's value**:
    
    python
    
- ```
    link_url = link_tag['href']
    # or a safer way:
    link_url = link_tag.get('href')
    ```
    
- **Get all URLs in a page**:
    
    python
    
- ```
    for link in soup.find_all('a'):
        print(link.get('href'))
    ```
    
- **Get the raw HTML string**:
    
    python
    

```
html_string = str(tag)
```

[Beautiful-Soup Docs](https://www.google.com/url?sa=i&source=web&rct=j&url=https://www.crummy.com/software/BeautifulSoup/bs4/doc/&ved=2ahUKEwiqnq_C2ruTAxVP1fACHaZVIK8Qy_kOegQIEhAB&opi=89978449&cd&psig=AOvVaw2MOLUjmPnQa_QtCSBivJUf&ust=1774550666915000)