# Scrapping Web Crypto - CoinMarketCap

**Note: This project was developed as a Midtest requirement.**

A Python-based project (Jupyter Notebook) designed to perform web scraping on CoinMarketCap. This project focuses on extracting cryptocurrency market data for the "Top Gainers" and "Top Losers", and subsequently exports the extracted data into an Excel spreadsheet format (.xlsx).

## Key Features
This script captures the latest cryptocurrency market data for assets experiencing the highest percentage increases (gainers) and decreases (losers) over the last 24 hours. The specific data extracted includes:
- Cryptocurrency Name
- Current Price
- Price Change Percentage over 24 hours (24h Change)
- 24-Hour Trading Volume

## Environment Prerequisites
Before running this project, ensure that your system has the following software installed:
- Python 3.8 or a newer version
- Jupyter Notebook
- A stable internet connection

## Installation Guide
Follow the steps below to properly configure the project locally:

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/yowxy/Scrapping-Crypto-CoinMarketCap.git
   ```

2. Navigate into the project directory:
   ```bash
   cd "Scrapping Web Crypto"
   ```

3. (Highly Recommended) Create and activate a virtual environment to prevent dependency conflicts with other projects:
   ```bash
   python -m venv .env
   
   # For Windows operating systems:
   .env\Scripts\activate
   
   # For macOS/Linux operating systems:
   source .env/bin/activate
   ```

4. Install all the required Python libraries by executing the following command:
   ```bash
   pip install requests pandas beautifulsoup4 openpyxl jupyter
   ```

## Usage Instructions
Steps to execute the data extraction process:

1. Launch Jupyter Notebook through your command line or terminal within the current project directory:
   ```bash
   jupyter notebook
   ```

2. In the automatically opened web browser window, select and open the `index.ipynb` file.

3. Execute the cells within the notebook sequentially by pressing `Shift + Enter` on each cell:
   - **Cell Block 1**: Imports the necessary libraries (requests, pandas, bs4, openpyxl).
   - **Cell Block 2**: Performs an HTTP GET request to the CoinMarketCap URL, parses the HTML structure, and formats the data. This process will print text previews and directly export the final results into `gainers.xlsx` and `losers.xlsx` in the same directory.
   - **Cell Block 3 & 4**: Displays a Pandas DataFrame representation of the newly created Excel files, allowing you to review the tabular format.

## Directory and File Structure
- `index.ipynb` : The main script containing the web scraping logic utilizing BeautifulSoup and data processing.
- `gainers.xlsx` : The generated output spreadsheet containing a compiled list of top-performing cryptocurrencies. (Available after script execution).
- `losers.xlsx` : The generated output spreadsheet containing a compiled list of worst-performing cryptocurrencies. (Available after script execution).
- `.env/` : The directory accommodating the local virtual environment (if you followed the virtual environment installation step).

## Disclaimer
The HTML structure (DOM) of the target website (CoinMarketCap) may be modified by its developers at any given time. If the data extraction fails in the future, please verify and update the search parameters (such as the HTML class reference `cmc-table`) located within the BeautifulSoup scraping logic inside the notebook file.
