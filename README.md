<div align="center">

<img src="assets/banner.svg" alt="Faith Onyinye Igwe: Analytics Engineer and Data Engineer" width="100%" />

<a href="https://github.com/FaithOIgwe">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=18&duration=3200&pause=900&color=67E8F9&center=true&vCenter=true&width=720&lines=Incremental+models+that+catch+late-arriving+data;Reversals+as+rows%2C+never+rewritten+history;Contracts+that+fail+the+build%2C+not+the+dashboard;Any+industry.+Same+rule%3A+the+numbers+must+tie+out." alt="typing" />
</a>

<br/>

<a href="https://faithoigwe.github.io"><img src="https://img.shields.io/badge/Portfolio-faithoigwe.github.io-22D3EE?style=for-the-badge&labelColor=0B1020" /></a>
<a href="https://instagram.com/project_onyi"><img src="https://img.shields.io/badge/@project__onyi-A78BFA?style=for-the-badge&logo=instagram&logoColor=white&labelColor=0B1020" /></a>
<a href="https://www.tiktok.com/@project_onyi"><img src="https://img.shields.io/badge/@project__onyi-34D399?style=for-the-badge&logo=tiktok&logoColor=white&labelColor=0B1020" /></a>

</div>

<br/>

## `> whoami`

I build the layer between raw event data and the numbers a business decides on: the models, tests, contracts and pipelines that make *"how many customers did X"* give the same answer in every dashboard.

Six years in data across **finance, retail, marketing, product and operations**, as an in-house engineer and as a freelance BI consultant. The industry changes; the hard part doesn't. It's rarely the SQL. It's the record that shows up twice, the correction that lands in a different month from the original, and two teams getting different totals from the "same" table. That's the work I like.

```yaml
role:        Analytics Engineer / Data Engineer
domains:     finance · retail · marketing · product · operations
focus:       data modelling · data quality · pipelines that fail loudly
currently:   building end-to-end platforms with dbt, Spark and CDC
```

<br/>

## `> featured_projects`

### [trade-ledger-analytics](https://github.com/FaithOIgwe/Trade_ledger_analytics) &nbsp; [![dbt ci](https://github.com/FaithOIgwe/Trade_ledger_analytics/actions/workflows/dbt-ci.yml/badge.svg)](https://github.com/FaithOIgwe/Trade_ledger_analytics/actions/workflows/dbt-ci.yml)

A brokerage data platform built end to end: one trading database, three ways out.

<img src="assets/trade-ledger-architecture.svg" alt="trade-ledger-analytics architecture: Postgres to dbt, Spark/Iceberg/Trino and Debezium/Redpanda/ClickHouse" width="100%" />

| Decision | Why it matters |
| --- | --- |
| **Incremental on arrival time, not event time** | A fill that executed Monday but landed Wednesday still gets picked up. A guard test stops one future-dated row from freezing every later run. |
| **Reversals are rows, not updates** | History is never rewritten, positions still net out, and you can see what was busted and when. |
| **Duplicates are counted, not silently dropped** | The dedupe records how many repeat reports it removed, so an unstable feed shows up as a metric. |
| **Enforced contracts on every mart** | Rename a column upstream and `dbt build` fails at the mart, not on a dashboard a week later. |
| **Tests that encode money rules** | Every trade reconciles to its cash settlement; fills never exceed order quantity; no short positions. |
| **CI builds the project twice** | The incremental path gets tested on every push, not just the full refresh. |

<br/>

### [sales-pipeline-analytics](https://github.com/FaithOIgwe/Data_Engineering_Projects/tree/main/sales_dbt%20project) &nbsp; [![dbt ci](https://github.com/FaithOIgwe/Data_Engineering_Projects/actions/workflows/sales-pipeline-analytics.yml/badge.svg)](https://github.com/FaithOIgwe/Data_Engineering_Projects/actions/workflows/sales-pipeline-analytics.yml)

HubSpot CRM data, with the mess left in, turned into pipeline, win-rate and funnel numbers that tie out. Plus creator commerce, to see whether the creators Sales closes go on to earn.

<img src="assets/sales-pipeline-overview.png" alt="New-business deals reaching each pipeline stage, and win rate by quarter" width="100%" />

| Decision | Why it matters |
| --- | --- |
| **History from property changes, not the deals table** | The deals table only knows today. Pipeline on any past date, time in stage and owner-at-the-time come from HubSpot's change log. |
| **A skipped stage still counts as reached** | A deal that jumped from Qualified to Proposal passed Demo. Without that, the funnel stops adding up. |
| **Two close dates, each with a job** | Bookings and win rate use the HubSpot close date Sales reports on; sales cycle uses when the deal really closed. Every backdated deal is flagged. |
| **Original, current and at-the-time owner** | Rep credit doesn't move when a rep leaves and their deals are bulk-reassigned. |
| **Reconciliation tests** | The rebuilt pipeline for the last day matches today's open deals, deal by deal; creator monthly sales tie to orders to the cent. |
| **A semantic layer tested against real questions** | "What was our win rate in 2025?" is answered through the metrics and in plain SQL, and CI fails if they disagree, so an AI tool gets it right too. |

## `> stack`

<p>
  <img src="https://img.shields.io/badge/SQL-0B1020?style=for-the-badge&logo=databricks&logoColor=67E8F9" />
  <img src="https://img.shields.io/badge/Python-0B1020?style=for-the-badge&logo=python&logoColor=FFD43B" />
  <img src="https://img.shields.io/badge/dbt-0B1020?style=for-the-badge&logo=dbt&logoColor=FF694B" />
  <img src="https://img.shields.io/badge/Snowflake-0B1020?style=for-the-badge&logo=snowflake&logoColor=29B5E8" />
  <img src="https://img.shields.io/badge/PostgreSQL-0B1020?style=for-the-badge&logo=postgresql&logoColor=4169E1" />
  <img src="https://img.shields.io/badge/Apache%20Spark-0B1020?style=for-the-badge&logo=apachespark&logoColor=E25A1C" />
  <img src="https://img.shields.io/badge/Airflow-0B1020?style=for-the-badge&logo=apacheairflow&logoColor=017CEE" />
  <img src="https://img.shields.io/badge/Iceberg-0B1020?style=for-the-badge&logo=apache&logoColor=A5F3FC" />
  <img src="https://img.shields.io/badge/Trino-0B1020?style=for-the-badge&logo=trino&logoColor=DD00A1" />
  <img src="https://img.shields.io/badge/ClickHouse-0B1020?style=for-the-badge&logo=clickhouse&logoColor=FFCC01" />
  <img src="https://img.shields.io/badge/Debezium%20CDC-0B1020?style=for-the-badge&logo=apachekafka&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-0B1020?style=for-the-badge&logo=docker&logoColor=2496ED" />
  <img src="https://img.shields.io/badge/GitHub%20Actions-0B1020?style=for-the-badge&logo=githubactions&logoColor=2088FF" />
  <img src="https://img.shields.io/badge/Azure%20%2F%20Fabric-0B1020?style=for-the-badge&logo=microsoftazure&logoColor=0078D4" />
  <img src="https://img.shields.io/badge/Sigma-0B1020?style=for-the-badge&logo=sigma&logoColor=A78BFA" />
  <img src="https://img.shields.io/badge/Power%20BI-0B1020?style=for-the-badge&logo=powerbi&logoColor=F2C811" />
  <img src="https://img.shields.io/badge/Tableau-0B1020?style=for-the-badge&logo=tableau&logoColor=E97627" />
</p>

<br/>

## `> how_i_work`

```sql
SELECT principle
FROM   faith.engineering_habits
WHERE  non_negotiable = TRUE;

-- 1. question → metric → grain → validate. Most wrong numbers are grain mistakes.
-- 2. Fail loudly. A broken build at the mart beats a wrong dashboard next week.
-- 3. Document what a metric counts AND what it deliberately leaves out.
-- 4. Explain the business impact, not just what was built.
```

<br/>

## `> more_work`

| Project | What it shows |
| --- | --- |
| [**Data_Engineering_Projects**](https://github.com/FaithOIgwe/Data_Engineering_Projects) | The sales dbt project above, plus Postgres data modelling (Sparkify), web-scraping ETL pipelines, Python for DE |
| [**A/B Testing: Marketing Campaign**](https://github.com/FaithOIgwe/A-B-Testing-Marketing-Campaign-Analysis-Python) | Experiment analysis and significance testing in Python |
| [**Danny's Diner: 8 Week SQL Challenge**](https://github.com/FaithOIgwe/Danny-s-Dinner-8-weeks-SQL-Challenge) | Window functions, CTEs, customer analytics |
| [**Mall Customer Segmentation**](https://github.com/FaithOIgwe/Mall-customers-Kmeans-Clustering-Analysis) | K-means clustering |

<br/>

## `> activity`

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=FaithOIgwe&show_icons=true&hide_border=true&bg_color=0B1020&title_color=67E8F9&icon_color=A78BFA&text_color=CBD5E1&rank_icon=github&include_all_commits=true" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=FaithOIgwe&layout=compact&hide_border=true&bg_color=0B1020&title_color=67E8F9&text_color=CBD5E1&langs_count=6" />

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/FaithOIgwe/FaithOIgwe/output/snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/FaithOIgwe/FaithOIgwe/output/snake.svg" />
  <img alt="contribution snake" src="https://raw.githubusercontent.com/FaithOIgwe/FaithOIgwe/output/snake-dark.svg" width="100%" />
</picture>

</div>

<br/>

## `> beyond_the_data`

🎥 Teaching data on Instagram & TikTok as **[@project_onyi](https://instagram.com/project_onyi)**: chart explainers, thinking like an analyst, learning data in the age of AI<br/>
🏃🏾‍♀️ Half marathons, training for a full &nbsp;·&nbsp; 🎨 painting &nbsp;·&nbsp; 🎹 keyboard &nbsp;·&nbsp; 🇫🇷 learning French

<!---
FaithOIgwe/FaithOIgwe is a special repository: its README.md appears on the GitHub profile.
--->
