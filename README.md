# Real-Time-Banking-Data-Engineering-Pipeline

This project demonstrates a modern, event-driven data pipeline for a retail banking domain. Transactions generated in a PostgreSQL OLTP database are captured via Change Data Capture (CDC), streamed through Kafka, persisted as Parquet files in object storage, and loaded into Snowflake for analytical processing and transformation with dbt.

The design mirrors the architecture used by banks and fintechs to deliver sub-minute analytics, regulatory reporting, and fraud detection.

In Simple Terms — What This Does for a Bank
Every time a customer deposits, withdraws, or transfers money, the bank's database records it. Most banks only look at this data the next day, after reports have been generated overnight. By then, it is already too late to catch fraud or answer a manager's question.

This project fixes that problem. Here is what it does, in plain language:

It watches the bank's database every second. The moment a new transaction happens, this pipeline sees it — no waiting for end-of-day reports.
It sends the information to a safe storage area. Every transaction is copied out of the main banking system so reports and analysis do not slow the bank down.
It keeps a permanent record. Every deposit, withdrawal, and transfer is saved as a file that can never be changed — this is what regulators like the Bank of Zambia require.
It loads the data into a place where anyone can ask questions. Managers, auditors, and analysts can run reports in seconds instead of waiting days.
It catches problems early. Suspicious activity — like someone withdrawing large amounts in different towns at once — can be flagged straight away instead of next week.
It turns the data into pictures. Charts and dashboards (Metabase) let managers see what's happening at a glance — total deposits today, transaction trends, account mix — without writing a single line of code.
It works automatically. Once running, the pipeline does everything by itself: capture, move, store, load, visualize. No one has to press a button.
The short version: this project turns a bank's raw transaction data into clean, trustworthy, real-time information that can be used for fraud detection, regulatory reporting, customer insights, and business decisions — without slowing down the bank's main systems
