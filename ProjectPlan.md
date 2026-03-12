# IS 477 Project Plan
### By Aadhya Mavani & Brock Hartweger

## Overview
Our project aims to analyze how Major League Baseball has evolved over time using a historical baseball dataset. Using datasets on each player’s individual performance during a season, our group can study long-term trends in offensive production along with how player statistics have progressed throughout the decades. By examining statistics such as hits, home runs, batting averages, and other key metrics, we can research how player development and the style of the game have molded into the game we know today.

Our plan is to clean and organize a dataset based on every MLB player’s season. After prepping the dataset, our group will analyze key performance statistics through variables such as home runs, batting average, home run percentage, and other variables, identifying trends throughout the decades. Using these variables, we will create summary statistics, visualizations, and regression models to predict the future of the game and what it would look like for the next decade. Overall, these models will help our group explore many different possibilities and give us data-driven insights for the next decade.

## Team
#### Brock (Researcher)
Responsible for ensuring data is prepped and ready to be implemented in the model. As well as determining which variables will be used to measure different eras of the MLB.

#### Aadhya (Modeler)
Responsible for implementation of machine learning models, visualizations, and summary statistics in order to analyze player trends and statistics.

## Research Questions 

1.) What is the relationship between at-bats and home runs after controlling for doubles, triples, and games played? How well does this model generalize to new data? 

2.) How do at-bats, games played, doubles, and triples relate to the likelihood of a player hitting 10 or more home runs in a season? How well does a classifier built on this relationship perform on unseen data?

3.) How accurately can at-bats, games played, doubles, and triples predict the number of home runs a player will hit in a season, and which of these variables contributes most to that prediction?


## Datasets

#### Retrosheet Baseball CSV Files (https://www.retrosheet.org/downloads/othercsvs.html)
Retrosheet is a non-profit organization that compiles historical MLB game data. From their CSV download portal, we will use two files: batting.csv, which contains game-level batting statistics for every player in every game from 1898–2025, and allplayers.csv, which contains biographical and team-season information for all players. These files are freely available for non-commercial use under Retrosheet's data license. We will aggregate the game-level batting records into season-level totals per player, producing metrics such as total home runs, at-bats, doubles, triples, and games played per season. The primary identifiers in this dataset are a player ID, team abbreviation, and season year.

#### Lahman’s Baseball Database via OpenIntro (https://www.openintro.org/data/index.php?data=mlb_teams)
The second dataset is sourced from Lahman's Baseball Database, a widely cited repository of historical MLB statistics. OpenIntro hosts a cleaned subset of this data (mlb_teams) containing 2,784 team-season records spanning multiple decades, with 41 variables including wins, losses, runs scored, home runs, strikeouts, attendance, and postseason outcomes. This dataset is available under an open license for educational use. The primary identifiers are team name/abbreviation and season year.

These two datasets will be integrated using team abbreviation and season year as shared keys, connecting individual player batting statistics (aggregated to the team-season level) with team outcomes such as wins, losses, and runs scored. Analysis will focus on 1950–2025, where data completeness is highest.

## Timeline
| Timeline | Task | Description | Due Date | Assigned To |
|----------|------|-------------|----------|-------------|
| Phase 1 | Project Plan | Write and submit ProjectPlan.md | March 12 | Both |
| Phase 2 | Data Acquisition & Exploration | Download Retrosheet CSV’s and mlb_teams dataset | March 13 | Brock |
| Phase 3 | Data Cleaning | Handle missing values, outliers, inconsistent team abbreviations across dataset | March 24 | Brock |
| Phase 4 | Data Integration | Aggregate batting.csv to season level, join with mlb_teams on team + year | March 26 | Brock |
| Phase 5 | Exploratory Analysis & Visualization | Summary statistics and visualizations of offensive trends across decades | March 28 | Aadhya |
| Phase 6 | Status Report | Write and submit interim status report | March 31 | Both |
| Phase 7 | Regression Model | Build linear regression model for home run prediction (Q1 and Q3) | April 10 | Aadhya |
| Phase 8 | Classification Model | Build classifier for 10+ HR prediction (Q2) | April 17 | Aadhya |
| Phase 9 | Model Evaluation | Evaluate model performance on test data, interpret variable importance | April 24 | Aadhya |
| Phase 10 | Workflow Automation | Build end-to-end reproducible Python workflow | April 27 | Both |
| Phase 11 | Final Report & Documentation | Write project report, metadata documentation, provenance notes | May 1 | Both |
| Phase 12 | Final Submission | GitHub release, tag, and Canvas submission | May 3 | Both |

## Constraints

#### Data Completeness
While Retrosheet's records span 1898–2025, data completeness improves significantly in later decades. Earlier seasons in our 1950–2025 window may have missing or incomplete game-level records, which could introduce bias when aggregating to season-level totals. Players with very few at-bats or partial seasons due to injury may also skew model results and will likely need to be filtered out.

#### Data Integration Challenges
Retrosheet and Lahman were compiled independently and may use different team abbreviations or naming conventions, requiring careful reconciliation before joining on team and year. Franchise relocations and expansions add further complexity. 

#### Model Limitations
Our models rely solely on counting statistics and do not account for contextual factors like ballpark dimensions, or player injuries, which could meaningfully affect model accuracy. 

#### Licensing
Retrosheet data is free for non-commercial use and Lahman's Baseball Database is available under a Creative Commons Attribution-ShareAlike license. Both are appropriate for academic use, but redistribution of raw data files should be handled carefully.

## Gaps
We have not yet determined the extent to which Retrosheet and Lahman use different team name codes, which may require us to manually match them up before the datasets can be joined. We also have not decided on a minimum number of at-bats required for a player to be included in our analysis, which will be worked out during the cleaning phase. It is also unclear whether we need to adjust statistics to account for how different the game was in different decades. To elaborate, scoring levels and rules were very different in 1950 compared to 2020, which could make raw numbers hard to compare directly. Finally, we have not yet explored whether creating new variables from existing ones, or trying different types of models, would improve our results. Both of these will be looked at during the analysis phase.

