# IS 477 Status Report
#### By Aadhya Mavani & Brock Hartweger

## Task Progress Update
##### Project Plan: 
The project plan was written and submitted on March 12 as ProjectPlan.md. This plan was then reviewed and approved with no issues flagged, other than no tag and release. 
##### Data Acquisition:
##### Data Cleaning:
##### Data Integration:
##### Exploratory Analysis & Visualizations: 
We coded the player-season level aggregation, summary statistics, supporting trend visualizations, and then the predicted vs. actual visualization. The game-level batting data was grouped by player and year to produce season totals for home runs, at-bats, hits, doubles, triples, strikeouts, etc. Then, players with fewer than 50 at-bats in a season were filtered out to reduce noise from part-time appearances. Following this, batting average was produced as a new column. Yearly averages across qualifying players were then computed and visualized across three panels, being average home runs per player-season, average batting average, and average strikeouts.
##### Regression Model: 
We built the linear regression model to address Research Questions 1 and 3. The model uses at-bats, games played, doubles, and triples as features to predict home run totals at the player-season level. The dataset was split 80/20 into training and test sets. Then, the model performance was evaluated using R² and RMSE on both the training and test sets, and coefficients were printed for each feature to assess variable importance. Finally, a predicted vs. actual scatter plot was generated to visually assess the model fit.

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
For the most part, the project has followed the original plan without any major deviations. Our project plan was approved without any issues flagged during grading, so no structural changes were required. One deviation I see from the original timeline is that we received more time to work on this status report, since the due date changed to April 14th from March 31st. Given that, we were able to include the linear regression model in this report as well. Furthermore, one of the gaps we identified in the project plan was that we had not decided on a minimum number of at-bats required for a player to be included in our analysis. Since this was to be determined during our cleaning phase, we decided to filter players to a minimum of 50 at-bats per season to exclude pitchers and part-time players whose low plate appearance totals could potentially skew model results. In terms of the research questions, datasets, and our analysis methods, though, no changes were made. 

## Challenges and Issues Encountered

## Individual Contribution Summaries
##### Brock:
For this milestone, I was responsible for data acquisition, cleaning, and integration. I obtained a dataset with 5.7 million MLB players' batting seasons spanning from 1878 to 2020. While cleaning the data, I noticed there were 746,000 rows of fully empty data. There were also numerous corrupted column headers that, while filtering out rows that had players with 0 at-bats in a given season. Lastly, with the individual player data, I imputed missing values (NAN) with the value 0 where necessary. Likewise, the team dataset was filtered the same way by filling in missing values, especially in the win/loss and statistical columns. Thus, both datasets were segregated into three historical eras: Early (1898-1950), Mid (1951-1990), and Contemporary (1991-present). Lastly, both datasets were aggregated by the year/date column, enabling analysis across both datasets.
##### Aadhya: 
For the current milestone, I was responsible for the exploratory analysis, visualizations, and the regression model. I wrote the player-season aggregation code, grouping game-level batting records by player and year and computing season totals for all key batting statistics. I applied the 50 at-bat filter to qualify the dataset for analysis and derived the batting average as a new column. I then computed yearly averages across qualifying players and built the three-panel trend visualization covering home runs, batting average, and strikeouts over time. I also built the linear regression model using at-bats, games played, doubles, and triples as predictors of home run totals, evaluated its performance on a held-out test set using R² and RMSE, and generated the predicted vs. actual scatter plot. Finally, I formatted the full notebook with markdown section headers and descriptions to improve readability and structure.
