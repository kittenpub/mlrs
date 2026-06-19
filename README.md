# mlrs — Machine Learning with Rust (2nd Edition)

Companion project for the book. `mlrs` is a single, progressively evolving
Cargo workspace that models a retail intelligence platform built on the
Online Retail II dataset.

The state of the project at the end of each chapter is committed under a
matching git tag (`chapter-01`, `chapter-02`, ...).

## Workspace layout

| Crate           | Kind   | Role                                            |
|-----------------|--------|-------------------------------------------------|
| `data-pipeline` | lib    | Data engineering (Polars / Arrow)               |
| `classical-ml`  | lib    | Regression, classification, SVM/NB/k-NN         |
| `deep-learning` | lib    | Neural networks, Burn, computer vision          |
| `nlp`           | lib    | NLP and transformer work (Candle)               |
| `model-server`  | bin    | REST API (axum)                                 |
| `mlrs-cli`      | bin    | Orchestrates each chapter's pipeline            |

## Toolchain

Pinned to Rust 1.85.0 via `rust-toolchain.toml`.

## Chapter 1 state

Workspace skeleton with all six crates compiling. The `data-pipeline` crate
holds the first functional module: `TransactionRecord`, `PipelineError`, and
the parallel `normalize_prices` utility with unit tests.

```bash
cargo test -p data-pipeline
cargo run -p mlrs-cli
```

## Dataset

Download `online_retail_data.zip`, extract, and place the two CSVs in
`data/raw/` (kept out of git):

```
data/raw/online_retail_2009_2010.csv
data/raw/online_retail_2010_2011.csv
```
