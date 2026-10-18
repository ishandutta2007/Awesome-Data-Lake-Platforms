# Awesome-Data-Lake-Platforms

## Top Data Lake Platforms Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Open Table Formats, Lakehouse Architecture & Multi-Engine Interoperability*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Data Lake Platforms**. These tools enable organizations to build lakehouse architectures on object storage—adding ACID transactions, schema evolution, time travel, and efficient upserts to data lakes while keeping data in open formats readable by multiple engines.



**Examples** include Databricks Delta Lake, Snowflake, Apache Iceberg, Dremio, Starburst, AWS Lake Formation, Google BigQuery, Microsoft OneLake, Cloudera, and Apache Hudi (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for open table formats, streaming ingestion, and multi-engine catalog interoperability—ideal for data engineers, platform architects, and organizations seeking transparent, vendor-independent lakehouse infrastructure.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Databricks (Delta Lake)](https://www.databricks.com/)**  

  **The lakehouse platform built by the original creators of Apache Spark** . **Delta Lake** provides ACID transactions, schema enforcement, and time travel on data lakes . **Unity Catalog** governs **17+ exabytes of data in open table formats** across enterprise deployments . **Photon engine** accelerates query execution. **Delta Lake 4.x** introduces **catalog-managed tables** and **coordinated commits** for multi-writer scenarios . **Note**: **Delta Lake's tooling is partially under the Business Source License**—slower integration for some non-Spark engines compared to fully open specifications . **The most widely deployed lakehouse platform** with the largest installed base.



- **[Snowflake](https://www.snowflake.com/)**  

  **Cloud data warehouse that pivoted to open formats** . **Apache Iceberg tables are now GA** with **Polaris Catalog** open-sourced as the foundation of Snowflake's Open Catalog offering . **Snowflake Horizon** provides governance across structured and unstructured data . **The strategic shift**: Snowflake historically suffered from **vendor lock-in**—private storage format, closed ecosystem. **Polaris and Iceberg support represent a significant opening** , though **Polaris is now in Apache Incubation** and adoption remains early . **Pricing**: **Credit-based** with transparent unit pricing but higher per-unit costs than competitors .



- **[Google BigQuery](https://cloud.google.com/bigquery)**  

  **Serverless data warehouse with managed Iceberg tables** . **BigQuery supports Apache Iceberg natively**—query Iceberg tables alongside native BigQuery tables . **BigQuery Omni** queries data across AWS and Azure . **The most serverless option**—no infrastructure to manage, automatic scaling, pay-per-query.



- **[Dremio](https://www.dremio.com/)**  

  **Lakehouse platform built on Apache Iceberg** . **Dremio Cloud** provides a fully managed lakehouse with **Iceberg REST Catalog compatibility**, autonomous reflections, and elastic engines that scale to zero . **The Iceberg-native choice**—treats Iceberg as the primary table format, not an add-on.



- **[Starburst Galaxy](https://www.starburst.io/)**  

  **Fully managed Trino service for federated analytics** . **Query across data lakes, databases, and warehouses** without data movement . **The commercial arm of the open-source Trino project** . **Best for**: federated queries across heterogeneous sources where Iceberg is one of many formats.



- **[AWS Lake Formation](https://aws.amazon.com/lake-formation/)**  

  **Managed data lake service on AWS** . Features **centralized permissions**, **governance**, and **S3 Tables with native Iceberg support** . **The AWS-native choice** for governing S3-based data lakes.



- **[Microsoft OneLake (Fabric)](https://www.microsoft.com/en-us/microsoft-fabric)**  

  **Unified data lake for Microsoft Fabric** . Features **OneLake Shortcuts** for cross-cloud data access, **Delta Lake and Iceberg support**, and **deep integration with Power BI and Microsoft 365** . **The Microsoft ecosystem choice**.



- **[Cloudera](https://www.cloudera.com/)**  

  **Enterprise data platform with lakehouse capabilities** . **CDP (Cloudera Data Platform)** provides hybrid cloud data management with governance, security, and multi-function analytics. **The surviving enterprise Hadoop distribution** after the 2018 Cloudera-Hortonworks merger .



- **[Tabular (Databricks)](https://tabular.io/)**  

  **Iceberg-focused data platform acquired by Databricks** for **over a billion dollars** (2024). Founded by **Iceberg's Netflix creators** (Ryan Blue and Dan Weeks) . **The acquisition signal**: Databricks betting on Iceberg interoperability alongside Delta Lake—the format war is ending .



## Open-Source GitHub Projects



- **[Apache Hudi](https://github.com/apache/hudi)**  

  **Streaming data lake platform** (Apache-2.0) — **the record-level upsert specialist** . **Brings core warehouse and database functionality directly to a data lake**: **tables, transactions, efficient upserts/deletes, advanced indexes, streaming ingestion services, data clustering/compaction optimizations, and concurrency**—all while keeping data in open source file formats . **Core architecture**: **Timeline** for transaction management, **COPY_ON_WRITE and MERGE_ON_READ** table types, **snapshot/incremental/read-optimized queries** . **Built for mutable, CDC-heavy data**—**Uber ingests billions of events daily** that need constant updates and corrections; before Hudi, there was no practical way to apply record-level mutations to data on S3/HDFS . **Hudi's Record Index delivers near-O(1) key lookups on trillion-row tables** . **Robinhood built a CDC streaming lakehouse on Hudi**—Kafka into Hudi with incremental processing—and **cut data freshness from ~24 hours to under 15 minutes** . **The reference implementation for streaming lakehouse with upserts** .



- **[Apache Iceberg](https://github.com/apache/iceberg)**  

  **Open table format for huge analytic datasets** (Apache-2.0) — **the multi-engine interoperability standard** . **Created by Netflix in 2018** to fix correctness and engine-agnostic access after their 100+ PB warehouse on S3 outgrew Hive . **Architecture**: **hierarchical metadata** (catalog → metadata file → manifest list → manifest files → data files) enabling **O(1) snapshot creation**, fine-grained partition pruning without directory listing, and complete catalog-storage decoupling . **The broadest engine support**—Spark, Flink, Trino, Snowflake, BigQuery, Athena, DuckDB, StarRocks all read Iceberg natively . **Momentum**: **Databricks acquired Tabular** (Iceberg creators) for $1B+; **AWS shipped S3 Tables** with native Iceberg support; **Snowflake made Iceberg tables GA and open-sourced Polaris**; **BigQuery added managed Iceberg tables** . **The REST catalog spec has become a de facto standard** . **The reference implementation for open, multi-engine lakehouse** .



- **[Delta Lake](https://github.com/delta-io/delta)**  

  **Open-source storage framework for ACID transactions on data lakes** (Apache-2.0) — **the Spark-native choice** . **Transaction log architecture**: append-only `_delta_log` directory with JSON entries listing added/removed files, periodically checkpointed to Parquet for faster reads . **Deepest Spark integration**—natural fit when **Spark Structured Streaming is your ingestion layer** . **Largest installed base**—used across majority of Fortune 500 and tens of thousands of organizations, anchored by Databricks . **Comcast case study**: Delta ingestion **replaced 640 machines with 64**—a **~10x compute reduction** alongside far less DevOps overhead . **Adobe Experience Platform**: replaced a cost-prohibitive NoSQL hot store with Delta lakehouse, reporting **80%+ reduction in scan time on 1 TB workload** and compression **from 1 TB to ~64 GB** . **UniForm** enables Delta tables to be read as Iceberg and Hive—interoperability without migration . **The reference implementation for Spark-centric lakehouse** .



- **[Apache Paimon](https://github.com/apache/paimon)**  

  **Streaming lake format for real-time lakehouse** (Apache-2.0) — **the LSM-based streaming lakehouse** . **Formerly Flink Table Store**, graduated to Apache Top-Level Project (April 2024) . **Innovatively combines lake format and Log-Structured Merge-tree (LSM)** to bring **real-time streaming updates into the data lake** . **Key capabilities**: **large-scale streaming updates** with high performance through Flink Streaming, **multiple merge engines** (deduplicate to keep last row, partial update to progressively complete records, aggregation, first row), **CDC ingestion** from MySQL, Kafka, MongoDB, Pulsar, PostgreSQL, and Flink CDC with schema evolution . **Real-time queries within one minute**; **millisecond latency for primary key filtering** . **Multimodal data lake**: stores images, videos, audio, documents, and model weights with **Blob Table**, **DiskANN vector index** for approximate nearest neighbor search, and **PyPaimon** native Python SDK with no JDK dependency . **Used in production by Alibaba, Ant Group, ByteDance, China Unicom** . **The reference implementation for real-time streaming lakehouse** .



- **[Apache Gravitino](https://github.com/apache/gravitino)**  

  **Open-source metadata lake and catalog** (Apache-2.0) — **the unified catalog layer** . **Graduated to Apache Top-Level Project (June 2025)** . **Feature-rich**: supports **tables, ML models, Kafka topics, and more** . **Credential vending**, **access control**, and **nascent lineage and MCP (Model Context Protocol) support** . **Adoption hampered by incomplete documentation**—powerful but challenging to implement . **Best for**: organizations building an open, multi-engine lakehouse needing a catalog that spans entity types beyond just tables .



- **[Lakekeeper](https://github.com/lakekeeper/lakekeeper)**  

  **Lightweight, high-performance Iceberg catalog written in Rust** (Apache-2.0) — **the minimalist catalog choice** . **Focused purely on being a high-performance Iceberg catalog** with **access control and credential vending** . **Excellent documentation** and a **working Docker playground**—incredibly easy to evaluate and deploy . **Simplicity is its strength**: lacks broader entity support of Gravitino, but excels at its narrow scope . **Best for**: teams wanting a production-ready Iceberg REST catalog without the complexity of a full metadata lake .



- **[Apache Polaris](https://github.com/apache/polaris)**  

  **Open-source Iceberg catalog** (Apache-2.0) — **the Snowflake-originated catalog** . **Now in Apache Incubation**—the open-source foundation of **Snowflake's Open Catalog offering** . **Best for**: organizations wanting Iceberg catalog interoperability with Snowflake ecosystem alignment .



### Additional Strong Open-Source Options



- **[Trino](https://github.com/trinodb/trino)** — Distributed SQL query engine (Apache-2.0) . **The federated query engine powering Starburst**—reads Iceberg, Delta, Hudi, and 40+ other sources natively . **The most flexible query layer** for multi-format lakehouses .

- **[Apache Spark](https://github.com/apache/spark)** — Unified analytics engine (Apache-2.0) . **The processing engine behind Delta Lake and most lakehouse workloads** .

- **[Apache Flink](https://github.com/apache/flink)** — Stateful stream processing (Apache-2.0) . **The streaming engine paired with Paimon** for real-time lakehouse .

- **[DuckDB](https://github.com/duckdb/duckdb)** — In-process analytical database (MIT) . **Reads Iceberg and Delta natively**—the SQLite of analytics for lakehouse queries .

- **[Apache XTable](https://github.com/apache/incubator-xtable)** — Cross-table format translation (Apache-2.0) . **Converts between Delta, Iceberg, and Hudi metadata**—interoperability without migration.

- Community **n8n** workflows for lakehouse maintenance alerting and compaction scheduling.



**Frameworks for building custom systems**: Combine **Apache Iceberg** for multi-engine interoperability with **Apache Hudi** or **Apache Paimon** for streaming upserts and real-time updates, **Lakekeeper** or **Apache Polaris** for catalog management, **Trino** for federated queries, and **Delta Lake** where Spark-centric pipelines and Databricks alignment matter—creating a comprehensive open lakehouse stack.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Data lake platforms handling enterprise data must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls and governance.

- **The table format choice should be driven by workload, not hype.** **Iceberg for multi-engine analytics** where organizations query the same tables from Trino, Snowflake, Flink, and Spark side by side . **Delta Lake for Spark-centric pipelines** needing multi-table transactions and deep Databricks integration . **Hudi for high-frequency record-level upserts** and CDC replication where purpose-built indexing outperforms general-purpose merge operations . **Paimon for real-time streaming lakehouse** where LSM-based updates and millisecond latency matter . **The workload, not the vendor, drove every successful choice** .

- **The format war is effectively over.** **Databricks acquired Tabular** (Iceberg creators) for $1B+; **Snowflake open-sourced Polaris** and made Iceberg tables GA; **AWS shipped S3 Tables with native Iceberg support**; **BigQuery added managed Iceberg tables** . **UniForm** lets Delta tables be read as Iceberg . **The practical question is no longer "which format wins"—it's "which format fits my engine ecosystem."**

- **The "free" open-source format has operational costs.** **Compaction, snapshot retention, metadata cleanup, and orphan-file controls are unmanaged** in a bare object storage plus table format setup . **Running vacuum too aggressively can break time travel queries** still referencing older versions . **Production tables need incremental processing on ingestion-matched intervals (5-15 minutes for streaming) paired with daily vacuum and snapshot expiration outside peak query hours** .

- **Catalog choice is the real lock-in risk.** **Lakekeeper** is lightweight and focused—excellent documentation and Docker playground . **Gravitino** spans tables, ML models, Kafka topics—powerful but complex . **Polaris** is Snowflake-aligned . **Unity Catalog** is Databricks-native but open-sourced . **The catalog tracks which version is authoritative**—choosing one determines which engines can read your tables and how multi-table transactions work .

- **Paimon's multimodal capabilities are genuinely novel.** **Blob Table** stores images, videos, audio, documents, and model weights with **separated storage layout**—blob data in dedicated `.blob` files, metadata in standard columnar files . **PyPaimon** provides native Python SDK with **no JDK dependency**, integrating with Ray, PyTorch, Pandas, and PyArrow . **This is a lakehouse built for AI workloads, not just analytics** .

- Self-hosted open-source solutions require proper infrastructure management, compaction scheduling, and ongoing maintenance. **Lakehouse platforms are data infrastructure**—governance, lineage, and access controls are non-negotiable.



---



**Made for data engineers, platform architects, and organizations building transparent lakehouse solutions.**  

Let's make Data Lake Platforms more open, data-driven, and interoperable.
