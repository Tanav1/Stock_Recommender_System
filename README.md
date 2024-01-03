# Stock Recommender System

For our final project, we developed a recommender system that helps users find stocks similar to their selected stock from the S&P 500 index. This system simplifies the stock selection process by using important financial data to identify similar stocks, providing users with informative recommendations.

## Problem Statement

The stock market can be complex and challenging for investors to navigate. Choosing which stocks to invest in and understanding the relationships between stocks can be daunting, especially for those without expertise in financial analysis. We aimed to address this problem by creating a recommender system that recommends stocks similar to a user-selected stock, making investment decisions more accessible.

## How It Works

1. **Data Collection**: We collected financial data from two sources:
   - [S&P 500 Companies Financials](https://datahub.io/core/s-and-p-500-companies-financials)
   - [S&P 500 Companies Weightage](https://finasko.com/sp-500-companies-weightage/)

2. **Data Preprocessing**: We cleaned and merged the data, removing unnecessary columns and preparing it for analysis.

3. **Scoring Function**: We designed a scoring function to calculate the similarity between stocks based on several key financial factors, including sector, price/earnings ratio, dividend yield, earnings per share, market capitalization, price/book ratio, and stock weight in the S&P 500 index.

4. **Recommender Function**: Users can input the ticker symbol of a stock they own or are interested in. The system then computes a similarity score between this input stock and all other stocks in the S&P 500. It returns the top 20 stocks with the highest similarity scores.

5. **Output**: The system presents the results as a DataFrame, including the stock symbol, company name, sector, and similarity score.

## Example Usage

Here are some examples of how to use the recommender system:

```python
# Output 20 stocks similar to Facebook (FB)
facebook_df = test("FB", merged_df)
print(facebook_df)

# Output 20 stocks similar to Walmart (WMT)
walmart_df = test("WMT", merged_df)
print(walmart_df)

# Output 20 stocks similar to Nike (NKE)
nike_df = test("NKE", merged_df)
print(nike_df)

# Output 20 stocks similar to Procter & Gamble (PG)
pg_df = test("PG", merged_df)
print(pg_df)
