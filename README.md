# Cryptocurrency Market Scraper: CoinMarketCap

**Note: This project was developed as a Midtest requirement.**

## 1. Overview
This project provides an automated, Python-based pipeline for extracting real-time market data from CoinMarketCap. The underlying architecture utilizes a Jupyter Notebook environment to parse and compile the "Top Gainers" and "Top Losers" metrics. Extracted information is automatically exported into structured Microsoft Excel datasets (`.xlsx`), enabling further analytical modeling and data processing.

## 2. Core Features
The script runs a robust scraping protocol engineered to capture the most volatile cryptocurrency assets within a rolling 24-hour window. Data points extracted per asset include:
- **Asset Identifier:** The official designation and name of the cryptocurrency.
- **Market Valuation:** The current trading price.
- **24-Hour Price Delta:** The recorded percentage change in value over the last day.
- **Trading Volume:** The aggregate 24-hour market transaction volume.

## 3. System Requirements
To execute this analysis pipeline, the target machine must fulfill the ensuing prerequisites:
- Python 3.8+ runtime environment.
- Jupyter Notebook execution engine.
- A stable internet connection to facilitate HTTP requests.

## 4. Initialization and Setup
Please adhere to the following configuration sequence to deploy the application locally:

1. **Repository Cloning:**
   Clone the source code to your local machine:
   ```bash
   git clone https://github.com/yowxy/Scrapping-Crypto-CoinMarketCap.git
   ```

2. **Directory Navigation:**
   Change the current working directory to the project boundary:
   ```bash
   cd Scrapping-Crypto-CoinMarketCap
   ```

3. **Virtual Environment Isolation (Recommended):**
   Isolate project dependencies to prevent system-wide package degradation:
   ```bash
   python -m venv venv
   
   # For Windows operations:
   venv\Scripts\activate
   
   # For UNIX-based operations (macOS/Linux):
   source venv/bin/activate
   ```

4. **Dependency Resolution:**
   Install the required internal dependencies via the package manager:
   ```bash
   pip install requests pandas beautifulsoup4 openpyxl jupyter
   ```

## 5. Execution Protocol
Follow these operational directives to trigger the web scraper:

1. Instantiate the Jupyter runtime server from the project's root directory:
   ```bash
   jupyter notebook
   ```

2. Upon automatic browser redirection, locate and open the `index.ipynb` node.

3. Progressively compile and execute the notebook cells sequentially:
   - **Initialization Phase:** Evaluates and imports necessary external libraries (`requests`, `pandas`, `bs4`, `openpyxl`).
   - **Extraction Phase:** Establishes HTTP transmission with CoinMarketCap, dissects the returned HTML DOM payloads, and sanitizes the derived output. The generated objects are natively written into `gainers.xlsx` and `losers.xlsx`.
   - **Verification Phase:** Uses Pandas DataFrames to output formatted visual previews, confirming data consistency and programmatic success.

## 6. Target Architecture File Map
- `index.ipynb` : The primary script enforcing extraction schemas via BeautifulSoup logic.
- `gainers.xlsx` : Serialized output file containing the top positive margin assets. *(Generated upon execution).*
- `losers.xlsx` : Serialized output file containing the top negative margin assets. *(Generated upon execution).*
- `venv/` : Local directory housing the containerized virtual environment dependencies.

## 7. Technical Disclaimer
The structural integrity of this extraction logic relies on the current, static DOM configuration inherent to the CoinMarketCap front-end layout. Future deployments or interface updates by the target provider may alter styling classes (such as the base class `.cmc-table`), which will directly deprecate the scraping node's query selectors. Active revision of the BeautifulSoup extraction pointers within the Notebook will be necessary should a structural front-end update occur.
