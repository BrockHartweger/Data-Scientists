# IS 477 Status Report
#### By Aadhya Mavani & Brock Hartweger

## Task Progress Update
##### Project Plan: 
The project plan was written and submitted on March 12 as ProjectPlan.md. This plan was then reviewed and approved with no issues flagged, other than no tag and release. 
##### Data Acquisition:
The primary dataset consists of 5.7 million rows, and is split into 21,000 individual CSV files representing each MLB player’s season. This data spans from 1898 to the present day, encompassing almost every single MLB player that has ever played. A secondary dataset consists of each team's statistics for a given season and encompasses data from 1876 to 2020. Both datasets were cleaned using the pandas library in Python.
##### Data Cleaning:
The batting data required significant preprocessing before data can be integrated. There were 764,000 rows of empty row data that needed to be removed, as well as faulty header/column variables, reducing rows to four million. Missing statistical values were imputed with the value 0 where necessary. The last preprocessing step needed for the batting was linking 21,000 individual batting CSVs into one. The team dataset required almost no cleaning besides some missing values needing to be filled with 0. Both datasets were then validated to make sure there were no missing values or faulty data being faulty. 
##### Data Integration:
Both datasets were segregated into three eras: Early (1898–1950), Mid (1951–1990), and Contemporary (1991–present). This is so our group can run analysis on each era of baseball and see how the game has evolved on each different variable, such as home run. 
##### Exploratory Analysis & Visualizations: 
We coded the player-season level aggregation, summary statistics, supporting trend visualizations, and then the predicted vs. actual visualization. The game-level batting data was grouped by player and year to produce season totals for home runs, at-bats, hits, doubles, triples, strikeouts, etc. Then, players with fewer than 50 at-bats in a season were filtered out to reduce noise from part-time appearances. Following this, batting average was produced as a new column. Yearly averages across qualifying players were then computed and visualized across three panels, being average home runs per player-season, average batting average, and average strikeouts.
##### Regression Model: 
We built the linear regression model to address Research Questions 1 and 3. The model uses at-bats, games played, doubles, and triples as features to predict home run totals at the player-season level. The dataset was split 80/20 into training and test sets. Then, the model performance was evaluated using R² and RMSE on both the training and test sets, and coefficients were printed for each feature to assess variable importance. The model achieved an R² of 0.4932 on the test set with an RMSE of 6.2383, and doubles had the strongest positive effect on HR prediction with a coefficient of 0.3258, while triples showed a negative relationship at -0.7813.

## Updated Timeline
| Task | Description | Due Date | Assigned To | Status |
|------|-------------|----------|-------------|--------|
| Project Plan | Write and submit ProjectPlan.md | March 12 | Both | Complete |
| Data Acquisition & Exploration | Download Retrosheet CSVs and mlb_teams dataset | March 13 | Brock | Complete |
| Data Cleaning | Handle missing values, outliers, inconsistent team abbreviations across dataset | March 24 | Brock | Complete |
| Data Integration | Aggregate batting.csv to season level, join with mlb_teams on team + year | March 26 | Brock | Complete |
| Exploratory Analysis & Visualization | Summary statistics and visualizations of offensive trends across decades | March 28 | Aadhya | Complete |
| Regression Model | Build linear regression model for home run prediction (Q1 and Q3) | April 10 | Aadhya | Complete |
| Status Report | Write and submit interim status report | April 14 | Both | Complete |
| Classification Model | Build classifier for 10+ HR prediction (Q2) | April 17 | Aadhya | Upcoming |
| Model Evaluation | Evaluate model performance on test data, interpret variable importance | April 24 | Aadhya | Upcoming |
| Workflow Automation | Build end-to-end reproducible Python workflow | April 27 | Both | Upcoming |
| Final Report & Documentation | Write project report, metadata documentation, provenance notes | May 1 | Both | Upcoming |
| Final Submission | GitHub release, tag, and Canvas submission | May 3 | Both | Upcoming |

## Changes to the Project Plan
For the most part, the project has followed the original plan without any major deviations. Our project plan was approved without any issues flagged during grading, so no structural changes were required. One deviation I see from the original timeline is that we received more time to work on this status report, since the due date changed to April 14th from March 31st. Given that, we were able to include the linear regression model in this report as well. 

In the exploratory analysis section, one of the gaps we identified in the project plan was that we had not decided on a minimum number of at-bats required for a player to be included in our analysis. Since this was to be determined during our cleaning phase, we decided to filter players to a minimum of 50 at-bats per season to exclude pitchers and part-time players whose low plate appearance totals could potentially skew model results. Also, in the trend charts that were outputted, the year range 1898–2025 was chosen rather than the originally planned 1950–2025, since the full historical data was already available and provided richer context.

## Challenges and Issues Encountered
One of the issues that came up was dealing with a dataset that consisted of 5.7 million rows, distributed across over 21,000 individual datasets, one per player, which needed to be combined into a single dataset. The file that resulted from this came out to be 565MB. Instead of dealing with one large dataset, it needed to be sliced into numerous datasets to account for the large volume, each about 500,000 rows. This challenge added significant time in the preprocessing stage before any meaningful analysis could begin.
## Individual Contribution Summaries
##### Brock:
For this milestone, I was responsible for data acquisition, cleaning, and integration. I obtained a dataset with 5.7 million MLB players' batting seasons spanning from 1878 to 2020. While cleaning the data, I noticed there were 746,000 rows of fully empty data. There were also numerous corrupted column headers that, while filtering out rows that had players with 0 at-bats in a given season. Lastly, with the individual player data, I imputed missing values (NAN) with the value 0 where necessary. Likewise, the team dataset was filtered the same way by filling in missing values, especially in the win/loss and statistical columns. Thus, both datasets were segregated into three historical eras: Early (1898-1950), Mid (1951-1990), and Contemporary (1991-present). Lastly, both datasets were aggregated by the year/date column, enabling analysis across both datasets.
##### Aadhya: 
For the current milestone, I was responsible for the exploratory analysis, visualizations, and the regression model. I wrote the player-season aggregation code, grouping game-level batting records by player and year and computing season totals for all key batting statistics. I applied the 50 at-bat filter to qualify the dataset for analysis and derived the batting average as a new column. I then computed yearly averages across qualifying players and built the three-panel trend visualization covering home runs, batting average, and strikeouts over time. I also built the linear regression model using at-bats, games played, doubles, and triples as predictors of home run totals, evaluated its performance on a held-out test set using R² and RMSE, and generated the predicted vs. actual scatter plot. Finally, I formatted the full notebook with markdown section headers and descriptions to improve readability and structure.
