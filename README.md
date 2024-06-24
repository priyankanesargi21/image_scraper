<h1>Web Image Scraper</h1>

<h3>Description:</h3>
<p>Web Image Scraper is a Python project designed to download images from a web page based on keyword entered in front end search bar. In this example, the project focuses on extracting images related to Narendra Modi from the web. The program recursively traverses links, identifies images with specified keywords in their alt attributes, and saves them to a local directory and even storing in mongodb.

To use the project, clone the repository and modify the example usage section with your preferred URL, save_directory, mongoDB URI. Ensure compliance with the terms of service of the website you are scraping, and consider contributing improvements to benefit the community</p>

<h3>Explanation:</h3>
<h6> Dependencies: </h6>

```
import requests
from bs4 import BeautifulSoup
import logging
import pymongo
logging.basicConfig(filename="scrapper.log" , level=logging.INFO)
import os
```

* `requests`: Used to send HTTP requests.
* `BeautifulSoup`: A library for parsing HTML content.
* `os`: Provides functionality for interacting with the operating system.
* `pymongo`: Used for mongodb connection
* `Logging`: Used to track events when server runs.

<h3>Things to Change after cloning</h3>

```
save_directory = "images/"
search_url = f"https://www.google.com/search?q={query}&sxsrf=AJOqlzUuff1RXi2mm8I_OqOwT9VjfIDL7w:1676996143273&source=lnms&tbm=isch&sa=X&ved=2ahUKEwiq-qK7gaf9AhXUgVYBHYReAfYQ_AUoA3oECAEQBQ&biw=1920&bih=937&dpr=1#imgrc=1th7VhSesfMJ4M"
mongodb_uri = "mongodb+srv://priyankanesargi:******@priyankanesargi.cnk5ej5.mongodb.net/?retryWrites=true&w=majority&appName=priyankanesargi"
```

<h5> If Mongodb not required then comment below code</h5>

```
mongodb_uri = "mongodb+srv://priyankanesargi:******@priyankanesargi.cnk5ej5.mongodb.net/?retryWrites=true&w=majority&appName=priyankanesargi"
client = pymongo.MongoClient(mongodb_uri)
db = client['image_scrap']
review_col = db['image_scrap_data']
review_col.insert_many(img_data) 
```

