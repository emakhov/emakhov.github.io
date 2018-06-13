---
layout: post
title:  "Data Quality: Small analytical framework for Big Data"
date:   2018-06-06 10:00:00 +0200
categories: projects scala
subtitle: "Developed by me at Agile Lab in 2017"
gh: https://github.com/emakhov/agilelab-data-quality
---

DQ is a framework to build parallel and distributed quality checks on big data environments.
It can be used to calculate metrics and perform checks to assure quality on structured or unstructured data.
It relies entirely on Spark.

Framework has been developed by me at [Agile Lab](http://www.agilelab.it).

![Project architecture](/assets/img/DQ2.png)

Compared to typical data quality products, this framework performs quality checks at raw level.
It doesnt leverage any kind of SQL abstraction like Hive or Impala because they perform type checks at runtime hiding bad formatted data.
Hadoop is mainly unstructured data (files), so we think that quality checks must be performed at row level without typed abstractions.

With DQ you are allowed to:
- Load heterogeneous data from different sources (HDFS, DB etc.) and various formats (Avro, Parquet, CSV, etc.)
- Apply SQL queries on Sources (powered with spark Dataframe API) 
- Select, define and perform metrics on DataFrames
- Compose and perform checks
- Evaluate quality and consistency on data, determined by constraints.
- Perform trend analysis, based on previous results.
- Transform results in order to make reports that you like.
- Save results on HDFS in multiple formats (csv, avro, parquet) or/and datastore etc.

Source code and documentation you can find on GitHub:
[Original repository](https://github.com/agile-lab-dev/DataQuality) or
[My fork](https://github.com/emakhov/agilelab-data-quality)