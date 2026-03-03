```text
██████╗ ███████╗ █████╗ ██╗
██╔══██╗██╔════╝██╔══██╗██║
██████╔╝█████╗  ███████║██║
██╔══██╗██╔══╝  ██╔══██║██║
██║  ██║███████╗██║  ██║███████╗
╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚══════╝

███████╗███████╗████████╗ █████╗ ████████╗███████╗
██╔════╝██╔════╝╚══██╔══╝██╔══██╗╚══██╔══╝██╔════╝
█████╗  ███████╗   ██║   ███████║   ██║   █████╗
██╔══╝  ╚════██║   ██║   ██╔══██║   ██║   ██╔══╝
███████╗███████║   ██║   ██║  ██║   ██║   ███████╗
╚══════╝╚══════╝   ╚═╝   ╚═╝  ╚═╝   ╚═╝   ╚══════╝

 █████╗ ██████╗ ██████╗
██╔══██╗██╔══██╗██╔══██╗
███████║██████╔╝██████╔╝
██╔══██║██╔═══╝ ██╔═══╝
██║  ██║██║     ██║
╚═╝  ╚═╝╚═╝     ╚═╝
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

















## Reminders

- Your code must be placed in the `run.py` file
- Your dependencies must be placed in the `requirements.txt` file
- Do not edit any of the other files or your code may not deploy properly

## Creating the Heroku app

When you create the app, you will need to add two buildpacks from the _Settings_ tab. The ordering is as follows:

1. `heroku/python`
2. `heroku/nodejs`

You must then create a _Config Var_ called `PORT`. Set this to `8000`

If you have credentials, such as in the Love Sandwiches project, you must create another _Config Var_ called `CREDS` and paste the JSON into the value field.

Connect your GitHub repository and deploy as normal.

## Constraints

The deployment terminal is set to 80 columns by 24 rows. That means that each line of text needs to be 80 characters or less otherwise it will be wrapped onto a second line.

---

Happy coding!
