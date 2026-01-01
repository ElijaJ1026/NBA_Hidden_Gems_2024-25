NBA Hidden Gems: Identifying High-Impact Role Players
Author:
Elija Turull  
https://www.linkedin.com/in/elija-turull-600405344/ | https://github.com/ElijaJ1026 | elijat2005@gmail.com

Project Overview:

This project analyzes 2024-25 NBA season data to identify the most effective bench players who deliver outsized impact relative to their playing time. The analysis targets NBA front offices seeking cost-effective role players and fans looking to discover lesser-known contributors.
A "hidden gem" is defined as a player with limited minutes (15-25 MPG) who provides multi-dimensional impact—scoring efficiently, facilitating offense, securing rebounds, and generating defensive stops—often on overlooked teams where their contributions go unnoticed.

---
Visualizations:

Top 15 Hidden Gems
<img width="2135" height="1361" alt="top_15_graph" src="https://github.com/user-attachments/assets/3b593600-2943-4441-8b56-1cad0495f03c" />

Value vs Playing Time
<img width="2853" height="2100" alt="value_vs_minutes" src="https://github.com/user-attachments/assets/b6d5bf91-b426-49f8-9d40-020c9c94920b" />

Team Bench Depth Comparison
<img width="2572" height="2100" alt="NBA_Teams_with_Best_Bench_Depth" src="https://github.com/user-attachments/assets/fed23c62-308e-495e-a5cb-6e11a15379c6" />

Methodology:

Data Collection
- Source: NBA official statistics via the `nba_api` Python library (swar/nba_api on GitHub)
- Dataset: 2024-25 season player statistics (569 players initially)

Role Player Definition & Filters
- Minutes per game: 15-25 (captures bench rotation players, excludes starters at 28+ minutes)
- Games played: Minimum 30 games (ensures statistical significance; eliminated small sample outliers)
- Initial filtering: reduced dataset to 154 qualifying role players

Metrics Calculated:

Per-Minute Statistics:
- Points per minute (PTS/MIN)
- Assists per minute (AST/MIN)
- Rebounds per minute (REB/MIN)
- Steals per minute (STL/MIN)
- Plus/Minus per minute (±/MIN)

Value Score Formula:
```
Value Score = (PTS/min × 3) + (AST/min × 2) + (STL/min × 2) + 
              (REB/min × 1) + (±/min × 2) + (FG% × 1)
```
Weighting rationale: Scoring and playmaking weighted highest, defensive activity (steals) emphasized, rebounding as baseline contribution.

Team Quality Adjustment:
```
Hidden Gem Score = Value Score / (W_PCT + 0.3)
```
This formula penalizes players on elite teams (high W_PCT) and boosts players on struggling teams, surfacing overlooked contributors. Players on top-performing teams require higher value scores to rank highly.

Tools & Technologies:
- Python 3.13.7
- Libraries: pandas (data manipulation), matplotlib (visualization), nba_api (data collection)
- Jupyter Notebook for analysis and documentation

---

Key Findings

Top 5 Hidden Gems:

1.Lonzo Ball (CHI) - Elite floor general producing 7.8 PPG with 2.6 APG in just 22.2 minutes. Controls tempo, generates easy looks for teammates, and impacts winning despite the Bulls' struggles (.457 W%). His return from injury has been overlooked nationally but provides major value.

2.Aaron Nesmith (IND) - Versatile wing who was crucial in the Pacers' playoff run, including a clutch shooting performance in Game 1 of the ECF. Averaging 12.0 PPG in 24.9 minutes with strong defense, he's a prototypical 3-and-D role player on an upside trajectory.

3.Mouhamed Gueye (ATL) - The definition of "hidden" - a versatile power forward delivering impact on both ends for the struggling Hawks. Limited sample (33 GP) but showed enough in restricted minutes (16.1 MPG) to warrant attention from teams seeking athletic, two-way forwards.

4.Dereck Lively II (DAL) - The 2023-24 6th-place ROTY finisher is an elite offensive rebounder and rim protector. Dominates the glass on both ends and creates second-chance opportunities. A legitimate building block playing just 23.1 minutes.

5.Day'Ron Sharpe (BKN) - Position-versatile big (plays both 4 and 5) producing Lively-level impact for the rebuilding Nets (.280 W%). His per-minute production in 18.1 MPG suggests he could handle a larger role on a competitive team.

Key Patterns:

Team Distribution:
- Hidden gems cluster on losing teams (Bulls, Hawks, Nets all sub-.500) where individual production stands out
- However, elite teams dominate bench depth rankings - **Celtics lead**, followed by Grizzlies, Bucks, and Thunder
- This suggests good teams have quality depth but individual players get less spotlight, while bad teams have 1-2 standouts carrying weak benches

Player Archetypes:
- Big men dominate top rankings (Lively, Sharpe, Gueye, Edey) - efficient role-playing centers/PFs
- Floor generals on bad teams rank highly (Ball, Conley) - their playmaking creates value despite team struggles
- 3-and-D wings present (Nesmith, Jones Jr.) - modern NBA's most valued role player type

Statistical Trends:
- Top performers average 18-24 minutes (true bench players, not borderline starters)
- Plus/minus per minute heavily influences rankings - winning impact matters more than raw counting stats
- Efficiency (FG%) and versatility (multiple stat categories) separate hidden gems from volume scorers

Team Bench Depth Rankings:

The team analysis revealed an interesting paradox:
- Best bench depth: Celtics, Grizzlies, Bucks, Thunder (elite teams with deep rotations)
- Weakest bench depth: Struggling teams rely on 1-2 hidden gems rather than balanced depth
- This validates that championship teams are built on bench quality, not just star power

---

Recommendations:

For Contending Teams: Prioritize Bench Depth

The data validates what championship teams already know: deep benches win titles. The Celtics, Bucks, and Thunder lead bench depth rankings, while the Pacers' playoff success demonstrated the value of quality rotation players like Aaron Nesmith. The Knicks' current success follows this blueprint - their strong rotation enables them to maintain intensity throughout games.

Target Opportunities

1. Bigs on Bad Teams - Day'Ron Sharpe (BKN), Mouhamed Gueye (ATL), and Dereck Lively II (DAL) represent the archetype: efficient, athletic bigs producing in limited roles on struggling teams. Contenders lacking frontcourt depth should aggressively pursue these profiles.

2. Proven Winners - Luke Kornet's trajectory validates this analysis. Ranked highly in our findings while with Boston, his trade to San Antonio has unlocked expanded production (7 RPG, 8 PPG with three-point range). Teams should target similar players from deep rosters who could flourish with expanded opportunity.

3. Floor Generals on Rebuilding Teams - Lonzo Ball (CHI) provides championship-level playmaking on a non-contender. Contenders needing secondary ball-handlers should explore availability of these high-IQ veterans stuck on rebuilding rosters.

For Teams with Hidden Gems: Strategic Decisions

- Rebuilding franchises (Nets, Hawks, Wizards) should consider trading veteran hidden gems (Sharpe, Gueye) to contenders for draft capital while their value is quantifiable
- Competitive non-contenders (Pacers, Mavericks) should protect and develop their gems - these players can grow into starting roles as teams ascend
- All teams should increase minutes for top-ranked hidden gems (18-22 MPG → 24-28 MPG) to evaluate starter potential before committing long-term resources elsewhere

Roster Construction Philosophy:

The Celtics model proves sustainable: rather than relying on 2-3 stars with replacement-level depth, build 8-9 player rotations where bench players deliver starter-caliber per-minute impact. This analysis identifies which players can fill those critical 15-25 MPG roles that separate contenders from pretenders.

Avoid the Elite Team Context Trap:

While teams like OKC rank high in bench depth, individual players (Wiggins, Caruso, Wallace) may not be true "hidden gems" - elite team context inflates their value. Teams should dig deeper than surface stats when evaluating players from championship-caliber rosters.

---

Limitations:

Sample Size Constraints

The 30-game minimum threshold, while necessary to filter statistical noise, excluded potentially valuable players with fewer appearances. Elite talents like Chet Holmgren (32 GP) barely qualified, raising questions about whether the cutoff eliminated legitimate contributors who missed time due to injury management or late-season call-ups. A 29-game sample could be equally valid but falls outside the analysis.

Defensive Metrics Gap

The analysis relies heavily on surface-level statistics and doesn't capture crucial defensive contributions:
- Rim protection (blocks alone don't measure deterrence or positioning)
- Perimeter defense (on-ball pressure, closeouts, screen navigation)
- Help defense and rotations (invisible on box scores but critical for team defense)
- Defensive versatility (ability to switch across positions)

While steals and plus/minus provide some defensive signal, a complete evaluation would incorporate advanced metrics like Defensive Win Shares (DWS), Defensive Box Plus/Minus (DBPM), or opponent field goal percentage when defending.

Missing Context:

Several contextual factors that influence player value remain unaccounted for:

- System dependency: A player thriving in Indiana's pace-and-space offense might struggle in a slower, half-court system. Scheme fit isn't captured in per-minute statistics.
  
- Role scalability: Can a player maintain efficiency if minutes increase from 20 to 30 per game? Small-sample excellence doesn't always translate to expanded roles.

- Competition level: The analysis doesn't distinguish between production in garbage time versus high-leverage playoff-intensity minutes.

- Injury history and durability: A player with elite per-minute stats but chronic injury concerns represents different value than an iron-man rotation player.

- Contract situations: A "hidden gem" earning $12M annually isn't the same value proposition as one on a minimum contract.

Temporal Limitations:

Analyzing only the 2024-25 season creates recency bias:
- No longitudinal comparison: Is this a breakout year or regression to the mean?
- Career trajectory unclear: Young players improving vs. veterans declining
- Seasonal variance: One strong or weak season may not represent true talent level

A multi-season analysis comparing 2023-24 and 2024-25 would provide stronger confidence in player rankings and identify sustainable contributors versus statistical outliers.

Methodological Subjectivity:

The weighting system (PTS/min × 3, AST/min × 2, etc.) reflects subjective prioritization of offensive contributions. Alternative weighting schemes emphasizing defense or efficiency differently would produce different rankings. The team quality adjustment formula (dividing by W_PCT + 0.3) was derived through iterative testing rather than theoretical justification.

Areas for Future Enhancement:
- Incorporate advanced defensive metrics (DBPM, DWS, opponent FG%)
- Add multi-season trend analysis
- Include contract value ($/WAR or similar efficiency metrics)
- Segment by position for more targeted comparisons
- Add playoff performance weighting for proven postseason contributors

---

Technical Details:

Environment
- Python (3.13.7)
- Jupyter Notebook

Libraries
python (3.13.7)
nba_api          # NBA statistics API wrapper
pandas           # Data manipulation and analysis
matplotlib       # Data visualization


Data Source
- API: NBA.com official statistics via `nba_api` library
- Endpoint: 'LeagueDashPlayerStats'
- Season: 2024-25
- Collection Date: December 2024

Repository Structure:

nba-hidden-gems/
│
├── data/
│   ├── nba.csv                          # Raw initial data pull
│   ├── nba_players_2024_25.csv          # Complete 2024-25 player statistics
│   └── role_players.csv                 # Filtered role players with calculated metrics
│
├── notebooks/
│   └── 01_data_exploration.ipynb        # Complete analysis workflow
│
├── visualizations/
│   ├── top_15_graph.png                 # Top 15 hidden gems bar chart
│   ├── value_vs_minutes.png             # Value score vs minutes scatter plot
│   └── NBA_Teams_with_Best_Bench_Depth.png  # Team bench depth comparison
│
└── README.md                            # Project documentation


Reproducibility
To reproduce this analysis:
1. Install dependencies: `pip install nba_api pandas matplotlib jupyter`
2. Run `01_data_exploration.ipynb` sequentially
3. Data will be refreshed with current season statistics

Note: Results may vary if run mid-season vs. end-of-season due to changing player statistics and games played.

Next Steps & Future Work

Potential Enhancements

This analysis provides a foundation for identifying undervalued role players. Future iterations could incorporate:

- Multi-season validation: Compare 2023-24 and 2024-25 to identify sustainable performers vs. statistical outliers
- Advanced defensive metrics: Integrate DBPM, DWS, and opponent shooting percentages for complete player evaluation
- Positional analysis: Segment by position (guards, wings, bigs) for more targeted talent identification
- Contract value integration: Layer in salary data to identify true value (production per dollar)
- Playoff performance weighting: Prioritize players with proven postseason contributions
- Machine learning prediction: Build models to forecast which current hidden gems will break out into larger roles

Project Impact:

This methodology demonstrates a data-driven approach to talent evaluation that complements traditional scouting. The findings validate observable NBA trends (importance of bench depth, value of efficient bigs) while surfacing specific actionable targets for team decision-makers.




