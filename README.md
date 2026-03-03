```text
██████╗ ███████╗ █████╗ ██╗          ███████╗███████╗████████╗ █████╗ ████████╗███████╗      █████╗ ██████╗ ██████╗
██╔══██╗██╔════╝██╔══██╗██║          ██╔════╝██╔════╝╚══██╔══╝██╔══██╗╚══██╔══╝██╔════╝      ██╔══██╗██╔══██╗██╔══██╗ 
██████╔╝█████╗  ███████║██║          █████╗  ███████╗   ██║   ███████║   ██║   █████╗        ███████║██████╔╝██████╔╝
██╔══██╗██╔══╝  ██╔══██║██║          ██╔══╝  ╚════██║   ██║   ██╔══██║   ██║   ██╔══╝        ██╔══██║██╔═══╝ ██╔═══╝   
██║  ██║███████╗██║  ██║███████╗     ███████╗███████║   ██║   ██║  ██║   ██║   ███████╗      ██║  ██║██║     ██║   
╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚══════╝     ╚══════╝╚══════╝   ╚═╝   ╚═╝  ╚═╝   ╚═╝   ╚══════╝      ╚═╝  ╚═╝╚═╝     ╚═╝          
```

## Overview

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


## Instructions

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


## The 5 Planes of UX
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
| As a developer | I want to set up the project structure so that the application can run locally | - Create main Python script<br>- Add required imports<br>- Install dependencies<br>- Verify script runs | Script runs without errors | <img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want the application to save results to Google Sheets so that I can access them later | - Set up Google Sheets API<br>- Add credentials<br>- Connect using gspread<br>- Test spreadsheet access | Application connects successfully to the spreadsheet |<img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want a worksheet created for each run so that my data is organized by date | - Generate today’s date<br>- Open worksheet<br>- Create worksheet if missing | Worksheet appears automatically |<img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want to enter search criteria so that I can analyze relevant apartments | - Country input<br>- City input<br>- Rooms input<br>- Location input<br>- Budget input | Inputs are accepted correctly |<img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569">|
| As a user | I want invalid inputs rejected so that the program runs correctly | - Validate country<br>- Validate city<br>- Validate budget | Invalid values stop execution | <img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want the program to load apartment listings so that I can analyze the market | - Set up Selenium<br>- Open krisha.kz<br>- Wait for listings | Listings page loads successfully | <img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want the program to collect apartment data so that it can be analyzed | - Extract header<br>- Extract price<br>- Extract location<br>- Extract link<br>- Store data | Listings appear in the data structure | <img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want invalid or irrelevant listings removed so that the analysis is accurate | - Remove duplicates<br>- Filter by rooms<br>- Filter by location<br>- Clean prices<br>- Filter by budget | Only valid listings remain | <img width="100" height="500" src="https://github.com/user-attachments/assets/e03d9d01-51a9-40d7-8970-3551bfcdf569"> |
| As a user | I want apartments ranked by investment potential so that I can find good opportunities | - Calculate z-score<br>- Calculate liquidity score<br>- Calculate center score<br>- Calculate investment score<br>- Sort listings | Listings ranked by investment score | Must Have |
| As a user | I want the analysis results saved and properly formatted in Google Sheets so that I can easily review and compare properties | - Clear worksheet before writing new data<br>- Add header row<br>- Upload analyzed data<br>- Format header in bold<br>- Freeze header row<br>- Highlight top investment listings | Data is successfully written to Google Sheets<br>Header remains visible when scrolling<br>Top listings are highlighted | Must Have |
| As a user | I want property metrics calculated and unrealistic listings filtered out so that I can compare apartments using reliable market data | - Extract apartment size (sqm)<br>- Convert size values to numeric format<br>- Remove invalid or zero sizes<br>- Calculate price per m²<br>- Filter unrealistic price per m² values<br>- Implement IQR outlier filtering | Dataset includes size and price per m²<br>Invalid sizes removed<br>Extreme values filtered out | Should Have |
| As a user | I want a summary of the market so that I understand price trends | - Calculate average price<br>- Calculate average size<br>- Calculate average price per m² | Summary printed in terminal | Should Have |
| As a user | I want the application to support multiple countries and cities so that I can analyze real estate markets in different locations | - Support multiple countries<br>- Support multiple cities<br>- Create dynamic URL generation<br>- Validate supported locations | User can select different countries and cities | Could Have |
| As a user | I want the application to collect listings from multiple real estate websites so that I can get a more complete view of the market | - Design scraper structure for multiple sites<br>- Add support for additional websites<br>- Merge results into a single dataset | Data can be collected from more than one website<br>Results are combined into one dataset<br>Data format is consistent | Could Have |
| As a user | I want the application to analyze apartment images and district-level market statistics so that I can better evaluate investment opportunities | - Collect apartment images<br>- Implement AI image analysis<br>- Detect apartment features from images | Images can be processed by AI<br>Apartment features can be extracted from images<br>Results improve investment analysis | Could Have |


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
