# Apify Google Places Lead Scraper with Quality Filtering to Google Sheets

An automated n8n workflow that searches for businesses on Google Places, filters leads based on quality metrics, and saves the results directly to Google Sheets.

## Overview

This workflow automates the process of:
1. **Searching** Google Places for businesses using custom search queries
2. **Filtering** results based on quality criteria (rating, review count, website presence)
3. **Formatting** the extracted data
4. **Saving** leads directly to a Google Sheets document

## Features

- 🔍 **Google Places Scraping**: Uses Apify's Google Places crawler to gather business information
- ⭐ **Quality Filtering**: Automatically filters leads based on:
  - Minimum rating of 4.2 or higher
  - Minimum 20 customer reviews
  - Must have a website
- 📊 **Google Sheets Integration**: Direct export to Google Sheets for easy analysis
- 🚀 **API Rate Limiting**: Built-in 90-second delays to prevent API overload
- 🔄 **Batch Processing**: Process multiple search queries in a single workflow run

## Workflow Components

### Nodes

| Node | Purpose |
|------|---------|
| **Manual Trigger** | Initiates the workflow |
| **Search Query Control Panel** | Define the search queries to execute |
| **Split Into Individual Searches** | Splits multiple queries into separate executions |
| **Prevent API Overload** | 90-second delay between API calls |
| **Run Apify & Get Results** | Executes Apify Google Places crawler API |
| **Filter Quality Leads** | Filters results based on quality criteria |
| **Format Output Data** | Transforms raw data into a structured format |
| **Save to Google Sheets** | Appends or updates data in Google Sheets |

## Configuration

### 1. Search Queries

Edit the **Search Query Control Panel** node to modify your search queries:

```json
{
  "queries": [
    "plumber in Phoenix Arizona",
    "plumber in Dallas Texas"
  ]
}
