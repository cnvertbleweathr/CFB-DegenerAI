# cfbbetting_prediction

![alt text](https://sdmntpreastus.oaiusercontent.com/files/00000000-542c-61f9-9b7c-c2ea5a4a33f4/raw?se=2025-05-11T04%3A54%3A59Z&sp=r&sv=2024-08-04&sr=b&scid=00000000-0000-0000-0000-000000000000&skoid=b0fd38cc-3d33-418f-920e-4798de4acdd1&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-05-10T19%3A19%3A59Z&ske=2025-05-11T19%3A19%3A59Z&sks=b&skv=2024-08-04&sig=biwARq4oAc78mMOXAwZpc6bMjP/5tlziEpFuIbm7Qck%3D "DegenerAI")

**Flow/Stack**
- AWS S3 for staging, Snowflake for warehousing
- Matillion for orchestration
- Matillion for Data ingestion to AWS S3 
- dbt for flattening, SCD Type 2 to update
- dbt for analysis & production-ready analysis
- [Snowflake Cortex for RAG and Query](https://quickstarts.snowflake.com/guide/ask_questions_to_your_own_documents_with_snowflake_cortex_search/#0)

**Initial Assumptions**
- [College Football API](https://api.collegefootballdata.com/api/docs/?url=/api-docs.json) will the the main source
- A numerical scale will need to be created based on analysis of contributing factors to trend
- Weighting will need to be attributed to different factors for the future, based on past performance.

**Metrics to be Considerd / Weighted**
- Coaches' relationship to beating spread/over under
- Tenure of coach, coaching staff, starting QB
  - Big offseason changes in coaching or roster continuity affect performance. Teams with high returning production often overperform early in the season before markets catch up.
- Run Offense, Pass Offense, Run Defense, Pass Defense over last few seasons, or since coach joined team
- Avg points scored / given up vs opponent ranking
- In-conference games
  - Some conferences consistently outperform others ATS (against the spread), especially in non-conference play. Trends like “Pac-12 teams struggle in early season road games in the South” can surface over years.
- Situational/scheduling
  - Track travel distance, short rest, back-to-back road games, early kickoffs, or altitude changes.
- Line Movement & Closing Line Value (CLV)
  - Track the opening and closing betting lines over time; Analyze how teams perform relative to the closing spread; CLV can be a sharp indicator of value and market efficiency.
- Public vs Sharp Money
  - If you can get access to public betting percentages (even outside of the API), compare line movement with bet distribution. Look for games where the line moves against the public consensus—these are often spots where sharps are betting.
- Tempo & Efficiency Metrics
  - Use advanced stats like offensive/defensive efficiency, success rate, and explosiveness (available via CFB Stats or CFBD API). High-tempo teams may lead to more variance—valuable for totals betting or underdog ML bets.
- Weather
  - Weather (wind, rain) can drastically affect totals and passing-dependent teams.
- Injuries 
  - Track injury reports, especially QB/OL/DB groups—huge performance impact in college football where depth is limited.
  - 
