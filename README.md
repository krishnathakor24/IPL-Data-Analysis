# IPL Data Analysis (Python, Pandas, Seaborn)

An exploratory data analysis of the Indian Premier League built on **ball-by-ball data (278,205 deliveries, 1,169 matches)**. The notebook cleans and standardizes the raw data, engineers match and phase features, and computes **12 team and player KPIs** covering win rates, batting, bowling, scoring phases, and the effect of the toss.

Google Colab Link: [IPL Data Analysis]([(https://colab.research.google.com/drive/16W9uj7QNu1NusjRIbMljJ2PB5_laiGew#scrollTo=Y1mDBYyTYvo2)])

## Objectives
- Standardize messy, multi-season IPL data into an analysis-ready form
- Measure team performance (win percentage, scoring by phase, best seasons)
- Identify standout batters and bowlers overall, by team, and by year
- Test whether winning the toss translates into winning the match

## Dataset
| Item | Detail |
|---|---|
| Granularity | One row per delivery |
| Size | 278,205 rows; 64 columns originally, 44 after cleaning |
| Matches | 1,169 |
| Contents | Teams, batter, bowler, runs, extras, wickets, venue, city, toss, match result, season, player of the match, super-over outcome |
| Source | <!-- add dataset source and credit (for example Kaggle / Cricsheet) --> |

## Data Cleaning & Preparation
1. **Dropped 20 low-value columns** (review details, umpire info, match type, and duplicated identifiers).
2. **Checked for duplicates** (none found) and reviewed missing values.
3. **Handled nulls meaningfully**: no-wicket deliveries labeled `No wicket`; missing extras and target values set to 0.
4. **Standardized franchise names** so renamed teams count as one: Delhi Daredevils → Delhi Capitals, Royal Challengers Bangalore → Bengaluru, Kings XI Punjab → Punjab Kings, Rising Pune Supergiant → Supergiants.
5. **Resolved match outcomes**: matches with no result were flagged, and tied matches were assigned to the super-over winner.
6. **Engineered features**: total runs per ball, boundary flag, wicket flag, result flag, and match **phase** (Powerplay, Middle Overs, Death Overs).

## KPIs Analyzed
| # | KPI | Visual |
|---|---|---|
| 1 | Win percentage of each team | Bar chart |
| 2 | Bowler economy rate | Horizontal bar |
| 3 | Runs by phase (Powerplay / Middle / Death) per team | Grouped bar |
| 4 | Top run-scorer for each team | Table |
| 5 | Top run-scorer for each year | Table |
| 6 | Highest season run total for each team | Table |
| 7 | Top 10 batters by strike rate (min. 2,000 balls faced) | Bar chart |
| 8 | Boundary split (4s vs 6s) and top 10 boundary hitters | Pie and bar |
| 9 | Impact of the toss on match outcome | Pie chart |
| 10 | Top wicket-taker for each year | Bar chart |
| 11 | Top wicket-taker for each team | Horizontal bar |
| 12 | Best bowling season for each team | Horizontal bar |

## Key Findings
- **The toss is close to a coin flip:** the toss winner won **595 of 1,169 matches (about 51%)**, so winning the toss gives only a very small edge.
- **Strike-rate leaders** (min. 2,000 balls faced): AB de Villiers (about 148.6), SA Yadav (about 145.6), JC Buttler (about 144.3), RR Pant (about 142.4), and CH Gayle (about 142.1).
- **Most prolific run-scorer in the strike-rate group:** DA Warner leads that list on volume, with 6,567 runs at a strike rate of about 135.4.
- **Most successful franchises by raw wins** (initial count, before name merging): Mumbai Indians (151), Chennai Super Kings (142), and Kolkata Knight Riders (135).
- **Phase analysis** compares how each franchise distributes its runs across Powerplay, Middle Overs, and Death Overs.

## Author
Krishna Thakor · [LinkedIn](https://www.linkedin.com/in/krishnamaheshchandrathakor/) · [Email](mailto:krishnathakor2411@gmail.com)
