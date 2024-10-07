# Expirenza Translator

Expirenza Translator is a Python script that crawls a restaurant's menu from
[Expirenza](https://expz.menu/) and translates the content from Ukrainian to a target language
using OpenAI's GPT models.

The script extracts categories, subcategories, menu items, descriptions, and allergens, saving
the data into an Excel file.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Script Details](#script-details)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Restaurant Details**: Scrapes the subtitle and about text of the restaurant.
- **Menu Extraction**: Retrieves categories, subcategories, and menu items including titles,
  amounts, descriptions, and allergens.
- **Translation**: Translates all extracted Ukrainian text into the target language using OpenAI's GPT API.
- **Excel Output**: Saves the data into an Excel file with separate sheets for categories, menu items,
and restaurant details.

### Prerequisites

- **Python 3.6** or higher.
- **Google Chrome** browser installed.
- **ChromeDriver** matching your Chrome version.
- **OpenAI API Key**: You need an API key from OpenAI to use their translation service.

### Steps

1. **Clone the Repository**

   ```bash
   git clone https://github.com/id-tarzanych/expirenza-translator.git
   cd expirenza-translator
   ```

2. **Create a Virtual Environment** (Optional but Recommended

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use venv\Scripts\activate
   ```
   
3. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Download ChromeDriver** (if not installed)

- Download ChromeDriver from the [official website](https://developer.chrome.com/docs/chromedriver/downloads).
- Ensure the version matches your installed version of Chrome.
- Add the ChromeDriver executable to your system's PATH or place it in the same directory as the script.

5. **Set OpenAI API Key**

Sign up for an OpenAI account and get your API key.

Set the `OPENAI_API_KEY` environment variable:

   ```bash
   export OPENAI_API_KEY='your-api-key-here'  # On Windows use set instead of export
   ```

---

## Usage

```bash
python main.py output_file.xlsx -u <restaurant_uuid> [-l <language>]
```

- `output_file.xlsx`: The name of the Excel file to save the results.
- `-u <restaurant_uuid>`: The UUID of the restaurant from Expirenza.
- `-l <language>`: (Optional) The target language for translation. Default is English.

### Example

```bash
python main.py menu-polish.xlsx -u c50ba2a6-90bb-4595-860b-8e6b08ffea8f -l Polish
```

### Help

```bash
python main.py -h
```

## Script Details

### Functionality

- **Translating Text**: Uses OpenAI's GPT models to translate Ukrainian text into the target language.
- **Web Scraping**: Utilizes Selenium WebDriver to navigate and scrape data from the Expirenza website.
- **Data Extraction**: Collects restaurant details, menu categories, subcategories, and menu items including
  descriptions and allergens.
- **Data Storage**: Saves the extracted and translated data into an Excel workbook with separate sheets.

### Excel Output Structure

- **Categories and Subcategories**: Contains Ukrainian text and translations of all categories and subcategories.
- **Menu Items**: Includes details of each menu item, grouped by item title, with columns for category, subcategory, 
  type (Title, Amount, Description, Allergens), Ukrainian text, and translation.
- **Restaurant Details**: Contains the subtitle and about text of the restaurant in Ukrainian and the translated version.

## Dependencies

- **openai**
- **selenium**
- **openpyxl**

Install them using:

```bash
pip install -r requirements.txt
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request on
[GitHub](https://github.com/id-tarzanych/expirenza-translator).

## License

This project is licensed under the [MIT License](LICENSE).

