# Time Series Forecasting of SARS-CoV-2 Mutation Rates
This repository contains the code, data, and documentation related to a series of experiments aimed at predicting the mutation rates of the COVID-19 virus. The experiments leverage Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU) neural networks, with a focus on different preprocessing techniques and protein-specific datasets.

## Introduction

This study explores COVID-19 mutation dynamics through LSTM and GRU models. Key focus areas include:

- Different preprocessing techniques
- Protein-specific datasets
- Model training and performance evaluation

## Running the Jupyter Notebooks
To run the Jupyter notebooks, follow these steps:
### 1. Clone the Repository
```bash
git clone https://github.com/Diksha1312/Time-series-forecasting-of-SARS-COV2-mutation-rates.git
cd Time-series-forecasting-of-SARS-COV2-mutation-rate
```
### 2. Set Up the Environment
Ensure you have a Python environment set up with the necessary dependencies. You can create a virtual environment and install the dependencies as follows:
```bash
conda create -n venv python=3.10 -y
conda activate venv
pip install -r requirements.txt
```
### 3. Run Notebooks
```bash
jupyter notebook
```
Open each notebook (e.g., gru_notebook.ipynb, lstm_notebook.ipynb) in your browser and run the cells sequentially.

## Experiment Summaries
### Experiment 01: Individual Proteins
- **Objective:** Train models using individual proteins as input.
- **Challenges:** Limited sample size led to convergence issues, and the absence of data scaling and rounding affected model performance.

### Experiment 02: Individual Proteins with Data Scaling and Rounding
- **Objective:** Improve model performance by incorporating data scaling and rounding.
- **Outcome:** Scaling and rounding improved model convergence and interpretability of results.

### Experiment 03: Whole Genome
- **Objective:** Extend the analysis to the entire genome, incorporating data from 27 proteins: NSP1, NSP2, NSP3, NSP4, NSP5, NSP6, NSP7, NSP8, NSP9, NSP10, NSP11, NSP12, NSP13, NSP14, NSP15, NSP16, Spike, NS3, E, M, NS6, NS7a, NS7b, NS8, N, NS9b, and NS9c.
- **Outcome:** The comprehensive dataset of 8,756 samples provided a more robust understanding of mutation rates and patterns across the full genome.

### Experiment 04: Specific Proteins
- **Objective:** Focus on specific proteins (NSP1, NSP3, NSP5, NSP8, NSP9, NSP13, NSP15) to assess the impact of a targeted dataset on model performance.
- **Outcome:** Despite a smaller dataset, the targeted approach yielded improvements in model accuracy and robustness.

## Repository Structure

The repository (Experiment 03 & 04) is organized into several folders, each containing files relevant to specific preprocessing steps, mutation rate calculations, and the execution of machine learning models.

### 1. Data Preprocessing Step 1 & 2
- **Purpose:** This file contains scripts that perform the initial preprocessing steps on the raw data, including sequence length consistency checks, error detection, and correction.
- **Files:**
  - **preprocessing_step1&2.ipynb:** Handles sequence length checks and filtering, Detects and corrects sequencing errors.
### 2. Data Preprocessing Step 3
- **Purpose:** This file contains the final preprocessing steps, focusing on scaling and rounding of mutation rates, which are crucial for improving model training effectiveness.
- **Files:**
  - **preprocessing_step3.ipynb:** This file merges the individual proteins based on their common labels essential for mutation rate calculation.
### 3. MRC Whole Genome Calculation/Specific Protein Calculation
      - **Purpose:** Contains the implementation of the Mutation Rate Calculation (MRC) algorithm for the whole genome and for specific proteins, producing the mutation rate matrix used as input for model training.
      - **Files:**
          - **mrc_whole_genome.ipynb:** Implements the mutation rate calculation for the entire genome.
          - **mrc_7proteins.ipynb:** Implements the mutation rate calculation for the 7 proteins.
### 4. Extract Ref Genome
      - **Purpose:** Extracts the reference genome used for comparison during mutation rate calculations. This step is essential for aligning the dataset with the reference sequences.
      - **Files:**
          - **extract_ref_genome_whole_genome.ipynb:** Extracts and processes the reference genome for the whole genome.
          - **extract_ref_genome_7proteins.ipynb:** Extracts and processes the reference genome for 7 proteins.
### 5. LSTM Notebook
    - **Purpose:** Contains the Jupyter notebook used to build, train, and evaluate the LSTM model on the preprocessed mutation data.
    - **Files:**
          - **lstm_notebook.ipynb:** Implements the LSTM model, including hyperparameter tuning and model evaluation.
### 6. GRU Notebook
    - **Purpose:** Contains the Jupyter notebook used to build, train, and evaluate the GRU model on the preprocessed mutation data.
    - **Files:**
          - **gru_notebook.ipynb:** Implements the GRU model, including hyperparameter tuning and model evaluation.


