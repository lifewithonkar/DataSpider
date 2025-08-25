🏦 TIAA Bank Loan Rates Scraper

📌 Project Overview

This project scrapes loan and mortgage rate data from financial websites (e.g., Bankrate) using Scrapy, and automates the scraping process using GitHub Actions.

🔄 Scrapy → Collects loan rate data (product, interest rate, APR, term, lender, date).

☁️ GitHub Actions → Runs the spider daily at a scheduled time.

💾 Storage → Saves data into JSON and CSV files (with option for S3 in future).



🚀 Features

Automated scraping of mortgage/loan rates.

Scheduled runs via GitHub Actions (daily at set IST time).

Data saved in CSV (historical data) and JSON (latest snapshot).

Easy to extend for cloud storage (AWS S3) or databases.



📂 Project Structure

loanrates-g5/

├── loanrates/                   # Main Scrapy project folder

│   ├── spiders/                 # All spiders & helper scripts

│   │   ├── data/                # Scraped data outputs

│   │   │   ├── bankrate.json    # Latest scraped data

│   │   │   ├── bankrates.csv    # Historical data (appended daily)

│   │   │   └── log/             # Logs folder

│   │   ├── append_json_to_csv.py# Script to append JSON to CSV

│   │   ├── bankrate_spider.py   # Main Scrapy spider

│   │   ├── __init__.py

│   │

│   ├── items.py                 # Item definitions for scraped fields

│   ├── middlewares.py           # Custom middlewares

│   ├── pipelines.py             # Data processing pipelines

│   ├── settings.py              # Scrapy project settings

│   └── __pycache__/

│

├── .github/workflows/ci.yml     # GitHub Actions workflow (automation)

├── requirements.txt             # Python dependencies

└── README.md                    # Project documentation



⚙️ Installation & Setup
1️⃣ Clone Repository
git clone https://github.com/lifewithonkar/spider.git
cd spider

2️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Run Scrapy Spider (locally)
python bankrate_loans.py


Output → bankrate_loans.json (latest snapshot)

Output → bankrate_rates_history.csv (appended daily history)



🛠️ Automation with GitHub Actions

Workflow runs daily at 10:30 AM IST.

Executes the Scrapy spider and updates JSON + CSV files.

Workflow file: .github/workflows/ci.yml



📌 Future Enhancements

Store scraped data in AWS S3.

Build a Django/Flask UI to display results.

Add user authentication for dashboard access.

Create data visualization (charts, trends, comparisons).
