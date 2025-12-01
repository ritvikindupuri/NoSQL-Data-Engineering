# NoSQL Data Engineering: MongoDB & Analytics Pipelines

## Project Overview

This repository documents the implementation of a scalable NoSQL data architecture using MongoDB and Python. Moving beyond traditional relational models, these projects focus on handling unstructured, hierarchical data and optimizing query performance for high-throughput environments.

The work demonstrates a full data lifecycle: from building ETL pipelines that transform tabular data into BSON documents, to executing complex aggregation pipelines and implementing indexing strategies for query optimization.

## Technical Competencies

* **NoSQL Database Management:** MongoDB, BSON data structures
* **Python Integration:** `pymongo`, Pandas for hybrid analysis
* **Data Modeling:** Schema design for nested objects and arrays
* **Query Optimization:** Indexing strategies (Compound, Text, Multikey), Query Execution Planning (`explain()`)
* **Aggregation Framework:** Multi-stage pipelines (`$lookup`, `$unwind`, `$group`, `$bucket`)

## Project Breakdown

### Project 10: NoSQL Migration & CRUD Operations (MovieLens)
Focused on the migration of large-scale tabular datasets into a document-oriented database to enable flexible schema evolution and rapid querying.

* **ETL Pipeline Engineering:** Developed a Python-based pipeline utilizing Pandas to transform the MovieLens CSV dataset (metadata, ratings) into hierarchical MongoDB documents, handling type conversion and bulk insertion (`insert_many`).
* **Advanced Querying:** Implemented regex-based pattern matching for string fields (dates, genres) and complex logical filtering (`$gt`, `$and`) to extract specific subsets of data without rigid schema constraints.
* **Data Lifecycle Management:** Executed bulk update and delete operations (`update_many`, `delete_many`) to sanitize the dataset, including removing low-quality records and programmatically injecting new feature flags across thousands of documents.

### Project 11: Advanced Aggregation & Performance Tuning (Ecommerce)
Simulated a high-volume ecommerce environment to solve complex analytical problems using MongoDB's Aggregation Framework and optimize database performance.

* **Hierarchical Data Analysis:** Leveraged Dot Notation and the `$elemMatch` operator to query deeply nested sub-documents (customer addresses) and array fields (product reviews) with precision.
* **Complex Aggregation Pipelines:** Architected multi-stage pipelines to perform relational-style operations in a NoSQL environment. Utilized `$unwind` to flatten array data, `$lookup` to perform left-outer joins between `Orders` and `Products` collections, and `$group` for category-level revenue reporting.
* **Performance Optimization:** Analyzed query execution plans using the database profiler (`explain()`). Reduced query execution costs from full collection scans (COLLSCAN) to efficient index scans (IXSCAN) by implementing Single Field, Compound, and Text indexes based on access patterns.
* **Hybrid Analytics:** Integrated MongoDB cursors with Pandas DataFrames to perform statistical analysis (inventory valuation, price distribution) that combines the storage flexibility of NoSQL with the analytical power of Python.

## Execution

1.  Ensure a local instance of MongoDB (Community Edition) is running on port `27017`.
2.  Install required dependencies: `pymongo`, `pandas`.
3.  Execute **Project 10** to initialize the MovieLens database and review basic CRUD implementation.
4.  Execute **Project 11** to build the Ecommerce database and review aggregation/indexing logic.
