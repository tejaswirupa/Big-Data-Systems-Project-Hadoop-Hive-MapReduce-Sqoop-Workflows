# 🛠 Big Data Systems Project

This project showcases scalable data engineering workflows built using Hadoop, MapReduce, Hive, and Sqoop. Across multiple modules, the project demonstrates real-world applications of big data technologies, including log aggregation, airline delay analysis, TF-IDF computation, and secondary sorting.

## 📌 Project Objectives

- Practice Hadoop-based data processing using real-world datasets
- Apply Hive for SQL-style querying and aggregation at scale
- Leverage Sqoop to bridge SQL and Hadoop ecosystems
- Build multi-stage MapReduce workflows for advanced analytics (e.g., TF-IDF)
- Optimize MapReduce tasks for performance and sort customization

---

## 📁 Modules

### 1. Word Count & Text Cleaning (MapReduce)
- Ran MapReduce jobs on Shakespeare texts
- Extracted top 10 frequent terms
- Cleaned text by removing punctuation and converting to lowercase
- Compared vocabulary richness of Shakespeare vs. Austen

### 2. Log Processing with Hadoop Streaming
- Parsed Hadoop logs to compute severity-level counts per minute (INFO, WARN, ERROR, FATAL)
- Output includes structured lines per minute with total and breakdown counts

### 3. Airline Delay Aggregation with Sqoop & MapReduce
- Imported data via Sqoop
- Computed min, max, and average flight delays by carrier
- Output sorted by average delay

### 4. Secondary Sorting in MapReduce
- Modified word count output to be sorted by frequency (descending)
- Implemented sort within MapReduce job using custom key manipulation

### 5. Hive Query – Worst Average Arrival Delay
- Joined airline and delay tables using HiveQL
- Extracted airline name and computed average arrival delay
- Exported final table as CSV using Hive's external export

### 6. TF-IDF Computation Pipeline (Streaming + Hive)
- Stepwise Hadoop Streaming pipeline:
  - Term count per doc
  - Total term count per doc
  - Document frequency per term
- Final TF-IDF calculated using Hive and output as `(doc_id, term, tfidf × 1,000,000)`

---

## 🧠 Key Skills & Tools

- **Technologies**: Hadoop, Hive, Sqoop, HDFS, HiveQL
- **Programming**: Python, Shell scripting, Streaming Mapper/Reducer
- **Concepts**: TF-IDF, MapReduce chaining, log analysis, airline performance tracking
- **Data Sources**: Shakespeare/Austen texts, Hadoop logs, Airline delay datasets

---

## 📊 Sample Outputs

- `top-10-words.txt`: Ten most frequent cleaned words in Shakespeare corpus
- `log-summary.txt`: Log entry count breakdown by minute and severity
- `airline-delay-summary.txt`: Carrier-wise delay statistics (min, max, avg)
- `worst-average-arrival-delay.txt`: Airlines ranked by average delay
- `tfidf-output.txt`: Final TF-IDF scores per term and document

---

## 🚀 Getting Started

Each module has its own script and supporting folder structure:
- Run using provided shell scripts (e.g., `process-log-file`, `terms-by-count`)
- Hadoop Streaming used with custom mapper and reducer Python scripts
- Hive scripts executed using `hive < script.hive`
- Sqoop used to selectively import SQL tables into HDFS

Ensure Docker-based Hadoop environment is properly set up with:
```bash
docker pull bigdata-hadoop:v7
docker run -it bigdata-hadoop:v7 /bin/bash

