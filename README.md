```text
██████╗ ███████╗ █████╗ ██╗          ███████╗███████╗████████╗ █████╗ ████████╗███████╗      █████╗ ██████╗ ██████╗
██╔══██╗██╔════╝██╔══██╗██║          ██╔════╝██╔════╝╚══██╔══╝██╔══██╗╚══██╔══╝██╔════╝      ██╔══██╗██╔══██╗██╔══██╗ 
██████╔╝█████╗  ███████║██║          █████╗  ███████╗   ██║   ███████║   ██║   █████╗        ███████║██████╔╝██████╔╝
██╔══██╗██╔══╝  ██╔══██║██║          ██╔══╝  ╚════██║   ██║   ██╔══██║   ██║   ██╔══╝        ██╔══██║██╔═══╝ ██╔═══╝   
██║  ██║███████╗██║  ██║███████╗     ███████╗███████║   ██║   ██║  ██║   ██║   ███████╗      ██║  ██║██║     ██║   
╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚══════╝     ╚══════╝╚══════╝   ╚═╝   ╚═╝  ╚═╝   ╚═╝   ╚══════╝      ╚═╝  ╚═╝╚═╝     ╚═╝          
```

# Overview

**Real Estate Analysis App** is a command-line data analysis tool that scrapes apartment listings and identifies potential real estate investment opportunities.

The application collects apartment listings from real estate websites using Selenium, processes the data with Pandas, calculates investment metrics, and exports results to Google Sheets.

The program runs as a **single-use session**, allowing the user to define search criteria such as location, rooms, and budget, and performs investment metric calculations including price per m² and undervaluation detection.


**The application:**

- Scrapes apartment listings

- Cleans and filters data

- Calculates price per square meter

- Identifies undervalued apartments

- Ranks investment opportunities

- Saves results to Google Sheets


# Instructions

**How to Use the App**

Run the program:

```bash
python main.py
```

You will be asked to enter:

- Country

- City

- Number of rooms

- Preferred location (optional)

- Maximum budget

Example:

```text
Enter country: Kazakhstan
Enter city: Almaty
Rooms: 2
Location: Samal
Budget: 40000000
```

The program will:

1. Connect to Google Sheets

2. Scrape apartment listings

3. Analyze market data

4. Rank investment opportunities

5. Export results

## UX
**MVP**

A command-line real estate analysis tool that:

- Collects apartment search parameters

- Scrapes listings automatically

- Cleans and filters data

- Calculates investment metrics

- Identifies undervalued apartments

- Saves results to Google Sheets


# The 5 Planes of UX
## 1. Strategy

**Purpose**

Provide automated real estate market analysis.

**Primary User Needs**

- Find affordable apartments

- Compare prices

- Identify investments

- Analyze market trends

**Business Goals**

- Provide reliable analysis

- Automate real estate research

- Save time searching listings

## 2. Scope

**Features**

- Real estate web scraping

- Data cleaning

- Price analysis

- Investment scoring

- Google Sheets export

**Content Requirements**

Input Content:

Country

- City

- Rooms

- Location

- Budget

Derived Content:

- sqm

- price_per_m2

- z-score

- investment_score

Output Content:

- Ranked apartments

- Market statistics

- Investment opportunities

**Constraints**

- Currently supports Kazakhstan only

- Currently supports Almaty only

- Scrapes krisha.kz

- Command-line interface

## 3. Structure

**User Flow**

```text
User starts app
   ↓
Enters search criteria
   ↓
System validates input
   ↓
Connects to Google Sheets
   ↓
Scrapes listings
   ↓
Processes data
   ↓
Calculates metrics
   ↓
Ranks investments
   ↓
Exports results
```

## Flowchart

<img width="900" height="1200" alt="real_estate_analysis" src="https://github.com/user-attachments/assets/b86b9db2-bacd-4be1-9c28-5d736df7c617">



## 4. Skeleton

**Terminal Layout**

Simple command-line interface:

```bash
$ python main.py

Enter country:
Enter city:
Enter rooms:
Enter location:
Enter budget:
```

**Output Example**

```bash
MARKET SUMMARY

Average price: 38,200,000 ₸
Average size: 58.4 m²
Average price per m²: 653,000 ₸


TOP INVESTMENT OPTIONS

Header: 2-ком квартира
Location: Самал
Price: 32,000,000 ₸
Size: 60 m²
Price per m²: 533,000 ₸
Link: https://...
```

## 5. Surface
**Visual Design**

Minimal terminal-based interface.

Features:

- Clean text layout

- Clear prompts

- Structured output

- Market summary section

- Top investment section

# User Stories

| Target | Expectation | Tasks | Outcome | Priority |
|--------|------------|-------|---------|----------|
| As a developer | I want to set up the project structure so that the application can run locally | - Create main Python script<br>- Add required imports<br>- Install dependencies<br>- Verify script runs | Script runs without errors | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want the application to save results to Google Sheets so that I can access them later | - Set up Google Sheets API<br>- Add credentials<br>- Connect using gspread<br>- Test spreadsheet access | Application connects successfully to the spreadsheet |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want a worksheet created for each run so that my data is organized by date | - Generate today’s date<br>- Open worksheet<br>- Create worksheet if missing | Worksheet appears automatically |<img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want to enter search criteria so that I can analyze relevant apartments | - Country input<br>- City input<br>- Rooms input<br>- Location input<br>- Budget input | Inputs are accepted correctly |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want invalid inputs rejected so that the program runs correctly | - Validate country<br>- Validate city<br>- Validate budget | Invalid values stop execution | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want the program to load apartment listings so that I can analyze the market | - Set up Selenium<br>- Open krisha.kz<br>- Wait for listings | Listings page loads successfully | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want the program to collect apartment data so that it can be analyzed | - Extract header<br>- Extract price<br>- Extract location<br>- Extract link<br>- Store data | Listings appear in the data structure | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want invalid or irrelevant listings removed so that the analysis is accurate | - Remove duplicates<br>- Filter by rooms<br>- Filter by location<br>- Clean prices<br>- Filter by budget | Only valid listings remain | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want apartments ranked by investment potential so that I can find good opportunities | - Calculate z-score<br>- Calculate liquidity score<br>- Calculate center score<br>- Calculate investment score<br>- Sort listings | Listings ranked by investment score |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want the analysis results saved and properly formatted in Google Sheets so that I can easily review and compare properties | - Clear worksheet before writing new data<br>- Add header row<br>- Upload analyzed data<br>- Format header in bold<br>- Freeze header row<br>- Highlight top investment listings | Data is successfully written to Google Sheets<br>Header remains visible when scrolling<br>Top listings are highlighted |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want property metrics calculated and unrealistic listings filtered out so that I can compare apartments using reliable market data | - Extract apartment size (sqm)<br>- Convert size values to numeric format<br>- Remove invalid or zero sizes<br>- Calculate price per m²<br>- Filter unrealistic price per m² values<br>- Implement IQR outlier filtering | Dataset includes size and price per m²<br>Invalid sizes removed<br>Extreme values filtered out |<img width="100" height="50" src="https://github.com/user-attachments/assets/63d6ecda-a6c1-4c71-bb69-cd8c253eec90">|
| As a user | I want a summary of the market so that I understand price trends | - Calculate average price<br>- Calculate average size<br>- Calculate average price per m² | Summary printed in terminal |<img width="100" height="50" src="https://github.com/user-attachments/assets/63d6ecda-a6c1-4c71-bb69-cd8c253eec90">|
| As a user | I want the application to support multiple countries and cities so that I can analyze real estate markets in different locations | - Support multiple countries<br>- Support multiple cities<br>- Create dynamic URL generation<br>- Validate supported locations | User can select different countries and cities |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|
| As a user | I want the application to collect listings from multiple real estate websites so that I can get a more complete view of the market | - Design scraper structure for multiple sites<br>- Add support for additional websites<br>- Merge results into a single dataset | Data can be collected from more than one website<br>Results are combined into one dataset<br>Data format is consistent |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|
| As a user | I want the application to analyze apartment images and district-level market statistics so that I can better evaluate investment opportunities | - Collect apartment images<br>- Implement AI image analysis<br>- Detect apartment features from images | Images can be processed by AI<br>Apartment features can be extracted from images<br>Results improve investment analysis |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|


## Features
**Existing Features**
**User Input**

Collects:

- Country

- City

- Rooms

- Location

- Budget

**Input Validation**

Ensures:

- Country supported

- City supported

- Budget numeric

**Web Scraper**

Uses Selenium to scrape:

- Title

- Price

- Location

- Link

- Description

**Data Cleaning**

- Remove duplicates

- Clean price values

- Extract sqm

- Extract rooms

**Investment Metrics**

Calculates:

- price_per_m2

- z_score

- liquidity_score

- center_score

- investment_score

**Outlier Filtering**

- Uses IQR method to remove unrealistic prices.

**Google Sheets Export**

Exports:

- Listings

- Metrics

- Scores

**Spreadsheet Formatting**

- Bold headers

- Frozen header row

- Highlight top investments

**Market Summary**

Displays:

- Average price

- Average sqm

- Average price per m²

## Future Features

**Multiple Cities**

- Search multiple cities and countries.

**Multiple Websites**

- Scrape multiple real estate websites.

**AI Image Analysis**

- Analyze apartment images.

**District Statistics**

- Analyze districts separately.

## Tools & Technologies

| Tool / Technology | Purpose |
|-------------------|----------|
| Python | Core programming language |
| Selenium | Automated web scraping and browser automation |
| WebDriver Manager | Automatic ChromeDriver management |
| Pandas | Data processing and analysis |
| NumPy | Statistical calculations and numerical operations |
| Google Sheets API | Cloud-based data storage |
| gspread | Google Sheets integration for reading/writing data |
| gspread-formatting | Formatting Google Sheets output |
| google-auth | Authentication with Google APIs |
| python-dotenv | Environment variable management |
| Requests | HTTP requests handling |
| OAuthLib | Secure API authentication flows |
| Draw.io | Flowchart and system architecture design |
| Git | Version control system |
| GitHub | Code hosting and collaboration |
| VSCode | Development environment |
| ChromeDriver | Selenium browser driver |

# Functions

The primary functions used in the Real Estate Analysis App are:

---

## start_driver()

Initializes a Selenium WebDriver.

- Attempts to launch Chrome in headless mode.
- Falls back to Firefox, Edge, or Safari if needed.
- Automatically installs drivers using `webdriver-manager`.
- Exits the program if no supported browser is available.

---

## get_user_input()

Collects search parameters from the user.

Prompts for:

- Country  
- City  
- Number of rooms  
- Preferred district (optional)  
- Maximum budget  

Also prints the application title using `pyfiglet`.

---

## validate_location(country, city)

Validates user input for supported locations.

- Ensures country is `"kazakhstan"`.
- Ensures city is `"almaty"`.
- Exits the program if unsupported.

---

## parse_price(price_input)

Parses and validates the maximum budget input.

- Converts input to integer.
- Defaults to 500,000,000 if invalid or negative.
- Prevents program failure due to incorrect input.

---

## setup_google_sheets()

Establishes connection to Google Sheets.

- Authenticates using service account credentials.
- Opens the spreadsheet `real_estate_analysis_app`.
- Creates or opens a worksheet named with today's date.
- Returns the worksheet object.

---

## scrape_data(rooms_input)

Scrapes apartment listings from krisha.kz.

- Launches Selenium WebDriver.
- Iterates pages up to `MAX_PAGES`.
- Waits for listing cards to load.
- Extracts:
  - Header
  - Price
  - Location
  - Link
  - Combined text
- Returns raw listing data as a list.

---

## clean_data(all_data, rooms_input, location_input, max_price)

Processes and analyzes scraped data.

Performs:

- DataFrame creation  
- Duplicate removal  
- Room extraction using regex  
- Location filtering  
- Price cleaning and numeric conversion  
- Budget filtering  
- Apartment size (sqm) extraction  
- Price per m² calculation  
- IQR outlier removal  
- Z-score calculation  
- Undervaluation scoring  
- Liquidity scoring  
- Center location scoring  
- Final investment score calculation  
- Sorting by investment score  

Returns a cleaned and ranked DataFrame.

---

## save_to_sheets(df, ws)

Exports analyzed data to Google Sheets.

- Clears worksheet  
- Writes header row  
- Uploads:
  - Header  
  - Price  
  - Location  
  - Link  
  - sqm  
  - price_per_m2  
  - z_score  
  - liquidity_score  
  - center_score  
  - investment_score  

---

## print_results(df, ws)

Formats and displays results.

In Google Sheets:

- Bolds header row  
- Freezes header row  
- Highlights top 3 investment listings  

In terminal:

- Prints market summary:
  - Average price  
  - Average size  
  - Average price per m²  
- Displays top 3 investment opportunities  
- Confirms save to Google Sheets  

---

## main()

Orchestrates the full application workflow.

Steps:

1. Collect user input  
2. Validate location  
3. Parse budget  
4. Setup Google Sheets  
5. Scrape listings  
6. Clean and analyze data  
7. Save results  
8. Display summary  

Acts as the central controller of the application.

---

## Program Entry Point

```python
if __name__ == "__main__":
    main()
```

# Imports

The following Python packages and external libraries were used in this project:

---

## Core Dependencies

### gspread
Used to interact with Google Sheets.  
Allows reading from and writing to spreadsheets, effectively serving as a lightweight cloud database.

### google.oauth2.service_account
Handles secure authentication with the Google Sheets API using a service account.

### selenium
Provides browser automation capabilities for scraping real estate listings.

### webdriver-manager
Automatically downloads and manages browser drivers (Chrome, Firefox, Edge), eliminating manual driver setup.

### pandas
Used for data manipulation and analysis.  
Transforms raw scraped data into structured DataFrames for processing.

### numpy
Provides numerical operations required for statistical calculations such as z-scores and investment metrics.

### gspread-formatting
Enables formatting of Google Sheets output (bold headers, frozen rows, highlighted cells).

### pyfiglet
Generates ASCII-art text for the application title displayed at startup.

---

## Standard Library

### datetime
Used to generate the current date for automatic worksheet naming.

### sys
Used to safely terminate the program if no supported browser is available.

---

## Selenium Components

### WebDriverWait & expected_conditions
Used to ensure webpage elements load before scraping begins, improving reliability.

### By
Locates elements on a webpage using class names, tags, and other selectors.

### ChromeService / FirefoxService / EdgeService
Used to configure and launch specific browser drivers.

---

## Why These Libraries Were Chosen

- **Selenium** enables dynamic website interaction where traditional HTTP requests are insufficient.
- **Pandas & NumPy** provide powerful data analysis capabilities.
- **Google Sheets API** removes the need for a traditional database while enabling persistent storage.
- **webdriver-manager** simplifies environment setup and improves portability.
- **gspread-formatting** enhances output presentation for better usability.

Together, these tools create a complete pipeline:
Web scraping → Data processing → Statistical analysis → Cloud storage → Presentation.


# Agile Development Process

## GitHub Projects

GitHub Projects was used as an Agile planning and tracking tool throughout development.

A Kanban-style board was created to manage:

- User Stories  
- Feature implementation  
- Bug fixes  
- Future improvements  

Tasks were organised into workflow stages such as:

- To Do  
- In Progress  
- Done  

This approach ensured structured progress and clear visibility of development priorities.

<img width="1908" height="881" alt="User story" src="https://github.com/user-attachments/assets/7962afa5-c8c9-467d-969e-2302fb3f3435">

---

## GitHub Issues

GitHub Issues was used to:

- Define User Stories  
- Track feature development  
- Record bugs  
- Document improvements  

Each issue followed a user-story format:

> As a user, I want... so that...

Issues were labelled according to priority and category.  
Comments were used to document thought processes, implementation decisions, and debugging steps.

This provided a transparent development history and clear traceability between requirements and implementation.

<img width="900" alt="User story 3" src="https://github.com/user-attachments/assets/ac19f9e7-e021-46c8-9f53-51c39304d0b2">

---

<img width="900" alt="User story 4" src="https://github.com/user-attachments/assets/37a4456c-9a07-455f-9985-7b05fb37966b">


## MoSCoW Prioritisation

User Stories were prioritised using the MoSCoW framework:

### Must Have
Core functionality required for the application to operate correctly:
- User input collection  
- Web scraping  
- Data cleaning  
- Investment scoring  
- Google Sheets export  

### Should Have
Important features that enhance usability:
- Market summary statistics  
- Investment ranking  
- Spreadsheet formatting  

### Could Have
Enhancements planned for future iterations:
- Multi-city support  
- Multi-website scraping  
- Advanced filtering  
Future or long-term improvements:
- AI image analysis  
- District-level predictive analytics  
- Historical performance tracking  

This prioritisation helped maintain focus on delivering a functional MVP while planning future scalability.

---

# Testing

Comprehensive testing was performed throughout development.

Testing included:

- Input validation checks  
- Web scraping reliability  
- Data cleaning accuracy  
- Outlier filtering validation  
- Investment score calculations  
- Google Sheets integration  
- Error handling scenarios  

For detailed testing documentation, please refer to:
<img width="900" alt="PEP8 end" src="https://github.com/user-attachments/assets/5144b68a-9ffe-42a7-b8ed-b73af7b87145">

---

<img width="900" alt="PEP8 clean" src="https://github.com/user-attachments/assets/3736527a-d7f8-4ce2-92e6-eda3b38007ca">

# Deployment




