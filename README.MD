# The Microstructure of Decentralized Exchanges: MEV, Trader Topologies, and Slippage Dynamics in Uniswap V3

**Author:** Pouyan Zare 
**Date:** August, 2026  
**Institution:** Tehran Institute for Advanced Studies(TeIAS); Khatam University  
**Advisors:** Dr Robab Kalantari

## Abstract
This repository contains the complete data engineering, cryptographic decoding, and econometric modeling architecture for my Master's Thesis. The codebase reconstructs the exact historical state of the Uniswap V3 ecosystem, isolates Maximum Extractable Value (MEV) algorithmic actors, maps the bipartite network topology of liquidity pools, and constructs a longitudinal panel tracking trader execution quality over time.

## Repository Structure
* `code/`: Contains the 9 sequential Jupyter Notebooks representing the full pipeline, from raw Ethereum RPC extraction to final econometric panel generation.
* `data_samples/`: Contains 50-row verifiable samples of the final data structures (Parquet and CSV) to allow peer reviewers to inspect the schema without requiring terabytes of storage.
* `literature/`: Contains the foundational academic papers and the BibTeX citation file referencing the mathematical formulas utilized in this research.

## Data Methodology & Reproducibility
Due to GitHub's file size constraints, the full 60+ million row datasets are not hosted in this repository. 
To completely reproduce this research from scratch:

1. Clone this repository.
2. Install the required environment: `pip install -r requirements.txt`
3. Provide your own Infura/Alchemy Ethereum Archive Node API key in place holders
4. Execute the notebooks sequentially from `01` to `09`. 

## Core Datasets Generated
* **Dataset A (Leg Ledger):** The foundational routing ledger detailing token transfers, decoded pricing, and exact block timestamps.
* **Dataset E (Pre-Trade State):** Reconstructs the exact tick and liquidity depth of the smart contract immediately preceding execution to calculate true mathematical price impact.
* **Dataset F (MEV Classifications):** Intra-block topological mapping to identify sandwich attacks and cyclic arbitrage loops.
* **Dataset G (Trader Demographics):** Cross-sectional profiles of all ecosystem participants, measuring Herfindahl-Hirschman Index (HHI) concentration and algorithmic heuristics.
* **Dataset H (Longitudinal Swap Panel):** The final bipartite network and time-series panel tracking user learning mechanics and execution slippage across their lifetime.

## Dependencies
This architecture relies heavily on out-of-core memory management to process blockchain scale data. The primary engine is `Polars` (executed via lazy evaluation), alongside `Web3.py` for direct on-chain verification.
