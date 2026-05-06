# IS 477 Final Project Report (How has the Game of Baseball Evolved?)
By Aadhya Mavani & Brock Hartweger
# Summary/Research Questions:
Our project aims to analyze how Major League Baseball has evolved over time using a historical baseball dataset. Using datasets on each player’s individual performance during a season, our group can study long-term trends in offensive production along with how player statistics have progressed throughout the decades. Coupling this with a dataset that consists of every MLB team’s season, we can measure an individual player's statistics versus a team’s performance. By examining statistics such as hits, home runs, batting averages, and other key metrics, we can research how player development and the style of the game have molded into the game we know today. 

Our plan is to clean and organize a dataset based on every MLB player’s season. After prepping the dataset, our group will analyze key performance statistics through variables such as home runs, batting average, home run percentage, and other variables, identifying trends throughout the decades. Using these variables, we will create summary statistics, visualizations, and a regression model to predict the future of the game and what it would look like for the next generation of players. Overall, these models will help our group explore many different possibilities and give us data-driven insights for the next decade. 

The motivation for this project stems from our fascination with sports analytics, and what better sport for analytics is there than baseball? Baseball piqued our interest due to its extensive historical record, allowing us the flexibility to tailor the project to our interests. Instantly, our group knew we wanted to do a project that was meaningful for both of us, and baseball was a common denominator of interest. Our group members share memories of staying up late to watch Chicago Cubs and White Sox games, as well as various World Series runs. This project isn’t necessarily an Information Systems 447 assignment; it’s a passion project for our group. Our project is an ode to baseball itself, reflecting its enduring presence throughout history. Through global events, depressions, wars, economic crises, etc., baseball has endured. This simple game is more than a game; it signifies tradition and stability in a tumultuous time. There are numerous reasons we chose this project, but in the end, both of us love the game.

1.) What is the relationship between at-bats and home runs after controlling for doubles, triples, and games played? How well does this model generalize to new data? 

2.) How do at-bats, games played, doubles, and triples relate to the likelihood of a player hitting 10 or more home runs in a season? How well does a classifier built on this relationship perform on unseen data? 

3.) How accurately can at-bats, games played, doubles, and triples predict the number of home runs a player will hit in a season, and which of these variables contributes most to that prediction?

# Data Profile:
## Retrosheet Baseball CSV Files


(https://www.retrosheet.org/downloads/othercsvs.html)


Retrosheet Baseball CSV Files is a non-profit organization that compiles historical MLB game data. From their CSV download portal, we use game-level batting data (batting_part_*.csv), which contains batting statistics for every player in each game from 1898–2025. The Retrosheet data used in this project is structured at the game level, where each row represents an individual player’s batting performance in a single game. Through aggregation, the dataset is merged to be at the season level, meaning each row consists of a player's individual season later on in the project. This is for one to scale down the dataset as a whole and perform analysis on season-level analysis of player performance and long-term trends. The raw dataset contains approximately 5.75 million rows of game-level data with 89 observational variables spanning the years from 1898 to 2025. The dataset was originally distributed across numerous CSV files, which were then merged into a single CSV dataset for convenience. The merged structure allows for a seamless integration of all historical records and allows for season-level analysis and integration.
​

The dataset contains an accurate and almost complete account of all MLB records across its history. There are numerous important variables through offensive statistics such as at-bats (b_ab), hits (b_h), home runs (b_hr), doubles (b_d), triples (b_t), runs batted in (b_rbi), walks (b_w), strikeouts (b_k), and stolen bases (b_sb). These variables give a wide scope of the offensive performance of a player during their tenure in the MLB. In addition to offensive statistics, there are many identifiable variables such as player ID, game ID (gid), team abbreviation, opponent team, and game date. These identifiers allow our group to track performance across separate seasons, and allows for the ability to aggregate and merge the data. Numerous variables were created through our process, such as season, year, and season homeruns. This allows our group to identify long-term analysis and trends within the game. The raw dataset contains numerous incomplete or non-informative data points, such as a player recording zero at-bats in a season. Since we are measuring offensive efficiency, our group chose to remove such rows from the data.
​

The Retrosheet game-level batting data is stored in the project repository under the directory /all_batting/. The dataset is then split across numerous CSV files in the format called batting_part_*.csv. The star represents the number of the dataset, for example,/batting_part_00.csv/ is the first csv of the twelve total. These files were combined during preprocessing in the project to form a single unified dataset for analysis of long-term performance trends.
​

These files are freely available for non-commercial use under Retrosheet's data license, meaning the data is allowed for educational use and academic research. The dataset consists of non-personal or secret information that might be privatized by such players. All records/stats pertain to public sporting events, thus privacy concerns and legal constraints are non-existent. The only ethical concern for this project is pertaining to the researchers providing accurate and appropriate analysis of a historical dataset. This includes proper cleaning methods, defining used variables, and accurate and permissible conclusions.
​

The dataset relates to all three of the research questions and is an essential backbone for each of them. This data is used to provide detailed game-level batting statistics that can be aggregated into player-season metrics to allow for long-term analysis. This dataset relates to the first research question, enabling a regression framework that examines the relationship between at-bats, doubles, triples, and other offensive variables in predicting home runs. It relates to the second research question by allowing the classification of a binary classification target, which would be +10 home runs in a season. This allows our group to research the likelihood of a player reaching such a threshold. For the third and last research question, the dataset allows our group to see which variables contributed the most in the estimation of total home runs. 

## Lahman Baseball Database (OpenIntro Version)


(https://www.openintro.org/data/index.php?data=mlb_teams)


The Lahman Baseball Database (accessed through OpenIntro) is a publicly available dataset that compiles historical Major League Baseball team statistics. From this source, this project uses the MLB teams dataset,which contains season-level performance data for professional baseball teams. From their CSV download portal, we use the season-level data (mlb_teams.csv), which contains statistics for every team in each game from 1876-2020. The Lahman Baseball Dataset used in this project is structured at the season level, where each row represents an individual team’s batting performance in a single season. No merging was needed to be made at the individual game-level since all data is already at season-level. The dataset contains approximately 2,784 rows and 41 variables spanning the entire history of Major League Baseball. Unlike the Retrosheet Dataset spanning across multiple CSV files, Lahman’s dataset is a singular dataset that allows for convenience and seamless integration.


The dataset contains an accurate and almost complete account of all MLB records across its history. There are numerous important variables through offensive statistics such as at-bats, hits, home runs, doubles, triples, walks, strikeouts, stolen bases, and runs scored. This dataset also includes pitching and fielding statistics; however, our group did not touch or use these statistics in our project. In addition to offensive statistics, there are many identifiable variables such as team name, year, league id, wins, and loses for the given season. These identifiers allow our group to track performance across separate seasons, and allows for the ability to aggregate and merge the data. Missing data is prevalent in this dataset, especially pertaining to records from before the year 1920.


The Lahman game-level batting data is stored in the project repository under the directory /mlb_teams.csv/. There is just a singular CSV, which is easy and convenient compared to Retrosheet.


These files are freely available for non-commercial use under Lahman’s data license, meaning the data is allowed for educational use and academic research. The dataset consists of non-personal or secret information that might be privatized by such teams. All records/stats pertain to public sporting events, thus privacy concerns and legal constraints are non-existent. The only ethical concern for this project is pertaining to the researchers providing accurate and appropriate analysis of a historical dataset. This includes proper cleaning methods, defining used variables, and accurate and permissible conclusions.

​
The dataset relates to all three of the research questions. This data is used to provide detailed season-level batting statistics for each of the questions to be merged with Retrosheet’s data. This dataset relates to the first research question, enabling a regression framework that examines the relationship between at-bats, doubles, triples, and other offensive variables in predicting home runs for each team. It relates to the second research question. This improves the model’s ability to distinguish between players who cross the threshold and those who do not by accounting for team context. This allows our group to research the likelihood of a player reaching such a threshold. For the third and last research question, the dataset allows our group to see which variables contributed the most in the estimation of total home runs.

# Data Quality:
# Data Cleaning (97/1000 Words)
The batting data required significant preprocessing before data can be integrated. There were 764,000 rows of empty row data that needed to be removed, as well as faulty header/column variables, reducing rows to four million. Missing statistical values were imputed with the value 0 where necessary. The last preprocessing step needed for the batting was linking 21,000 individual batting CSVs into one. The team dataset required almost no cleaning besides some missing values needing to be filled with 0. Both datasets were then validated to make sure there were no missing values or faulty data being faulty.


# Findings (0/500 Words)
Upon exploring and analyzing the MLB batting and team data from 1898-2020, we identified clear patterns at both the league and player level. A visualization of historical league data showcased several major trends. Firstly, batting averages varied significantly across different points in tim, ranging from 0.23 all the way to 0.29. They peaked during the 1920-30s but then dropped sharply in the late 1960s during a time when pitching was heavy. They do recover slightly from the 1980s to 2000s but once again drop closer to 2020. Total home attendance has increased dramatically from 2–5 million annually in the early 1900s to the high 70–80 millions annually in the early 2000. Obviously, we do see a sharp drop in 2020 because of the Corona virus. For fielding errors, they have decreased a lot since the 1900s, going from over 5000 yearly to a 2500–3000 range yearly. This shows long term improvements in defense. 


The linear regression model was developed to estimate the individual player home runs per season using features like at-bats, hits, RBIs, walks, and strikeouts. This model performed quite well, obtaining a train R2 of 0.8466 and test R2 of 0.8424. The test RMSE is also 3.44 home runs, showcasing consistent performance. We saw that the predicted values for players hitting home runs closely matched the actual values, especially in the 5–35 home runs range. However, for extreme performances that went over 50 home runs, the model did appear to underestimate in its predictions. Through the coefficients, we see that RBIs has the strongest positive impact on predictions, which makes sense because it is primarily used to measure a batter’s ability to produce runs. On the other hand, doubles and triples were negatively associated with home-runs, which also checks out because teams with high triples tend to follow a speed-oriented strategy, whereas teams with high home runs are more power forward. 


The Random Forest classification model was coded to predict whether a player would hit at least 10 home runs in a season, thus allowing to differentiate between regular hitters and power hitters. A stratified 80/20 split was used on players with at least 100 at-bats which is basically a statistic representing a batter’s turn. This model achieved a high accuracy of 90% on a test set with 6374 samples. For players with less than 10 home runs, the precision was 0.95 and the recall was 0.91, and for players with more than 10 home runs, precision and recall values were 0.81 and 0.89 respectively. This shows strong overall model performance. Also, the model’s AUC ROC score of 0.967 is extremely strong and indicates an excellent ability to differentiate between classes. I think adding balanced class weights helped acknowledge the class imbalance without impacting the model’s performance on the majority group 


# Future Work (0/500 Words)
# Challenges (87/500 Words)
One of the issues that came up was dealing with a dataset that consisted of 5.7 million rows, distributed across over 21,000 individual datasets, one per player, which needed to be combined into a single dataset. The file that resulted from this came out to be 565MB. Instead of dealing with one large dataset, it needed to be sliced into numerous datasets to account for the large volume, each about 500,000 rows. This challenge added significant time in the preprocessing stage before any meaningful analysis could begin.
# Reproducing Steps
https://uofi.box.com/s/k16jpnbyp6qfk1zg6irve0dsunedszkh
#Refrences
