# Customer Sentiment Analysis - Flipkart iPhone 16 (128GB)
***
## 1. Project Overview

This project focuses on conducting a comprehensive **Customer Sentiment Analysis** for the **iPhone 16 128GB** model, using publicly available product reviews from the Flipkart e-commerce platform.

The primary objective was to act as a Data Analyst to gauge public perception, evaluate customer reactions, and derive actionable insights regarding the product's overall sentiment (Positive, Negative, or Neutral). These insights are crucial for product management, decision-making, and identifying areas for customer experience improvement.

## 2. Dataset and Data Collection

The raw data was collected via a web scraping process targeting the product review pages for the iPhone 16 (128GB) on Flipkart.

* **Source:** Flipkart Product Reviews
* **Methodology:** Web Scraping using **requests** and **BeautifulSoup**
* **Volume:** **400** customer reviews were successfully scraped and analyzed.
* **Key Data Points Captured:** Username, Rating (1-5 stars), Review Title, and Full Review Text.

## 3. Methodology and Analysis Workflow

The project followed a standard data science pipeline, from data acquisition to insight generation:

### Data Cleaning and Preprocessing

1.  **Data Integrity:** Checked for and removed duplicate entries. All 400 records were unique.
2.  **Missing Value Handling:** Verified columns for completeness (no missing values were found).
3.  **Data Type Conversion:** The `rating` column was converted from an object to a numeric data type.
4.  **Text Normalization:** Review titles and text were cleaned by removing extra spaces and converting all text to lowercase.

### Sentiment Analysis

Sentiment analysis was performed using the **TextBlob** library, which generates a polarity score (ranging from -1 for negative to +1 for positive) for each text entry.

1.  **Polarity Calculation:** Individual polarity scores were generated for both the `r_title` and `r_text`.
2.  **Average Polarity:** An average polarity score (`avg_polarity`) was calculated from the title and text scores.
3.  **Sentiment Classification:** Reviews were classified into sentiment categories based on the average polarity score:
    * **Positive:** `avg_polarity` ≥ 0.1
    * **Negative:** `avg_polarity` < 0.1

## 4. Key Findings and Insights

### Sentiment Distribution

The analysis revealed an overwhelmingly positive sentiment towards the iPhone 16 (128GB) model:

| Sentiment Type | Count | Percentage (%) |
| :--- | :--- | :--- |
| **Positive** | 393 | 98.25% |
| **Negative** | 7 | 1.75% |

This distribution suggests a high level of satisfaction among the customers who left reviews on Flipkart.

### Rating vs. Textual Sentiment Correlation

The relationship between the numerical star rating and the calculated average textual sentiment was investigated:

* **Correlation Coefficient:** Approximately **0.018** (Pearson correlation coefficient).
* **Interpretation:** The extremely low correlation indicates **no significant linear relationship** between the star rating and the written sentiment. This suggests that a user's numerical rating does not always consistently align with the positivity or negativity expressed in their review text, highlighting the value of textual analysis beyond simple star ratings.

### Review Length vs. Sentiment

The correlation between the total review length (words) and the average polarity score was examined to see if longer reviews expressed stronger sentiments.

* **Correlation Coefficient:** Approximately **-0.118**.
* **Interpretation:** This weak negative correlation suggests that as review length increases, the average sentiment polarity slightly tends to decrease, but the relationship is not significant.

## 5. Technology Stack

* **Programming Language:** Python
* **Data Manipulation and Analysis:**
    * `pandas`
    * `numpy`
* **Web Scraping:**
    * `requests`
    * `BeautifulSoup`
* **Natural Language Processing (NLP):**
    * `TextBlob`
* **Data Visualization:**
    * `matplotlib.pyplot`
    * `seaborn`
    * `WordCloud` (for keyword frequency visualization)
