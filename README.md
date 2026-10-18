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

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global data lake and lakehouse market is estimated at approximately **$18B to $24B in 2026** (scaling from ~$16B–$19B in 2024–2025 at a >20% CAGR, on trajectory toward $70B+ by the early 2030s). The sector exhibits a **hybrid market structure with high concentration among top cloud hyper-scalers and platform titans** (Databricks, Snowflake, AWS, Microsoft, Google capturing the vast majority of enterprise spend), coexisting with a **moderately fragmented ecosystem** of independent query engines, specialized catalogs, and open table formats (Apache Iceberg, Delta Lake, Trino) competing for multi-cloud and vendor-neutral deployments.

## SaaS/Hosted Platforms

| Platform | Company | Company Size (Valuation / Revenue) | Description | Starting Pricing (Specific Tier) | Free Tier Limits / Free Trial |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Microsoft OneLake (Fabric)](https://www.microsoft.com/en-us/microsoft-fabric)** | Microsoft | **~$3.1 Trillion** market cap | Unified data lake for Microsoft Fabric with OneLake Shortcuts, native Delta Lake/Iceberg format support, and direct Power BI / Office 365 integration. | **$0.36/hour** (Pay-as-you-go for entry **F2 Capacity** [2 CUs @ $0.18/CU-hour]; OneLake storage from $0.023/GB/month) | **60-day free trial** with full platform access (provisioned at F4/F64 capacity equivalence) and up to **1 TB OneLake data storage**. |
| **[Google BigQuery](https://cloud.google.com/bigquery)** | Alphabet (Google) | **~$2.1 Trillion** market cap | Fully managed, serverless enterprise data warehouse and lakehouse engine with native Apache Iceberg table support and BigQuery Omni cross-cloud queries. | **$6.25 per TB** scanned (On-Demand query pricing; storage at $0.02/GB/month active) | **Perpetual Free Tier**: **1 TB of query data processed per month** and **10 GB of active storage per month** free forever. |
| **[AWS Lake Formation](https://aws.amazon.com/lake-formation/)** | Amazon (AWS) | **~$1.9 Trillion** market cap | Centralized permissions, security governance, and access control for data lakes on S3, featuring S3 Tables with native Apache Iceberg support. | **$0/month** core governance plane; Storage Optimizer compaction billed at **$0.44 per DPU-hour** | **Perpetual Free Tier**: Lake Formation permissions and catalog governance are **100% free ($0)**; underlying AWS Glue Data Catalog includes **1M objects & 1M requests/month free**. |
| **[Snowflake](https://www.snowflake.com/)** | Snowflake Inc. | **~$45 Billion** market cap (~$3.6B ARR) | Cloud data platform supporting managed and unmanaged Apache Iceberg tables, open Apache Polaris catalog integration, and Snowflake Horizon governance. | **$2.00 per credit** (Standard Edition on-demand; compressed storage at $23/TB/month) | **30-day free trial** with **$400 in free usage credits** (no credit card required upfront; trial expires at 30 days or $400 consumption). |
| **[Databricks (Delta Lake)](https://www.databricks.com/)** | Databricks | **~$43 Billion** valuation (~$2.4B+ ARR) | The pioneer lakehouse platform built by the creators of Apache Spark. Features Unity Catalog for cross-engine governance and the Photon query execution engine. | **$0.15 per DBU** (Standard/Jobs batch compute; SQL Serverless from $0.70/DBU; All-Purpose compute from $0.40/DBU) | **14-day free trial** with **$400 in free DBU credits**; also provides a perpetual **Community/Free Edition** for learning (single serverless micro-cluster, 15GB RAM limit, non-production). |
| **[Cloudera](https://www.cloudera.com/)** | Cloudera (KKR / CD&R) | **~$5.3 Billion** take-private valuation (~$1B ARR) | Enterprise hybrid cloud data platform with lakehouse services (CDP) for data engineering, streaming, and multi-function analytics across private and public clouds. | **$0.04 to $0.07 per CCU-hour** (Cloudera Compute Unit: Data Hub @ $0.04/CCU-hr, Data Warehouse @ $0.07/CCU-hr; 1 CCU ≈ 1 vCPU + 4GB RAM) | **60-day free trial** for CDP Public Cloud (access to data hub, warehouse, and machine learning workspaces; cloud infrastructure billed separately). |
| **[Starburst Galaxy](https://www.starburst.io/)** | Starburst Data | **~$3.35 Billion** valuation | Fully managed cloud service powered by Trino for fast federated SQL queries across data lakes, catalogs, and hybrid multi-cloud databases without data movement. | **$0.40 to $0.55 per Galaxy Credit** (Standard/Pro compute execution; clusters consume credits based on size and uptime) | **Perpetual Free Tier**: **Up to 3 free concurrent clusters** and community support; also offers a **30-day Enterprise trial** with **$500 in free usage credits**. |
| **[Dremio](https://www.dremio.com/)** | Dremio | **~$2.0 Billion** valuation | Apache Iceberg-native lakehouse engine featuring an Iceberg REST Catalog, autonomous reflections for query acceleration, and engines that scale to zero. | **$0.20 per DCU** (Dremio Compute Unit: 2XS engine = 32 DCUs/hr @ $6.40/hr; XS engine = 64 DCUs/hr @ $12.80/hr; $0 storage fee when using customer S3/ADLS) | **Standard Community Tier** (free software/engine management with limits up to small engine sizes, 10 users per project); plus a **30-day Cloud trial** with **$400 in free compute credits**. |
| **[Tabular (Databricks)](https://tabular.io/)** | Databricks (Acquired) | **~$1.0 Billion+** acquisition price | Universal Iceberg storage and catalog management platform created by Apache Iceberg co-creators (Ryan Blue, Dan Weeks); acquired by Databricks in 2024. | **$0.15 to $0.70 per DBU** (Integrated into Databricks platform pricing via UniForm and managed Iceberg catalogs) | **14-day Databricks trial** with **$400 credits** for exploring Tabular-integrated Iceberg features on Databricks. |



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
