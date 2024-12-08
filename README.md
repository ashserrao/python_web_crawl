# python_web_crawl - Scrapy Project

This repository contains a Scrapy project that demonstrates the use of `python_web_crawl` to scrape book details from the website [Books to Scrape](http://books.toscrape.com/).

## Features

- Extracts book titles, prices, and availability statuses from the site.
- Uses Scrapy's `python_web_crawl` class with `Rule` and `LinkExtractor` for efficient crawling.
- Handles dynamic link extraction and follows links within specified categories.

## Requirements

Ensure you have the following installed:

- Python 3.8+
- Scrapy 2.0+

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/python_web_crawl.git
   cd python_web_crawl
   ```

2. Create a virtual environment (optional but recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:

   ```bash
   pip install scrapy
   ```

## Usage

1. Navigate to the project directory:

   ```bash
   cd first_crawler
   ```

2. Run the spider:

   ```bash
   scrapy crawl mycrawler
   ```

3. The scraped data will be displayed in the terminal by default. To save it to a file, you can use:

   ```bash
   scrapy crawl mycrawler -o output.json
   ```

## Code Overview

### `python_web_crawl`

The spider is implemented in the following way:

- **`allowed_domains`**: Ensures the spider only crawls the `toscrape.com` domain.
- **`start_urls`**: Specifies the starting point of the crawl.
- **`rules`**: Defines the crawling behavior:
  - Follow links within the category pages.
  - Extract item details from individual product pages.
- **`parse_item`**: Extracts book title, price, and availability information.

### Key Scrapy Features Used

- **python_web_crawl**: A spider with predefined rules for crawling websites.
- **LinkExtractor**: Simplifies the extraction of links.
- **CSS Selectors**: For efficient data extraction from HTML.

## Example Output

A sample JSON output looks like this:

```json
[
  {
    "title": "A Light in the Attic",
    "price": "£51.77",
    "availability": "In stock"
  },
  {
    "title": "Tipping the Velvet",
    "price": "£53.74",
    "availability": "In stock"
  }
]
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a pull request.

---

Feel free to explore, modify, and use this project as a base for your web scraping needs!
