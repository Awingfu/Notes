# Intro/Overview

## Fine vs Course Grained Operations

Fine grained are operated against a single record,
course grained are operated on entire dataset

## Actions

* Actions like 'collect()' will force computation of chained commands

## Clojures

* Variables and functions bundled together to be sent to worker nodes for computation

## Stages

* Stages are from parent to child RDD (separated by a transform)
* Pipelining allows stages to be run asynchronously (faster than just normal parallelism)
  * Pipelining allows partial RDD's to be run through the next function

## Narrow vs Wide Transformation

* Narrow transforms do not require a shuffle between partitions like filters. These are the optimal transforms
* Wide transforms require shuffles (like reduce by keys)

## Lineage

* Graph of transforms required when action is called
* AKA logical execution plan

## Directed Acyclic Graph (DAG)

* no cycles, composed of the logical execution plan
* starts with RDD that reads data and ends at RDD where action is called

## Resilient Distributed Dataset (RDD)

* if a node fails, spark can request another node to take over tasks
* whichever node finished the same task is kept, weak node's work is void
