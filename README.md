# Federico Vita

I'm a data engineer based in Messina, Italy.

For the past seven years I've worked on the data systems companies actually run on, mostly
as a consultant, which means a lot of different clients and domains. Oracle ETL pipelines
and regulatory reporting (IVASS, ANIA) for insurance groups. High volume telematics
ingestion over Kafka. PostgreSQL modeling and ingestion for an energy sector portal, plus
the ASP.NET Core services around it. The unglamorous parts: legacy PL/SQL migrations
between instances, reconciling data that two systems disagree about, jobs that have to run
correctly at 3am.

More recently I've been moving toward the modern data stack. I finished a
[Master in Data Engineering](https://certify.profession.ai/69f88359c63b283adf882aca) and
I'm working through the Databricks Data Engineer Associate. Everything in the portfolio
below came out of that.

Best way to reach me: [LinkedIn](https://www.linkedin.com/in/federicovita/) or
[federico.vita1997@gmail.com](mailto:federico.vita1997@gmail.com).

## What I use

**Day to day at work:** SQL, PL/SQL on Oracle, Python, PostgreSQL, Kafka, Docker, C# and
ASP.NET Core, KNIME.

**In the portfolio and side projects:** PySpark, Snowflake, AWS (Lambda, API Gateway,
DynamoDB, Glue, Step Functions, Redshift), Azure Data Factory, MongoDB, DuckDB,
scikit-learn, pytest, mypy, GitHub Actions.

**Learning right now:** Databricks, dbt, Airflow.

## Portfolio

Eleven projects from the master, all public and MIT licensed. I went back through them
afterwards and brought them to a consistent standard: tests and CI where it made sense,
type checking, a README that explains the choices rather than just the code.
[Browse them all here.](https://github.com/profession-ai-data-engineering-master)

| # | Project | What it is | Stack |
|---|---------|-----------|-------|
| 1 | [Household Expense Manager](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto1) ([docs](https://profession-ai-data-engineering-master.github.io/profession_ai_data_engineering_progetto1/)) | An expense tracking CLI. The interesting part is the reporting engine: you can swap between aggregating in memory with Python or pushing the work down to SQL with DuckDB, behind the same interface. Clean Architecture and DDD, strict mypy, 96% coverage, CI across three Python versions, Sphinx docs. | Python, DuckDB, pytest, mypy, Sphinx |
| 2 | [Stock index analysis](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto2) | Ten years of S&P 500 and EURO STOXX 50 compared. Follows the OSEMN process, with IQR outlier detection on returns and volumes to find the extreme days and tie them back to real market events. | pandas, matplotlib, Jupyter |
| 3 | [SQL feature engineering](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto3) | A denormalised view of 26 behavioural features per bank customer, ready to feed an ML model. Comes with a one command Docker environment, SQL linting and validation assertions in CI. Schema tuning took a query from 1.55s to 120ms. | MySQL 8, Docker, SQLFluff, GitHub Actions |
| 4 | [Contact book on MongoDB](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto4) | Queries and updates over a deliberately messy dataset, where a phone field is sometimes a string and sometimes a list. Small data, so the point is the modeling decisions, which the README argues for explicitly. | MongoDB, pymongo, Docker, pytest |
| 5 | [Book catalogue scraper](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto5) | The site turned out to be static, so I dropped Selenium for plain requests. Modular pipeline with retry, rate limiting and structured logging. 28 tests, 90% coverage, no network calls in the test suite. | requests, BeautifulSoup, pandas, pytest |
| 6 | [Clinical preprocessing pipeline](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto6) | Two custom scikit-learn transformers for things the built in ones can't do: fitting on a subset of rows, applying a transform only to skewed columns. Property based tests with Hypothesis, 97% coverage. | scikit-learn, Hypothesis, mypy |
| 7 | [Diabetes progression model](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto7) | A regression case study kept honest: all preprocessing lives inside the CV folds so there's no leakage, and the result (R² 0.444 to 0.476) is reported as the modest improvement it is. Logic in a tested package at 99% coverage, notebook just tells the story. | scikit-learn, pandas, pytest, mypy |
| 8 | [Wikipedia article classification](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto8) | 153k articles into 15 categories. The original exercise needed a paid Databricks tier, so I ported it to local Spark and anyone can now run it for free. Also found and fixed a bug where a pipeline stage was silently ignored. | Apache Spark, PySpark, Spark ML |
| 9 | [AWS end to end pipeline](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto9) | BTC and XMR prices joined against Google Trends on a Medallion layout in S3. One parametric Glue job for both currencies instead of two scripts, Step Functions running them in parallel, Redshift Serverless and QuickSight on top. Written up as a report with real runs. | AWS S3, Glue, Step Functions, Redshift, Athena |
| 10 | [Azure Data Factory ETL](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto10) | A film catalogue cleaned and filtered entirely in a Mapping Data Flow, no application code. Handles the real world mess: broken headers, titles with commas, ratings that aren't numbers. | Azure Data Factory, Blob Storage |
| 11 | [Clinical data warehouse](https://github.com/profession-ai-data-engineering-master/profession_ai_data_engineering_progetto11) | Snowflake warehouse built around the GDPR constraints rather than bolting them on after: three roles with real separation, dynamic masking on the PII that survives, synthetic data for development. Layered model, star schema, idempotent ELT with quarantine for orphan records. | Snowflake, SQL, AWS S3 |

### FitFriends (private repo)

A side project, a mobile app for finding people to train with. Serverless backend on AWS:
36 Python Lambdas, API Gateway with both REST and WebSocket, DynamoDB single table design,
infrastructure in SAM, dev and prod split across AWS Organizations. Flutter client. CI/CD
with a coverage gate at 90%.

## Get in touch

[LinkedIn](https://www.linkedin.com/in/federicovita/) or
[federico.vita1997@gmail.com](mailto:federico.vita1997@gmail.com). Happy to talk.
