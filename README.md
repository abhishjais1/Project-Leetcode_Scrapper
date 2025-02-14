# LeetCode Problem Finder

This project is a Flask-based web application that allows users to search for LeetCode problems using relevant keywords. It uses a custom search engine built with TF-IDF (Term Frequency-Inverse Document Frequency) to find and rank the most relevant LeetCode problem links.

---

## Features
- **Keyword-based Search:** Enter any keyword to get a list of relevant LeetCode problem links.
- **Relevance Ranking:** Problems are ranked based on TF-IDF scores, ensuring the most relevant questions appear first.
- **Web Scraping:** Utilizes Selenium to scrape LeetCode for problem links.
- **Preprocessing and Indexing:** Efficient preprocessing of problem descriptions, vocabulary creation, and inverted indexing for quick search and retrieval.

---

## How It Works
1. **Data Collection and Preparation:**
   - `scrape.py`: Scrapes LeetCode for problem links and stores them in a text file (`lc.txt`).
   - `cleaner.py`: Cleans the scraped data to remove duplicates and unwanted patterns.
   - `prepare.py`: 
     - Processes problem descriptions.
     - Builds vocabulary (`vocab.txt`) and calculates IDF values (`idf-values.txt`).
     - Constructs an inverted index (`inverted_index.txt`) for quick lookups.

2. **Search Engine:**
   - **TF-IDF Calculation:**
     - `get_tf_dict(term)`: Calculates term frequency for a given term.
     - `get_idf_value(term)`: Calculates inverse document frequency.
     - `calc_docs_sorted_order(q_terms)`: Computes relevance scores and sorts documents accordingly.
   - **Flask Web Application:**
     - Users can enter a search term through a form.
     - The backend processes the query, calculates relevance scores, and returns the top 20 relevant LeetCode problem links.

---

## Prerequisites
- Python 3.x
- Flask
- Flask-WTF
- Selenium
- ChromeDriver (Ensure it's compatible with your version of Google Chrome)

---

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/LeetCode-Problem-Finder.git
   cd LeetCode-Problem-Finder
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Download and set up ChromeDriver:**
   - Ensure ChromeDriver is placed in your system's PATH or the project directory.

---

## Usage

1. **Data Preparation:**
   - Run the scraping script to gather LeetCode problem links:
     ```bash
     python scrape.py
     ```
   - Clean the data:
     ```bash
     python cleaner.py
     ```
   - Prepare the documents, vocabulary, and inverted index:
     ```bash
     python prepare.py
     ```

2. **Start the Flask Application:**
   ```bash
   python app.py
   ```

3. **Access the Application:**
   - Open your browser and go to `http://127.0.0.1:5000`
   - Enter a keyword in the search box to get a list of relevant LeetCode problem links.

---

## Example Queries

- Searching for **"binary tree"** returns a list of LeetCode problems related to binary tree operations.
- Searching for **"dynamic programming"** shows relevant problems focused on dynamic programming concepts.

---

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

---

## Technologies Used

- **Flask**: Web framework for building the application.
- **Flask-WTF**: Form handling.
- **Selenium**: Web scraping.
- **BeautifulSoup**: HTML parsing.
- **TF-IDF Algorithm**: Ranking of relevant documents.

---

## Future Enhancements

- Implement caching to speed up repetitive queries.
- Enhance the ranking algorithm for better relevance.
- Improve the frontend UI for a better user experience.

---



## Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request with improvements or bug fixes.

---

## Contact
For questions or suggestions, please contact:
- **Your Name**: abhishek942a@gmail.com
- **GitHub**: abhishjais1
