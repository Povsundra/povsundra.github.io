---
title: "Building a Data Pipeline for Economic Data and Developing Power BI Dashboards for Analysis"
excerpt: "Designed automated Python ETL pipelines, modeled PostgreSQL data warehouses, and developed interactive Power BI dashboards for economic data analysis."
collection: portfolio
date: 2025-10-31
header:
  teaser: /images/project_showcase.mp4
---

**Role:** Data Analyst Intern at the General Secretariat of National Council for Minimum Wage (Ministry of Labour and Vocational Training)  
**Year:** Aug – Oct 2025  
**Status:** Completed

---

## 🎯 Project Objective
The primary objective of this project was to modernize the data handling and reporting capabilities of the Ministry. The existing workflow relied heavily on manual data extraction from XML files to Excel, which was time-consuming and prone to human error. The goal was to build a robust, centralized data warehouse and automate the **ETL (Extract, Transform, Load)** processes to feed real-time, interactive dashboards for stakeholders and policy researchers.

## 🛠️ Methodology & Technical Approach
To solve the data inefficiencies, I developed an end-to-end data pipeline with a focus on data integrity, deduplication, and performance:

* **Automated Python ETL Pipeline:** 
  * Extracted trade and economic datasets (e.g., from the International Trade Centre - ITC).
  * Systematically cleaned, transformed, and structured raw, semi-structured XML data into a normalized format.
  * *Impact:* Ensured high data quality, structured data for immediate analysis, supported better decision-making, and saved significant manual processing time.

* **Database Design & PostgreSQL Warehousing:** 
  * Designed the **Warehouse Layer (Final Storage)** using **PostgreSQL** to house the cleaned and structured data.
  * Implemented robust schema designs with appropriate data types (e.g., `BIGSERIAL` for primary keys, `NUMERIC(20,4)` for precise trade values).
  * Enforced strict database constraints to ensure data integrity and clean reporting, including:
    * `PRIMARY KEY` on the ID.
    * `CHECK` constraints (e.g., `month BETWEEN 1 AND 12`).
    * **Composite `UNIQUE` Constraints** (`country`, `importers`, `product_code`, `year`, `month`) to prevent duplication and ensure exactly one unique trade record per cohort.

* **Data Analysis & Visualization (Power BI):** 
  * Connected the PostgreSQL data warehouse directly to **Power BI**.
  * Developed **3 interactive dashboards** to translate complex economic metrics into accessible visual insights for non-technical stakeholders.

## 📈 Key Results & Business Impact
* **Efficiency Gains:** Successfully eliminated manual XML-to-Excel workflows, reducing the overall data preparation time by **~70%**.
* **Reliability:** The stringent database design guaranteed 100% deduplicated and accurate records for policy analysis.
* **Enhanced Decision Support:** The interactive Power BI dashboards were officially adopted by the research team, providing seamless ongoing stakeholder reporting and data-driven decision support for policy research.

## 🎥 Video Showcase
*Due to the confidential nature of the data, the source code is not publicly available. Below is a video showcase summarizing the workflow and demonstrating the interactive dashboards.*

<video width="100%" controls>
  <source src="/images/project_showcase.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## 🙏 Acknowledgement & Data Source
Special thanks to my advisor, **Mr. Danut CHHORN**, for providing access to the dataset used in this project. The data was supplied by the **National Council for Minimum Wage** under the **Ministry of Labour and Vocational Training, Cambodia**. This project focuses on building a data pipeline for economic data processing and developing Power BI dashboards for analytical reporting and decision support.

---

## 💻 Tech Stack
`Python` `PostgreSQL` `Power BI` `ETL Pipeline` `Database Design` `Data Warehousing` `Data Cleaning` `Data Modeling` `Reporting` 
