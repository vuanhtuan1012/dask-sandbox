# Dask Sandbox  <!-- omit in toc -->

- [Introduction](#introduction)

## Introduction

- [Dask](https://docs.dask.org/en/stable/) is an open-source Python library for **parallel computing** and **scaling data workflows.** It lets you work with datasets and computations that are:
  - too large for memory
  - too slow on a single CPU
  - spread across multiple machines.

  > We can think of Dask as "*Pandas and Numpy, but scalable and parallel*".

- **Core idea:** normally, Python code runs on one core and in memory. If data is huge, reading data can crash or become slow. Dask:
  - splits the data into partitions,
  - processes chunks in parallel,
  - and executes lazily when needed.
- Main **Dask collections:**
  - **Dask DataFrame:** parallel version of Pandas. Useful for:
    - Large CSV/parquet files.
    - ETL pipelines.
    - Data preprocessing.
  - **Dask Array:** parallel Numpy arrays. Useful for:
    - Scientific computing.
    - Large matrices.
    - ML preprocessing.
  - **Dask Delayed:** turns regular Python functions into parallel tasks.
  - **Dask Distributed:** runs computations on:
    - multiple CPU cores,
    - multiple machines,
    - clusters,
    - cloud environments.

    This gives us task scheduling, monitoring dashboard, and fault tolerance.
- **Why people use Dask ?**
  - Handles larger-than-memory datasets: Dask streams data in trunks instead of loading everything at once.
  - Parallelism: uses multiple CPU cores effectively.
  - Familiar APIs: minimal changes from Pandas/Numpy code.
  - Scales gradually: we can start on a laptop, move to a server, then to a cluster without rewriting most code.
- **Lazy execution:** Dask **builds a task graph first,** then **executes later.** Nothing happens immediately. Execution starts only when be called. This allows Dask to optimize the workflow.
- **When to use Dask ?** Dask is good when:
  - Pandas becomes too slow.
  - Data does not fit RAM.
  - You need parallel CPU workloads.
  - You want scalable Python piplines.
- **When NOT to use Dask ?** Dask may be unnecessary if:
  - Data fits comfortably in memory.
  - Workflow is small/simple.
  - Overhead outweighs benefits.

  For small datasets, plain Pandas is often faster and simpler.
