```text
██████╗ ███████╗ █████╗ ██╗          ███████╗███████╗████████╗ █████╗ ████████╗███████╗      
██╔══██╗██╔════╝██╔══██╗██║          ██╔════╝██╔════╝╚══██╔══╝██╔══██╗╚══██╔══╝██╔════╝      
██████╔╝█████╗  ███████║██║          █████╗  ███████╗   ██║   ███████║   ██║   █████╗        
██╔══██╗██╔══╝  ██╔══██║██║          ██╔══╝  ╚════██║   ██║   ██╔══██║   ██║   ██╔══╝          
██║  ██║███████╗██║  ██║███████╗     ███████╗███████║   ██║   ██║  ██║   ██║   ███████╗      
╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚══════╝     ╚══════╝╚══════╝   ╚═╝   ╚═╝  ╚═╝   ╚═╝   ╚══════╝      

█████╗ ██████╗ ██████╗
██╔══██╗██╔══██╗██╔══██╗ 
███████║██████╔╝██████╔╝
██╔══██║██╔═══╝ ██╔═══╝ 
██║  ██║██║     ██║   
╚═╝  ╚═╝╚═╝     ╚═╝    
```

# Overview

# Real Estate Investment Analysis App

A Python application that **scrapes apartment listings from Krisha.kz**, analyzes real estate market data, and identifies **potential investment opportunities**.

The application automatically processes property listings using statistical analysis and exports the results to **Google Sheets** for easy viewing and tracking.

---

## Features

- Scrapes apartment listings from **Krisha.kz**
- Filters listings by **number of rooms**
- Optional filtering by **location or district**
- Filters properties by **maximum budget**
- Calculates **price per square meter**
- Removes unrealistic listings using **statistical filtering**
- Detects **undervalued properties**
- Generates an **investment score**
- Saves results to **Google Sheets**
- Highlights the **top investment opportunities**

---

## Project Workflow

1. User enters search criteria:
   - Country
   - City
   - Number of rooms
   - Preferred location
   - Maximum budget

2. **Playwright** scrapes property listings from Krisha.kz.

3. The data is cleaned and structured using **Pandas**.

4. The application calculates:

   - Apartment size (m²)
   - Price per square meter
   - Z-score (market deviation)
   - Liquidity score
   - Center location score
   - Overall investment score

5. Listings are ranked by **investment score**.

6. Results are exported to **Google Sheets** where the best opportunities are highlighted.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Workflow](#project-workflow)

- [Instructions](#instructions)
  - [How to Use the App](#how-to-use-the-app)

- [UX](#ux)
  - [MVP](#mvp)
  - [The 5 Planes of UX](#the-5-planes-of-ux)
    - [Strategy](#1-strategy)
    - [Scope](#2-scope)
    - [Structure](#3-structure)
    - [Skeleton](#4-skeleton)
    - [Surface](#5-surface)

- [User Stories](#user-stories)

- [Features](#features-1)
  - [Existing Features](#existing-features)
  - [Future Features](#future-features)

- [Tools & Technologies](#tools--technologies)

- [Functions](#functions)

- [Imports](#imports)

- [Agile Development Process](#agile-development-process)
  - [GitHub Projects](#github-projects)
  - [GitHub Issues](#github-issues)
  - [MoSCoW Prioritisation](#moscow-prioritisation)

- [Testing](#testing)
  - [Manual Testing Documentation](#manual-testing-documentation)

- [Bug Fixing](#bug-fixing)

- [Deployment](#deployment)
  - [Heroku Deployment](#heroku-deployment)
  - [Google Sheets API Setup](#google-sheets-api-setup)

- [Local Development](#local-development)
  - [Cloning the Repository](#cloning-the-repository)
  - [Forking the Repository](#forking-the-repository)
  - [Local vs Deployed Version](#local-vs-deployed-version)

- [Credits](#credits)
  - [Content & Learning Resources](#content--learning-resources)
  - [Media & Data Sources](#media--data-sources)
  - [Tools & Development Environment](#tools--development-environment)
  - [AI Assistance](#ai-assistance)

- [Acknowledgements](#acknowledgements)

---

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


# UX
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


<img width="600" src="https://github.com/user-attachments/assets/a95d2d94-43fe-4eda-b383-c007bdf421f1">


Derived Content:

- sqm

- price_per_m2

- z-score

- investment_score
  

Output Content:

- Ranked apartments

- Market statistics

- Investment opportunities


<img width="600" src="https://github.com/user-attachments/assets/f660ee40-6369-4ad4-b7ec-fe1b25d8968e">



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

<img width="600" src="https://github.com/user-attachments/assets/b86b9db2-bacd-4be1-9c28-5d736df7c617">



## 4. Skeleton

**Terminal Layout**

Simple command-line interface:

```bash
$ python main.py

Enter the country (only Kazakhstan is available):
Enter the city (only Almaty is available):
Number of rooms desired (e.g., 2):
Preferred district or location (optional):
Enter your maximum budget (0 - 500000000):
```
---
<img width="600" src="https://github.com/user-attachments/assets/6674821f-f979-4c25-8e77-d9b65e18cfa6">


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
| As a user | I want the program to load apartment listings so that I can analyze the market | - Set up Playwright<br>- Open krisha.kz<br>- Wait for listings | Listings page loads successfully | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want the program to collect apartment data so that it can be analyzed | - Extract header<br>- Extract price<br>- Extract location<br>- Extract link<br>- Store data | Listings appear in the data structure | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want invalid or irrelevant listings removed so that the analysis is accurate | - Remove duplicates<br>- Filter by rooms<br>- Filter by location<br>- Clean prices<br>- Filter by budget | Only valid listings remain | <img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want apartments ranked by investment potential so that I can find good opportunities | - Calculate z-score<br>- Calculate liquidity score<br>- Calculate center score<br>- Calculate investment score<br>- Sort listings | Listings ranked by investment score |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want the analysis results saved and properly formatted in Google Sheets so that I can easily review and compare properties | - Clear worksheet before writing new data<br>- Add header row<br>- Upload analyzed data<br>- Format header in bold<br>- Freeze header row<br>- Highlight top investment listings | Data is successfully written to Google Sheets<br>Header remains visible when scrolling<br>Top listings are highlighted |<img width="100" height="50" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want property metrics calculated and unrealistic listings filtered out so that I can compare apartments using reliable market data | - Extract apartment size (sqm)<br>- Convert size values to numeric format<br>- Remove invalid or zero sizes<br>- Calculate price per m²<br>- Filter unrealistic price per m² values<br>- Implement IQR outlier filtering | Dataset includes size and price per m²<br>Invalid sizes removed<br>Extreme values filtered out |<img width="100" height="50" src="https://github.com/user-attachments/assets/63d6ecda-a6c1-4c71-bb69-cd8c253eec90">|
| As a user | I want a summary of the market so that I understand price trends | - Calculate average price<br>- Calculate average size<br>- Calculate average price per m² | Summary printed in terminal |<img width="100" height="50" src="https://github.com/user-attachments/assets/63d6ecda-a6c1-4c71-bb69-cd8c253eec90">|
| As a user | I want the application to support multiple countries and cities so that I can analyze real estate markets in different locations | - Support multiple countries<br>- Support multiple cities<br>- Create dynamic URL generation<br>- Validate supported locations | User can select different countries and cities |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|
| As a user | I want the application to collect listings from multiple real estate websites so that I can get a more complete view of the market | - Design scraper structure for multiple sites<br>- Add support for additional websites<br>- Merge results into a single dataset | Data can be collected from more than one website<br>Results are combined into one dataset<br>Data format is consistent |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|
| As a user | I want the application to analyze apartment images and district-level market statistics so that I can better evaluate investment opportunities | - Collect apartment images<br>- Implement AI image analysis<br>- Detect apartment features from images | Images can be processed by AI<br>Apartment features can be extracted from images<br>Results improve investment analysis |<img width="100" height="50" src="https://github.com/user-attachments/assets/08a75d02-ba3d-47f2-a3bc-19bb0b7ecc02">|


# Features
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

Uses Playwright to scrape:

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
| [Python](https://www.python.org/) | Core programming language used to build the application |
| [Playwright](https://playwright.dev/) | Automated web scraping and browser automation for extracting real estate listings |
| [Pandas](https://pandas.pydata.org/) | Data cleaning, transformation, and analysis of scraped property data |
| [NumPy](https://numpy.org/) | Statistical calculations and numerical analysis for investment scoring |
| [Google Sheets API](https://sheets.googleapis.com/) | Cloud-based storage used to save analyzed real estate data |
| [gspread](https://docs.gspread.org/en/latest/) | Python library for interacting with Google Sheets (reading and writing data) |
| [gspread-formatting](https://pypi.org/project/gspread-formatting/) | Applies formatting such as bold headers, frozen rows, and highlighted results in Google Sheets |
| [google-auth](https://accounts.google.com/o/oauth2/v2/auth) | Handles authentication with Google APIs using a service account |
| [requests](https://pypi.org/project/requests/) | HTTP library used by Google API integrations |
| [python-dotenv](https://pypi.org/project/python-dotenv/) | Manages environment variables and configuration settings |
| [pyfiglet](https://pypi.org/project/pyfiglet/) | Generates ASCII art titles for the console interface |
| [Regular Expressions (via Pandas)](https://docs.python.org/3/library/re.html) | Extracts structured data such as number of rooms and apartment size from listing text |
| [Git](https://git-scm.com/) | Version control system used to track code changes |
| [GitHub](https://github.com/) | Platform for hosting the repository and project collaboration |
| [VS Code](https://code.visualstudio.com/) | Development environment used to write and run the code |



# Functions

The primary functions used in the Real Estate Analysis App are:

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

- Launches Playwright.
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

### playwright
Provides browser automation capabilities for scraping real estate listings.

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

---


## Why These Libraries Were Chosen

- **Playwright** enables interaction with dynamic websites where traditional HTTP requests are insufficient, allowing JavaScript-rendered content to be scraped reliably. It was also chosen because it works well in cloud environments such as Heroku, where headless browsers are required.

- **Pandas & NumPy** provide powerful data manipulation and statistical analysis tools used for cleaning listings, calculating price per square meter, removing outliers, and generating investment scores.

- **Google Sheets API** (via gspread) acts as lightweight cloud storage, eliminating the need for a traditional database while allowing results to be easily viewed and shared.

- **gspread-formatting** improves readability by formatting headers, freezing rows, and highlighting the most attractive investment opportunities.

Together, these tools create a complete pipeline:

**Web scraping → Data cleaning → Statistical analysis → Investment ranking → Cloud storage → Presentation**




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

<img width="900" alt="User story" src="https://github.com/user-attachments/assets/7962afa5-c8c9-467d-969e-2302fb3f3435">

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

---

<img width="900" alt="User story done" src="https://github.com/user-attachments/assets/92df8a37-d9fa-480f-88a6-14622202a971">


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

I validated all of my Python files using the recommended [PEP 8 CI Python Linter](https://pep8ci.herokuapp.com/).
The initial validation revealed several errors, which are shown below.

---

<img width="900" alt="PEP8 end" src="https://github.com/user-attachments/assets/5144b68a-9ffe-42a7-b8ed-b73af7b87145">


The validation process identified the following errors, which were then corrected:

---

<img width="900" alt="PEP8 clean" src="https://github.com/user-attachments/assets/3736527a-d7f8-4ce2-92e6-eda3b38007ca">


## Manual Testing Documentation

Defensive programming and application stability were manually tested using the following user acceptance tests.

| Feature | Expectation | Test | Result |
|--------|-------------|------|--------|
| Country validation | The application should only support Kazakhstan | Enter `USA` as country | Program displays message: *"Currently only Kazakhstan supported."* <img width="300" src="https://github.com/user-attachments/assets/b08a9c59-44ec-4872-8de6-385f5908cae8">|
| City validation | The application should only support Almaty | Enter `Astana` as city | Program displays message: *"Currently only Almaty supported."* <img width="300" src="https://github.com/user-attachments/assets/563786d5-ce7d-452a-be80-fade1e33daf6">|
| Price validation | The program should handle invalid price input | Enter a non-numeric value such as `abc` | Program assigns default max price of **500,000,000 ₸** <img width="300" src="https://github.com/user-attachments/assets/ec121045-a767-428c-a910-8e0f778cf162">|
| Unrealistic budget | The program should not crash when a very low budget is entered | Enter `6000` as budget | Program runs normally and returns **"No listings found."** <img width="300" src="https://github.com/user-attachments/assets/454e31d1-4201-4934-89a2-5b42b4ce7ea5">|
| Slow page loading | Scraper should not crash when pages load slowly | Simulate slow page loading | Timeout protection stops scraping safely |
| Page loading optimisation | Scraper should load pages efficiently | Load page using `domcontentloaded` | Pages load faster and scraper continues |
| Scraper stability | Program should not crash if a page fails to load | Trigger a page timeout | Program prints **"Page failed to load, stopping scraper."** |
| Missing listings | Program should handle empty datasets safely | Scrape with strict filters | Program prints **"No listings found."** <img width="300" src="https://github.com/user-attachments/assets/454e31d1-4201-4934-89a2-5b42b4ce7ea5">|
| Duplicate listings | Listings should not appear multiple times | Scrape multiple pages | Duplicate entries removed using `drop_duplicates()` |
| Google Sheets export | Results should be stored correctly | Run full scraping process | Listings successfully saved to Google Sheets <img width="300" src="https://github.com/user-attachments/assets/e557e56a-b11b-48d0-9b49-6f6e314cf738">|

---

## Example Output

After successful scraping and analysis, the program prints a **market summary and top investment opportunities**.

Example console output:

<img width="900" src="https://github.com/user-attachments/assets/e7fc7dd3-170d-4f4b-9f83-035a22f1a080">

---

<img width="900" src="https://github.com/user-attachments/assets/8e05657e-5926-4bcb-9e0a-7392e2a9e7ae">


---

<img width="900" src="https://github.com/user-attachments/assets/d907f10d-3bb2-4d1d-b3b1-2d0ca1383e62">


## Bug fixing

| Feature | Test | Result |
|-------|------|------|
| Chrome installation on Heroku | Checked `/app/.chrome-for-testing/` using `heroku run bash` | Chrome binaries detected |
| Chromedriver installation | Checked `/app/.chrome-for-testing/chromedriver-linux64/` | Chromedriver detected |
| Selenium browser startup | Ran the application via the web interface | Browser failed to start consistently on Heroku |
| Scraper functionality | Attempted to load listing pages using Selenium | Selenium errors occurred in the cloud environment |
| Data extraction | Tested scraping logic locally | Data extracted successfully |

### Note

During deployment testing, Selenium produced persistent issues on Heroku related to Chrome driver initialization.  
Despite multiple fixes (buildpack configuration, driver paths, and headless settings), the issue could not be fully resolved in the Heroku environment.

To ensure stable scraping in production, the scraping implementation was migrated from **Selenium to Playwright**, which provides better compatibility with headless browsers in cloud deployments.

### Timeout Adjustments

Heroku dynos run slower than a local machine. To ensure page content loads completely before scraping begins, the scraping timeouts were increased.

```bash
    page.goto(url, wait_until="domcontentloaded", timeout=60000)


    page.wait_for_selector(".a-card", timeout=60000)
```

### Playwright Browser Installation

To ensure that the required browser is available in the deployment environment (such as Heroku), Chromium is installed automatically using Playwright during runtime.

<img width="400" src="https://github.com/user-attachments/assets/508b429e-9ccf-41c4-a9ec-5e893ce45114">


This command installs the **Chromium browser** required for Playwright to run the scraping process. The stdout and stderr outputs are redirected to DEVNULL to suppress installation logs and keep the console output clean.

⚠️**Important note:** Installing Chromium during runtime may introduce a delay when the application starts. As a result, it can sometimes take **1–3 minutes** for the main ASCII-art text to appear while the browser installation and initialization process completes.

---

# Deployment

This project was deployed using **Heroku**, a cloud Platform as a Service (PaaS) that allows developers to build, run, and operate applications entirely in the cloud.

The application scrapes real estate listings, analyzes investment opportunities using Python, and stores the results in Google Sheets.

---

## Heroku Deployment

To deploy this application to Heroku, follow the steps below.

## 1. Create a Heroku App

1. Log in to your **Heroku account**.
2. From the **Heroku Dashboard**, click **New** in the top-right corner.
3. Select **Create new app**.
4. Enter a **unique app name**.
5. Choose the region closest to you (**EU or USA**).
6. Click **Create App**.

---

## 2. Configure Environment Variables

Navigate to:

`Settings → Reveal Config Vars`

Add the following variable:

| KEY | VALUE |
|-----|------|
| PORT | 8000 |

If using Google Sheets integration, add your service account credentials as an environment variable:

| KEY | VALUE |
|-----|------|
| CREDS_JSON | *(paste the contents of your `creds.json` file)* |

The `CREDS_JSON` variable should contain the full JSON content of your **Google service account credentials file**.

These credentials allow the application to securely authenticate with the **Google Sheets API** and write the analyzed data to the spreadsheet.

⚠️ **Important:**  
Never commit your `creds.json` file to a public repository. Environment variables are used to keep sensitive credentials secure when deploying the application.

---

### Google Sheets Access

The application writes results to the following spreadsheet:

[Google spreadsheet](https://docs.google.com/spreadsheets/d/1LsCn1ZCsya1gHUvBHxhPOWLg6muRCamR4Mk9WYVjDYM)

The sharing settings were intentionally configured to **"Anyone with the link – Viewer"** in order to simplify access for project reviewers and supervisors.

This allows the spreadsheet results to be viewed without requiring a Google account while preventing unauthorized edits.

⚠️ **Note:**  
This access configuration is intended **only for supervision and project evaluation purposes**.

Make sure the Google Sheet is **shared with the service account email** from the credentials file, otherwise the application will not be able to update the spreadsheet.

---

### Google API Credentials

The application uses a **Google service account** to securely access the Google Sheets API.

The credentials file (*creds.json*) contains authentication information that allows the application to write data to the spreadsheet.

For security reasons, this file is not included in the repository.

To run the project locally:

- Create a **Google Cloud Project**.

- Enable the **Google Sheets API**.

- Create a **Service Account**.

Download the credentials file and rename it to:

```bash
creds.json
```
Place the file in the **project root directory**.

Share the Google Sheet with the service account email (Editor access).


## 3. Add Buildpacks

Heroku requires buildpacks to install dependencies and run the application.

Navigate to:

`Settings → Buildpacks`

Add the following buildpacks in this order:
1. **Python**
2. **Node.js**

The order is important because the Python backend must run before Node services.

---

## 4. Required Deployment Files

Heroku requires several files in the project repository to run properly.

#### requirements.txt

This file lists all Python dependencies used in the project.

Install dependencies locally with:

```bash
pip3 install -r requirements.txt
```

If new packages are installed, update the file using:

```bash
pip3 freeze --local > requirements.txt
```

---

#### Procfile

The **Procfile** tells Heroku how to run the application.

Create it with the following command:

```bash
echo web: node index.js > Procfile
```

---

#### .python-version

This file specifies the Python version Heroku should use.

Example:

```text
3.12
```

---

## 5. Connect Heroku to GitHub

From the **Deploy tab** in Heroku:

1. Select **GitHub** as the deployment method.
2. Search for your repository.
3. Click **Connect**.

You can choose between **automatic deployment** or **manual deployment**.

---

### Automatic Deployment (Recommended)

Heroku automatically redeploys the application whenever new changes are pushed to GitHub.

---

### Manual Deployment

Alternatively, deploy using the terminal.

Login to Heroku:

```bash
heroku login -i
```

Set the Heroku remote:

```bash
heroku git:remote -a your_app_name
```

Push the application:

```bash
git push heroku main
```

---

## 6. Application Deployment

After deployment, Heroku will:

- Install dependencies from **requirements.txt**
- Run the Python application
- Execute the real estate scraping and analysis workflow

The application will run inside a **web-based terminal interface**.

---

## 7. Live Application

The live deployed application can be accessed here:

[Real Estate Analysis App](https://real-estate-app-2026-9178939f4b7b.herokuapp.com/)

---

### Notes

- The Google Sheets credentials file (`creds.json`) should **not be uploaded to GitHub**.
- Instead, the credentials should be stored securely in **Heroku Config Vars**.
- Playwright browsers may need to be installed during deployment using:

**playwright install chromium**

This ensures the scraper can run correctly in the cloud environment.

## Installing Puppeteer Heroku Buildpack

To run Puppeteer on Heroku, additional system dependencies are required because Heroku does not include all the libraries needed for Chromium by default. The `puppeteer-heroku-buildpack` installs the required dependencies so Puppeteer can run correctly in the Heroku environment.


## 8. Add the Puppeteer Buildpack

Install the buildpack using the Heroku CLI:

[heroku buildpacks:add](https://github.com/jontewks/puppeteer-heroku-buildpack)


Alternatively, you can add it from the **Heroku Dashboard**:

1. Open your application in the Heroku Dashboard.
2. Navigate to **Settings**.
3. Click **Add Buildpack**.
4. Enter the following URL:

[Puppeteer Heroku Buildpack](https://github.com/jontewks/puppeteer-heroku-buildpack)


<img width="900" src="https://github.com/user-attachments/assets/bed68260-90df-4a75-834c-1734c39ba74d">



# Google Sheets API Setup

This application uses **Google Sheets** as a lightweight cloud database to store analyzed real estate listings.

Each time the application runs, it:

- Connects to Google Sheets via the API  
- Opens the spreadsheet `real_estate_analysis_app`  
- Creates (or opens) a worksheet named with today’s date  
- Saves analyzed listings and investment scores  

---

## Create Your Own Google Sheet

To run your own version of this project, you must create a Google Sheet.

### Step 1 — Create Spreadsheet

1. Go to Google Sheets  
2. Create a new spreadsheet  
3. Name it:


The application will automatically create daily worksheets such as:

<img width="900" src="https://github.com/user-attachments/assets/4d11edbc-5616-4228-b17f-bbfcf395f5b5">



No manual worksheet setup is required.

---

# Google Cloud Platform Setup

You must create a **Service Account** and enable the required APIs.

### Step 1 — Create a New Project

1. Go to Google Cloud Console  
2. Click **Select a Project** → **New Project**  
3. Enter a project name  
4. Click **Create**  
5. Click **Select Project**

---

### Step 2 — Enable Required APIs

Go to:

APIs & Services → Library

Enable:

- Google Drive API  
- Google Sheets API  

---

### Step 3 — Create Service Account Credentials

1. Go to **APIs & Services → Credentials**
2. Click **Create Credentials**
3. Choose **Service Account**
4. Enter a service account name
5. Click **Create**
6. Under Role, select:

**Editor**


7. Click **Continue**
8. Click **Done**

---

### Step 4 — Generate the Credentials File

1. Locate the newly created **Service Account** in the credentials list.
2. Click on the service account name.
3. Navigate to the **Keys** tab.
4. Click **Add Key → Create New Key**.
5. Select **JSON**.
6. Click **Create**.

A JSON file will be downloaded to your computer.

---

### Step 5 — Configure the Credentials File

Rename the downloaded file to:

**creds.json**

Place the file in the **root directory of the project**.

Example project structure:

real-estate-analysis-app
│
├── main.py
├── requirements.txt
├── Procfile
├── creds.json
└── README.md


---

### Step 6 — Share the Google Sheet with the Service Account

1. Open your **Google Sheet**.
2. Click **Share**.
3. Copy the **service account email** from the credentials file.
4. Add it as a collaborator.
5. Grant **Editor** access.

This allows the application to write data to the spreadsheet using the **Google Sheets API**.


# Local Development

This project can be cloned or forked to create a local copy on your own machine for development and testing.

Before running the project locally, ensure that all required dependencies are installed. These dependencies are listed in the **requirements.txt file**.

To install them, run:

```bash
pip3 install -r requirements.txt
```

If the project uses environment variables or confidential credentials (such as **env.py**, **.env files**, **API keys**, or database configuration files), these must be created manually in your local environment. These files are typically excluded from the repository to protect sensitive information.

Once dependencies are installed, the application can be run locally using the appropriate Python command depending on the project structure.

## Cloning the Repository

You can clone the repository by following these steps:

1. Navigate to the GitHub repository.

2. Click the green **Code** button near the top of the page.

3. Choose your preferred method: **HTTPS, SSH**, or **GitHub CLI**.

4. **Copy** the repository URL.

5. Open **Git Bash** or your **terminal**.

6. Navigate to the directory where you want to store the project.

7. Run the following command:

```bash
git clone https://github.com/akashebaev-ux/real_estate_analysis_app.git
```
8. Press **Enter** to create your local clone.

After cloning, move into the project directory and install the required dependencies.

---

## Forking the Repository

Forking allows you to create your own copy of the repository so you can make changes without affecting the original project.

To fork this repository:

1. Log in to your **GitHub** account.

2. Open the repository page.

3. Click the **Fork** button in the top-right corner.

4. GitHub will create a copy of the repository in your own account.

You can then clone your forked version to your local machine and start working on the project.

---

## Local vs Deployed Version

The local version of the application allows developers to test features and experiment with the code before deployment.

The deployed version is hosted online and may include:

- Production configuration settings

- Environment variables

- Performance optimizations

While both versions should behave similarly, small differences may occur depending on the deployment environment or hosting platform.

---


# Credits

## Content & Learning Resources

| Source | Contribution |
|------|------|
| Python Documentation | Official reference for Python language features and libraries |
| Pandas Documentation | Data manipulation and analysis techniques used for cleaning and processing listing data |
| NumPy Documentation | Statistical calculations such as z-scores and numerical analysis |
| Playwright Documentation | Guidance for browser automation and scraping dynamic web pages |
| Google Sheets API Documentation | Integration for storing analysis results in cloud spreadsheets |
| gspread Documentation | Python library used to interact with Google Sheets |
| Stack Overflow | Troubleshooting programming issues and debugging techniques |
| W3Schools | Reference material for Python concepts and syntax |
| GeeksforGeeks | Programming explanations and examples used during development |

---

## Media & Data Sources

| Source | Notes |
|------|------|
| Krisha.kz | Real estate listings used as the primary dataset for apartment market analysis |
| Google Sheets | Cloud-based storage used for saving and viewing analyzed results |

---

## Tools & Development Environment

| Tool | Purpose |
|------|------|
| Git | Version control system used for tracking project changes |
| GitHub | Repository hosting and project management |
| Visual Studio Code | Primary development environment |
| Heroku | Cloud platform used to deploy and run the application |

---

## AI Assistance

AI tools were used during development as **learning aids and development support**.

### ChatGPT

Used for:

- Explaining some error messages  
- Helping structure docstrings and README sections  

AI assistance was used **as a learning support tool**, and all code written in the project was reviewed, understood, and implemented by the developer.

---

# Acknowledgements

I would like to thank:

- The open-source developer community for sharing knowledge and educational resources.  
- Developers and contributors on platforms such as **Stack Overflow** for providing solutions and discussions that helped solve technical challenges.  
- Educational materials and programming documentation that supported the development of this project.
