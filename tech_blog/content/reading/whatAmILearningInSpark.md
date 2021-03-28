---
title: "Spark Learnings"
date: 2019-09-15T21:38:47+01:00
draft: false
weight: 8
---

This will all mostly be unreadable trash which I am typing just to try and recall some of the aspects that I have notice when reading through the Spark: The Definitive Guide


### Dataframes

Dataframes aren't a spark specific concept, but they are a common usage of data processing to split the data in to shards. These are the pieces in the processing puzzle which will be separated & distributed across parallel process to provide Spark with the partitioned data needed to be able to process in isolation & without duplication.

Spark runs a lazy load processing model, such that all of the processes applied onto the dataframe are mapped into a DAG of steps to be run, with each one mapping the dataframe from one form to another. Not sure yet if this is true of all actions within Spark, as this would seem odd to only ever have an output of dataframes - though this may only account for dataset manipulation...

## Spark Sessions

A spark session is the controlling agent of the Spark workloads, it will designate the split work to the available Spark Executors. The available spark executors are determined by the resource manager, which is usually YARN or something similar. The Spark session will designate the work to the executors & maintain the knowledge of what is active, so this is the single point of failure if no backup strategy is defined - if the SparkSession object goes down, nothing will be managing the executors. I think this means that they could complete onwards still, but the Spark session maintains the overall view of their progress, so if the session goes down it is unknown whether all executors finished successfully.

## Lanugages

Spark is compatible with many languages, with the main implementations in Scala (the native Spark language), Java, Python, and some others - probably Ruby.

Spark is distributed with a number of language specific bootup operators, PySpark the python version of this. Running PySpark allows the 
