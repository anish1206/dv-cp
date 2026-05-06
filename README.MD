# Defining "Success" in the Film Industry

For my analysis, I am dividing "Success" into two primary categories:

---

## 1. Commercial Success (Financial Viability)
A successful movie for a new filmmaker is one that makes its money back and generates a profit. To measure this, I will create two new calculated metrics based on the `revenue` and `budget` columns in my dataset.

*   **Profit:** The absolute amount of money made after costs.
    *   *My Formula:* `Profit = Revenue - Budget`
*   **Return on Investment (ROI):** I consider this to be the **most crucial metric** for a new filmmaker. A $10,000 movie that makes $100,000 has an incredible ROI and is a massive success, even if the absolute profit is tiny compared to a Marvel movie. 
    *   *My Formula:* `ROI (%) = ((Revenue - Budget) / Budget) * 100`

**My Success Criteria:** I will define a commercially successful film in this dataset as one having an **ROI > 100%** (meaning it at least doubled its production budget).

---

## 2. Audience and Critical Success
Financial success is great, but a filmmaker's long-term career relies on making movies that people actually want to watch and recommend. To measure this, I will look at audience engagement.

*   **Audience Rating:** I'll measure this using the `vote_average` column.
*   **Statistical Significance:** I realized that a movie with a 10/10 rating but only 2 votes is not a real success; it's just an anomaly. To fix this, I need to use the `vote_count` column to filter out movies that nobody watched.
*   **Cultural Footprint:** I will also look at the `popularity` column to see how much engagement and trending value the movie had.

**My Success Criteria:** I will define a critically successful film as having a **`vote_average` >= 7.0**, but only if it meets a minimum threshold of **`vote_count` > 100**. This ensures the ratings I analyze are statistically reliable.

---

## My "Target Profile" 
When I start building my visualizations and mining the dataset for insights, I will be hunting for patterns, genres, and movie characteristics that fall into the Sweet Spot. 

Ultimately, the goal of my Exploratory Data Analysis (EDA) is to find out what types of movies achieve **both**:
1. High ROI (Low financial risk, high reward)
2. High Vote Average (Loved by the audience)

### Columns I Need for This Phase
To measure the criteria I set above, I will isolate and clean the following columns from my dataset during the preprocessing stage:
*   `budget` *(I must filter out rows where budget is 0)*
*   `revenue` *(I must filter out rows where revenue is 0)*
*   `vote_average`
*   `vote_count` *(I will drop rows where this is < 100)*
*   `popularity`