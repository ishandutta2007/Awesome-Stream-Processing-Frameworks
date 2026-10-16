# Awesome-Stream-Processing-Frameworks

## Top Stream Processing Frameworks Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Stateful Computations, Event-Time Processing & Exactly-Once Semantics*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Stream Processing Frameworks**. These tools provide the programming models and runtime engines for continuous computation over unbounded data — handling event-time windows, watermarks, stateful operators, checkpointing, and exactly-once delivery so applications can react to events as they happen.

**Examples** include Confluent ksqlDB, AWS Kinesis, Apache Flink, Databricks Structured Streaming, Google Cloud Dataflow, Azure Stream Analytics, Redpanda Cloud, StreamNative Cloud, Decodable, and Hazelcast (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, stateful stream processing, and transparent checkpoint management — ideal for data engineers prioritizing data sovereignty, developers building real-time pipelines, and organizations avoiding per-CSU or per-event cloud pricing.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Confluent Cloud (ksqlDB)](https://www.confluent.io/product/ksqldb/)**  
  **Managed stream processing database purpose-built for Kafka.** ksqlDB provides an intuitive SQL-like syntax to query, read, write, and process data in Kafka in real-time at scale, without requiring Java or Scala proficiency. Built on Kafka Streams under the hood — "use ksqlDB when you can" is a fair rule of thumb, reserving Kafka Streams for complex stateful logic beyond SQL's reach. Features **push queries** (continuous subscription to changing results) and **pull queries** (point-in-time lookup), removing the need for separate serving systems. **Embedded connectors** run pre-built Kafka Connect connectors directly on ksqlDB servers. Supports exactly-once processing semantics and integrates with Schema Registry for Avro. **Confluent Community License** — source-available but not OSI-approved open source. Confluent Cloud pricing is consumption-based per CSU at roughly **$0.12/hour**. **Limitations**: Only works with Kafka topics as source and sink; SQL dialect is non-standard and has limitations.

- **[AWS Kinesis Data Analytics](https://aws.amazon.com/kinesis/data-analytics/)**  
  Fully managed service for processing streaming data with Apache Flink, SQL, or Java. Integrates with Kinesis Data Streams, Firehose, and Lambda.

- **[Google Cloud Dataflow](https://cloud.google.com/dataflow)**  
  Fully managed Apache Beam runner for batch and streaming with autoscaling and exactly-once semantics.

- **[Azure Stream Analytics](https://azure.microsoft.com/en-us/products/stream-analytics/)**  
  Real-time analytics service with SQL-based queries over streaming data from IoT Hub, Event Hubs, and Blob Storage.

- **[Databricks Structured Streaming](https://www.databricks.com/)**  
  Apache Spark-based stream processing with Delta Lake integration, exactly-once guarantees, and unified batch/streaming APIs.

- **[Redpanda Cloud](https://redpanda.com/)**  
  Managed Kafka API-compatible streaming platform with built-in tiered storage. Redpanda itself is **source-available under BSL license**, not OSI open source.

- **[StreamNative Cloud](https://streamnative.io/)**  
  Managed Apache Pulsar service with Kafka protocol compatibility, tiered storage, and stream processing capabilities.

- **[Decodable](https://www.decodable.co/)**  
  Managed stream processing platform built on Apache Flink with SQL-based pipelines and connector ecosystem.

- **[Hazelcast Cloud](https://hazelcast.com/)**  
  Managed real-time data platform combining stream processing with a fast data store. Hazelcast Jet provides distributed stream and batch processing.

## Open-Source GitHub Projects

- **[Apache Flink](https://github.com/apache/flink)**  
  **The leading open-source framework for stateful computations over unbounded and bounded data streams.** Supports **event-time processing, exactly-once semantics, and runs on all common cluster environments** — Kubernetes, YARN, Mesos, and standalone. The **DataStream API** provides low-level control over state, timers, and windowing, while the **Table API and SQL** layer enables declarative stream processing. **Checkpointing and savepoints** provide fault tolerance and upgrade paths without reprocessing. **State backends** (RocksDB, heap) scale to terabytes of keyed state. Apache 2.0 licensed. The standard for complex stateful stream processing where SQL alone is insufficient.

- **[Apache Kafka Streams](https://github.com/apache/kafka)**  
  **Lightweight, powerful Java library for enriching, transforming, and processing real-time streams of data.** The engine under ksqlDB. Provides **DSL** (functional programming API) and **Processor API** (imperative API) — can combine both. Best for full-fledged stream processing applications requiring complex stateful logic like finite state machines, where SQL is insufficient. **No separate cluster required** — it's a library embedded in your application. Included with Apache Kafka distribution. Apache 2.0 licensed.

- **[Apache Beam](https://github.com/apache/beam)**  
  **Unified programming model for batch and streaming data processing** with SDKs for Java, Python, and Go. Pipelines are portable across runners including Flink, Spark, and Google Cloud Dataflow. **Portability framework** ensures consistent semantics across execution engines. **Windowing, triggers, and watermarks** are first-class concepts in the model. Apache 2.0 licensed.

- **[RisingWave](https://github.com/risingwavelabs/risingwave)**  
  **Open-source streaming database with PostgreSQL wire compatibility and disaggregated S3-backed storage.** Apache 2.0 licensed. Compute nodes run the Rust-based streaming engine, meta nodes manage cluster state, and compactor nodes handle storage compaction — state stored in S3 simplifies scaling and recovery. Sources include Kafka, Pulsar, Kinesis, PostgreSQL CDC, MySQL CDC. **Sub-second latency** for most queries. **PostgreSQL-compatible SQL** including materialized views, joins, window functions, and UDFs. The open-source alternative to Confluent Cloud — one system consolidates ingestion, processing, state management, and serving.

- **[Timeplus Proton](https://github.com/timeplus-io/proton)**  
  **Fast and lightweight stream processing engine powered by ClickHouse libraries.** C++ implementation with SIMD optimization — delivers **90 million EPS, 4ms end-to-end latency, and high-cardinality aggregation with 1 million unique keys** on an M2 Max MacBook Pro. **Single binary <500MB**, no JVM or other dependencies. Features streaming ETL, tumble/hop/session windows, watermarks, **incremental materialized views**, CDC, and data revision processing. Apache 2.0 licensed.

- **[Materialize](https://github.com/MaterializeInc/materialize)**  
  **Streaming database maintaining SQL views incrementally** — when source data changes, Materialize updates view results without recomputing from scratch. Built on Timely Dataflow and Differential Dataflow. Sources connect to Kafka, PostgreSQL CDC, or webhook inputs. **PostgreSQL-compatible wire protocol**. **Managed SaaS only** — the open-source version was deprecated. Pricing starts at roughly **$0.35/hour**.

- **[Apache Pulsar](https://github.com/apache/pulsar)**  
  **Cloud-native distributed pub-sub messaging and streaming platform** with multi-tenancy, geo-replication, and tiered storage. Includes **Pulsar Functions** for lightweight stream processing and **Pulsar IO** for connectors. Apache 2.0 licensed.

- **[Bytewax](https://github.com/bytewax/bytewax)**  
  **Python-first stateful stream processing framework with a Rust-based distributed engine.** Dataflow API with operators like `map`, `filter`, `fold_window`, and `join`. Connectors for Kafka, files, and WebSockets. Apache 2.0 licensed.

- **[Benthos (Redpanda Connect)](https://github.com/redpanda-data/benthos)**  
  **Stream processor with 200+ connectors** for building data pipelines. Declarative configuration with mapping language and support for Kafka, HTTP, and databases. Apache 2.0 licensed.

- **[Feldera](https://github.com/feldera/feldera)**  
  **Incremental computation engine evaluating arbitrary SQL programs incrementally.** Processes millions of events per second on a laptop with full SQL support including joins, aggregates, window functions, and recursive queries.

### Additional Strong Open-Source Options

- **Quix Streams** — Python library for Kafka stream processing with pandas-like API for real-time data transformations.
- **Memphis** — Real-time data processing platform with built-in schema management, observability, and dead-letter queues.
- **NATS JetStream** — Cloud-native messaging system with persistent streaming, exactly-once delivery, and key-value store. Lightweight alternative to Kafka.
- **Apache Samza** — Distributed stream processing framework built on Kafka with stateful processing and fault tolerance.
- **Apache Storm** — Classic distributed real-time computation system. Spouts and bolts model.
- **Apache Heron** — Twitter's successor to Storm with improved performance and resource efficiency.

**Frameworks for building custom systems**: Combine **Apache Flink** for arbitrarily complex stateful stream processing with event-time semantics, **Kafka Streams** for lightweight embedded processing without a separate cluster, **ksqlDB** for SQL-native stream processing directly on Kafka topics, **Apache Beam** for portable pipelines across execution engines, and **RisingWave** or **Materialize** for PostgreSQL-compatible streaming databases with materialized views — to build a complete stream processing stack tailored to your latency, throughput, and operational constraints.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Stream processing frameworks differ significantly in latency profile, state management approach, and operational complexity. **ksqlDB is not OSI-approved open source** — it uses the Confluent Community License which restricts some commercial uses. **Materialize's open-source version is deprecated** — only the managed SaaS remains. **Redpanda is source-available under BSL, not open source**. **Benchmarks are workload-dependent** — validate against your specific event rate, state size, and query complexity. **Flink's state backends must be sized appropriately** — RocksDB state can exceed disk capacity if keyed state grows unbounded. **Exactly-once semantics require careful sink configuration** — not all connectors support transactional writes .
- Self-hosted open-source solutions require proper cluster orchestration, checkpoint storage planning, state backend tuning, and monitoring.

---

**Made for data engineers, streaming architects, platform teams, and developers building real-time data pipelines.**  
Let's make stream processing more open, stateful, and operationally understandable.
