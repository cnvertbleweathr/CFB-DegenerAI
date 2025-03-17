# cfbbetting_prediction

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
