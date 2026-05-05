# IS 477 Final Project Report (How has the Game of Baseball Evolved?)
By Aadhya Mavani & Brock Hartweger
# Summary: (275 Words / 500-600)
Our project aims to analyze how Major League Baseball has evolved over time using a historical baseball dataset. Using datasets on each player’s individual performance during a season, our group can study long-term trends in offensive production along with how player statistics have progressed throughout the decades. By examining statistics such as hits, home runs, batting averages, and other key metrics, we can research how player development and the style of the game have molded into the game we know today.

Our plan is to clean and organize a dataset based on every MLB player’s season. After prepping the dataset, our group will analyze key performance statistics through variables such as home runs, batting average, home run percentage, and other variables, identifying trends throughout the decades. Using these variables, we will create summary statistics, visualizations, and regression models to predict the future of the game and what it would look like for the next decade. Overall, these models will help our group explore many different possibilities and give us data-driven insights for the next decade.
# Research Questions:
1.) What is the relationship between at-bats and home runs after controlling for doubles, triples, and games played? How well does this model generalize to new data?

2.) How do at-bats, games played, doubles, and triples relate to the likelihood of a player hitting 10 or more home runs in a season? How well does a classifier built on this relationship perform on unseen data?

3.) How accurately can at-bats, games played, doubles, and triples predict the number of home runs a player will hit in a season, and which of these variables contributes most to that prediction?
# Data Profile: (224 Words / 2000)
Retrosheet Baseball CSV Files (https://www.retrosheet.org/downloads/othercsvs.html)
Retrosheet is a non-profit organization that compiles historical MLB game data. From their CSV download portal, we will use two files: batting.csv, which contains game-level batting statistics for every player in every game from 1898–2025, and allplayers.csv, which contains biographical and team-season information for all players. These files are freely available for non-commercial use under Retrosheet's data license. We will aggregate the game-level batting records into season-level totals per player, producing metrics such as total home runs, at-bats, doubles, triples, and games played per season. The primary identifiers in this dataset are a player ID, team abbreviation, and season year.

Lahman’s Baseball Database via OpenIntro (https://www.openintro.org/data/index.php?data=mlb_teams)
The second dataset is sourced from Lahman's Baseball Database, a widely cited repository of historical MLB statistics. OpenIntro hosts a cleaned subset of this data (mlb_teams) containing 2,784 team-season records spanning multiple decades, with 41 variables including wins, losses, runs scored, home runs, strikeouts, attendance, and postseason outcomes. This dataset is available under an open license for educational use. The primary identifiers are team name/abbreviation and season year.

These two datasets will be integrated using team abbreviation and season year as shared keys, connecting individual player batting statistics (aggregated to the team-season level) with team outcomes such as wins, losses, and runs scored. Analysis will focus on 1950–2025, where data completeness is highest.
# Data Quality:
# Data Cleaning (97/1000 Words)
The batting data required significant preprocessing before data can be integrated. There were 764,000 rows of empty row data that needed to be removed, as well as faulty header/column variables, reducing rows to four million. Missing statistical values were imputed with the value 0 where necessary. The last preprocessing step needed for the batting was linking 21,000 individual batting CSVs into one. The team dataset required almost no cleaning besides some missing values needing to be filled with 0. Both datasets were then validated to make sure there were no missing values or faulty data being faulty.
# Findings (0/500 Words)
# Future Work (0/500 Words)
# Challenges
