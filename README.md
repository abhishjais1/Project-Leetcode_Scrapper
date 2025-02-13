# Leetcode Problems Finder

This project is a web application that allows users to search for relevant LeetCode problems using specific keywords. It efficiently returns a list of problem links that are most relevant to the entered search term.  

## Features  
- **Keyword Search:** Enter a keyword to get a list of related LeetCode problems.  
- **Relevance Ranking:** Results are ranked using TF-IDF to ensure the most relevant problems appear first.  
- **Flask Web Interface:** Simple and user-friendly search interface built with Flask.  

## Tech Stack  
- **Backend:** Python, Flask  
- **Web Scraping:** Selenium, BeautifulSoup  
- **Algorithm:** TF-IDF (Term Frequency-Inverse Document Frequency)  

## Project Structure  
```
Leetcode-Scraping/
│
├── qData/                 # Contains scraped LeetCode data  
│   ├── cleaner.py         # Cleans and processes scraped data  
│   ├── scrape.py          # Scrapes LeetCode problem links  
│   └── ...  
│
├── templates/             # HTML templates for the Flask app  
│
├── app.py                 # Main Flask application file  
├── prepare.py             # Prepares data for search indexing  
├── vocab.txt              # Vocabulary for TF-IDF calculations  
├── idf-values.txt         # IDF values for terms  
└── README.md               # Project documentation  
```

## Installation  
1. Clone the repository:  
    ```bash
    git clone <repository-url>
    cd Leetcode-Scraping
    ```  
2. Install required packages:  
    ```bash
    pip install -r requirements.txt
    ```  
3. Start the Flask server:  
    ```bash
    python app.py
    ```  
4. Access the application at `http://localhost:5000`.  

## How It Works  
- The scraper collects problem links from LeetCode.  
- Data is processed and indexed using TF-IDF.  
- When a user enters a search term, the application calculates relevance scores and displays the most relevant problem links.  

## Live Demo  
Check out the live version: [LeetCode Scraper](https://leetcode-scrapper-pl5z.onrender.com)  

