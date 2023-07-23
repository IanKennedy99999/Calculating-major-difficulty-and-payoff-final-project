# Calculating-major-difficulty-and-payoff-final-project

Overview
This Python script is designed to perform several tasks related to data extraction and analysis for various academic majors and job listings. The script leverages web scraping, API calls, and data manipulation to collect and store data in a local SQLite database. It also generates visualizations to analyze the collected data.

Dependencies
Before running the script, make sure you have the following dependencies installed:

Selenium
BeautifulSoup (bs4)
SQLite3
Pandas
Numpy
Matplotlib
Requests
You can install these dependencies using pip:

Copy code
pip install selenium beautifulsoup4 pandas numpy matplotlib requests
How to Use the Script
Download the script and place it in a folder.
Install the required dependencies using pip (as mentioned above).
Obtain necessary API keys and replace the placeholders in the script with your actual API keys. The placeholders to replace are indicated in angle brackets (e.g., <INSERT OPENAI API KEY>).
Ensure you have the appropriate web drivers (e.g., ChromeDriver) for Selenium. Update the chromedriver_path variable in the script to point to the correct driver path.
Create a new SQLite database file named "database.db" in the same folder as the script. The script will automatically create necessary tables in this database to store data.
Optionally, modify the list of majors and job titles in the items list inside the main() function, according to your desired data collection needs.
Script Functionality
atlasMajor(major): This function scrapes data from the University of Michigan's Atlas AI website to collect information about courses related to the specified major. It stores course data such as title, median grade, and evaluation scores in the SQLite database.

convertGrades(): This function converts letter grades to a 4.0 scale for all courses in the database. It updates the 'median_grade' column for each course.

salary(jobTupl): This function uses the Jooble API to search for job listings related to the specified job titles. It collects job data such as job title, location, snippet, salary, and company name, and stores it in the SQLite database.

GPTsalary(major): This function uses the OpenAI API (GPT-3) to generate a 5-bullet point list of job titles an individual with the specified major would normally have.

jobAvg(column_name): This function calculates the average value of the specified column ('salary' by default) for each unique major in the database. It generates a text file named 'output.txt' with the mean values and a bar plot visualizing the results.

majorAvg(column_name): This function calculates the average value of the specified column for each unique major in the database. It generates a text file named 'output.txt' with the mean values and a bar plot visualizing the results.

companyList(): This function retrieves a list of distinct company names from the jobs table in the database.

get_ticker(company_name): This function uses the Polygon.io API to get the stock ticker symbol for a given company name.

get_price_history(company_names): This function uses the Alpha Vantage API to retrieve historical stock price data for the given company names. It stores the data in the stocks table of the SQLite database.

plotStocks(): This function plots the historical stock close prices over time for each unique company in the stocks table.

Running the Script
To execute the script, simply run the main() function. The script will perform the defined tasks for each item in the items list, and you can observe the results in the database and generated visualizations.

Please note that some parts of the script (e.g., job salary data retrieval) may have usage limitations due to API rate limits or other restrictions, so the full functionality might require additional adjustments or API subscriptions. Additionally, some parts of the script may take some time to execute, depending on the amount of data collected and the API response times.

Important: Ensure that you have proper API keys and follow the terms of service for the APIs used in the script.
