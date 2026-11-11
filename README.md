# IPL Analytics Dashboard | Power BI

An interactive **Indian Premier League (IPL) analytics dashboard** built with Microsoft Power BI. The project explores IPL match, team, player, venue, batting, bowling and season-level information through interactive report pages.

> **Project status:** Power BI report created. The repository should include the `.pbix` report and the CSV data files required to reproduce or refresh the analysis.

## Live Interactive Dashboard

Explore the published Power BI report here:

**[View the IPL Analytics Dashboard](https://app.powerbi.com/view?r=eyJrIjoiY2JjMTExY2QtYTk4MS00NGVjLThiZGUtODVjNTAxNDk5NWE5IiwidCI6IjA2ODkxNTc3LTNkYmMtNGJhMi1hYjBiLTVkM2UzZTg5ZTVlYyJ9)**

The report opens in a browser. Use the page navigation and available report interactions to explore the IPL analysis.

## Dashboard Preview

Add screenshots of your report here after uploading them to the repository:

```text
![IPL Dashboard Home](screenshots/home-page.png)
![IPL Overview](screenshots/ipl-overview.png)
![Team Profile](screenshots/team-profile.png)
![Player Profile](screenshots/player-profile.png)
```

## Report Pages

The report contains the following pages:

| Page | What it shows |
|---|---|
| **Home Page** | IPL introduction and navigation to the report sections. |
| **IPL Overview** | High-level league statistics and season trends, including total seasons, participating teams, matches, frequently used venues, umpire appearances, no-ball/wide-ball trends, average runs per innings and qualifying teams by season. |
| **Team Profile** | Team-focused analysis with slicers and visuals for exploring team performance. |
| **Player Profile** | Player-focused analysis with slicers and visuals for exploring individual player statistics. |
| **Tooltip** | Supporting tooltip visuals used to provide additional context when hovering over report visuals. |

### Highlights

The overview page includes:
- Total IPL seasons, participating teams and matches.
- Most-used stadiums/venues.
- No-ball and wide-ball trends by season.
- Average runs per innings by season.
- Most frequently featured TV umpires.
- Qualifying teams by season.

The report is designed for interactive exploration. Use the page navigation, slicers and visual interactions to explore the available information.

## Data

The accompanying `IPL.zip` archive contains CSV datasets for match summaries, ball-by-ball details, batting cards, bowling cards and points tables.

### Dataset files

| File | Description |
|---|---|
| `all_season_summary.csv` | Consolidated match-level summary data. |
| `all_season_details.csv` | Consolidated ball-by-ball/commentary-level match data. |
| `all_season_batting_card.csv` | Consolidated batting scorecard data. |
| `all_season_bowling_card.csv` | Consolidated bowling scorecard data. |
| `points_table.csv` | Season-wise team standings and points-table information. |
| `2022/` | Season-specific points table, batting card, bowling card, match details and summary. |
| `2023/` | Season-specific batting card, bowling card, match details and summary. |
| `2024/` | Season-specific batting card, bowling card, match details and summary. |

The consolidated `all_season_*` files in the supplied archive contain seasons **2008–2023**. Separate season-specific files are also provided for **2022, 2023 and 2024**. Avoid appending both consolidated and season-specific copies together without checking for overlap, as this can double-count records.

### Main data entities

- **Matches:** season, match ID, teams, toss, result, winner, dates and venue.
- **Ball-by-ball details:** innings, over/ball, runs, extras, boundaries, batter and bowler information.
- **Batting cards:** runs, balls faced, fours, sixes, strike rate and dismissal/innings information.
- **Bowling cards:** overs, maidens, runs conceded, wickets, economy and other bowling figures.
- **Points tables:** rank, matches played/won/lost, points and net run rate.

> Data quality note: the supplied master ball-by-ball file contains at least one repeated record under a key formed from `comment_id`, `match_id`, `innings_id`, `over` and `ball`. Validate the source and the intended grain before removing records; repeated-looking commentary rows are not automatically errors.

## Key Metrics and Analysis Ideas

The dashboard currently highlights several league-level metrics. Depending on the data fields and report filters, useful additional analysis can include:

- Team win percentage and season-wise points.
- Toss decision versus match result.
- Batting first versus chasing win rates.
- Highest team totals and lowest team totals.
- Top run scorers and highest individual scores.
- Batting average and strike rate.
- Top wicket-takers and bowling economy.
- Venue-wise average first-innings scores.
- Boundary contribution (fours and sixes).
- Powerplay, middle-over and death-over scoring.
- Season-wise scoring and match-result trends.

Any additional measures should be validated against the source data and documented with their calculation definitions.

## Tools and Technologies

- **Microsoft Power BI Desktop** — report authoring and interactive visualizations.
- **CSV** — source data format.
- **Power Query** — suitable for importing, cleaning and shaping the CSV data.
- **Power BI data model** — relationships and report filtering.

Only list DAX, Python, SQL or other tools in your final project stack if you actually used them in the report workflow.

## Getting Started

### 1. Download the project

Clone the repository:

```bash
git clone https://github.com/<your-username>/<your-repository>.git
cd <your-repository>
```

Or download the repository as a ZIP from GitHub and extract it.

### 2. Extract the datasets

Extract `IPL.zip` while keeping its folder structure intact. The report's data-source paths may need to be updated if the files are moved to a different computer.

### 3. Open the report

1. Install [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Open `ipl_dashboard.pbix`.
3. If Power BI asks for data-source credentials or cannot find a CSV file, open **Transform data → Data source settings** and update the file paths.
4. Select **Close & Apply** if you changed Power Query sources.
5. Refresh the report and check the totals and visuals.

### 4. Publish (optional)

You can publish the report to your Power BI workspace using Power BI Desktop's **Publish** option. Sharing and embedding options depend on your Power BI license, tenant settings and workspace permissions.

**Privacy warning:** Do not use **Publish to web** for confidential, personal or restricted data. Publish to web makes the report publicly accessible to anyone with the link and potentially discoverable by others.

## Suggested Repository Structure

```text
ipl-analytics-dashboard/
├── ipl_dashboard.pbix
├── IPL.zip
├── README.md
└── screenshots/
    ├── home-page.png
    ├── ipl-overview.png
    ├── team-profile.png
    └── player-profile.png
```

If you prefer to store the extracted CSVs directly in GitHub, use a `data/` directory and update the paths in Power Query accordingly. Large CSV files may exceed GitHub's normal file-size limits; consider Git LFS or provide a documented download source when appropriate.

## Notes and Limitations

- The figures shown in the report depend on the seasons and records present in the supplied CSV data.
- The consolidated datasets and season-specific datasets overlap. Do not combine them blindly.
- Validate totals after changing source paths, transformations or relationships.
- Check the source dataset's license and attribution requirements before redistributing the CSV files.
- This project is an analytics and visualization project; it is not an official IPL, BCCI or team-affiliated product.

## Future Improvements

- Add a dedicated season comparison page.
- Add a match-by-match analysis page.
- Add advanced batting and bowling leaderboards.
- Add venue and toss-impact analysis.
- Add powerplay, middle-over and death-over breakdowns.
- Add clear metric definitions, refresh date and data-source attribution.
- Improve accessibility with consistent contrast, meaningful titles and alt text.

## Author

**Raja Babu**

B.Tech — Computer Science and Engineering

[GitHub](https://github.com/Raja786000)

---

*This project is independently created for learning, analysis and portfolio demonstration. IPL names, team names and related marks belong to their respective owners.*
