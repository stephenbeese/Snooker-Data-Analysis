# How has the professional snooker tour grown internationally since its height of popularity during the 1980s?

**This project** is a comprehensive data analysis tool designed to streamline data exploration, analysis and visualisation for snooker match results between 1982 and 2020. The tool supports multiple data formats and provides an intuitive interface for both novice and expert data scientists.

The project aims to analyse historical professional snooker data to understand how the sport has evolved internationally since its peak in the 1980s. I will be focusing on player demographics, tournament distribution and prize money trends.


## Dataset Content
* My dataset consists of 4 csv files
    * matches.csv (193530 rows × 13 columns)
    * tournaments.csv (2720 rows × 11 columns)
    * scores.csv (934716 rows × 5 columns)
    * players.csv (13640 rows × 6 columns)

* These tables are all related to eachother through the use of primary and foreign keys.

* These tables are big and contain a lot of rows.

* I plan to merge these tables into one master table, this will make it easier to analyse and gain insights.

* You can find the Kaggle link to this dataset <a href="https://www.kaggle.com/datasets/rusiano/snooker-data-19822020" target="_blank" rel="noopener">here</a>


## Business Requirements
The main business requirement is to evaluate how professional snooker has evolved internationally since its peak popularity in the 1980s. This includes:

* Measuring the growth in tournaments held outside the UK.
* Tracking the participation and success of international players.
* Analysing whether this global expansion has impacted prize money and competitiveness.
* Providing clear, interactive visualisations to help stakeholders quickly understand trends.


## Hypothesis and how to validate?
* My hypothesis is that the sport has grown globaly, due to the rise international players which has helped produce more tournaments outside of the UK making the sport more accessible for everyone around the world.

* To attempt to validate my hypothesis, I will look at the data trends over the 38 year period I have data for.

* I will look at:
    * The number of players internationally per season
    * The number of international tournaments per season
    * How the average prize money per tournament has been affected by this
    * The number of players reaching the latter stages of tournaments(Quarter-Final, Semi-Final and Final) and whether that has a knock on effect of more popularity in other parts of the world.

I feel that this data will give me a good insight into how the sport has grown globaly. 


## Project Plan
1. **Gather the snooker data**
2. **Clean the data**
3. **Merge data into useful tables**

   * **Table 1 (Matches Full)**

     | Match\_id | tournament\_id | date | season | year | tournament\_name | stage (QF, SF, F) | best\_of | player1\_name | player1\_country | player2\_name | player2\_country | score1 | score2 | tournament\_country | tournament\_prize | match\_winner | winner\_country | is\_international\_match | is\_international\_tournament | number\_of\_centures |
     | --------- | -------------- | ---- | ------ | ---- | ---------------- | ----------------- | -------- | ------------- | ---------------- | ------------- | ---------------- | ------ | ------ | ------------------- | ----------------- | ------------- | --------------- | ------------------------ | ----------------------------- | -------------------- |
4. **Analyse Data**
* **Data Management:** Data was ingested from multiple CSV files and merged into a master table via primary/foreign keys (tournament\_id, player\_id, match\_id).
* **Processing:** Used Pandas for cleaning, type conversion, and feature engineering (e.g., `is_international_match` flag, match stage classification).
* **Analysis:** Grouped data by season, region, and match stage to identify trends.
* **Interpretation:** Created interactive Plotly visualisations to reveal patterns in UK vs international growth, match stages, and player wins.
* **Methodology:** Chose exploratory data analysis (EDA) to uncover hidden relationships in historical data before applying structured visual comparisons.

## The rationale to map the business requirements to the Data Visualisations
* **Requirement:** Understand global growth → **Visualisation:** Line charts comparing UK vs International matches over time.
* **Requirement:** Track international player success → **Visualisation:** Stacked bar charts showing UK vs International final winners per season.
* **Requirement:** Assess latter-stage competitiveness → **Visualisation:** Multi-line charts showing Quarter-final, Semi-final, and Final appearances for UK vs International players.
* **Requirement:** Historical tournament distribution → **Visualisation:** Grouped bar charts showing tournament counts by region per season.

## Analysis techniques used
* **Grouping & Aggregation:** Pandas `groupby` for summarising trends by season, stage, and country.
* **Feature Engineering:** Created binary flags for UK vs International matches, mapped Boolean values to readable labels.
* **Visual Analysis:** Used Plotly for interactive exploration and enabling filtering.
* **Limitations:** Data covers only 1982–2020, so post-2020 developments aren’t reflected. Some missing player country data could slightly skew results.
* **Alternatives:** Could have used statistical modelling to predict future international growth, but focus remained on historical trends.
* **Generative AI Use:** Used AI to refine analysis questions, improve plotting code efficiency, and structure the README narrative.

## Ethical considerations
* **Bias:** Dataset is historical and may reflect earlier UK bias in tournament hosting and participation. Addressed by explicitly showing UK vs International comparisons.
* **Privacy:** Data is public and non-sensitive, containing no personal identifiers beyond professional player names.
* **Fairness:** All analysis treats UK and international players equally, without weighting one group over the other.

## Key Findings
* **UK dominance** in the early decades – From the early 1980s through the mid-1990s, UK-based matches vastly outnumbered international ones.

* **Steady international growth** – Since the early 2000s, international matches and player participation have risen steadily.

* **Narrowing performance gap** – International players now reach later stages (QF/SF/F) more frequently, especially post-2010.

* **Occasional international surges** – Some seasons saw international tournament counts match or exceed UK counts.

* **Prize money impact** – The globalisation of snooker correlates with growth in prize funds for both UK and international events.


## Development Roadmap
* **Challenges:**
  * Merging large datasets while preserving relational integrity.
  * Dealing with missing or inconsistent country data for players.
* **Strategies:**
  * Used incremental merging and checks after each join.
  * Filled missing countries via cross-referencing other matches.
* **Next Steps:**
  * Incorporate post-2020 data for more recent trends.
  * Extend analysis to prize money inflation-adjusted comparisons.
  * Explore machine learning models to forecast future international growth. 

## Main Data Analysis Libraries
* **Pandas** – Data cleaning, aggregation, feature creation.
* **NumPy** – Efficient numeric operations.
* **Plotly Express** – Interactive line charts, bar charts, filtering controls. Example: multi-line chart for QF/SF/F matches by region.
* **Seaborn** – Static grouped bar charts for comparison snapshots.
* **Matplotlib** – Fine-tuning plots and labels when needed and static plots.

## Unfixed Bugs
* No Known Bugs

## Credits 

### Content 

* **Dataset Source**: [Snooker Data 1982-2020](https://www.kaggle.com/datasets/rusiano/snooker-data-19822020) (Kaggle)

* **Assistance**: ChatGPT, GitHub Copilot (code structuring & README drafting)
