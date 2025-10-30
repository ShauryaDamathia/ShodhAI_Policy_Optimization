# Policy Optimization for Financial Decision-Making: Loan Approval

## Project Overview

This project addresses the critical business challenge of loan approval decision-making within a fintech context. The objective is to develop an intelligent system that moves beyond simple risk prediction to directly optimize for financial returns. Using the LendingClub loan dataset, this repository presents an end-to-end machine learning solution, from data analysis to the implementation and critical comparison of two advanced modeling paradigms:

1.  A **Supervised Deep Learning Model** to accurately predict the probability of loan default.
2.  An **Offline Reinforcement Learning Agent** to learn a profit-maximizing loan approval policy.

The core of this analysis lies in comparing the risk-averse policy derived from the predictive model against the value-driven policy learned by the RL agent, providing actionable insights for a real-world business strategy.

## How to Reproduce This Project

### 1. Prerequisites

-   Python 3.8+
-   Git

### 2. Setup

Clone the repository and set up a virtual environment with the required dependencies.

# Clone the repository
git clone <your-repository-url>
cd your-project-name

# Create and activate a virtual environment (recommended)
python3 -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install the required packages
pip install -r requirements.txt

### 3. Obtain the Data

1.  Download the `accepted_2007_to_2018.csv` file from the [Kaggle dataset page](https://www.kaggle.com/datasets/wordsforthewise/lending-club).
2.  Place the downloaded CSV file into the `data/` directory.

### 4. Execute the Notebooks

The analysis is broken into three sequential Jupyter notebooks located in the `notebooks/` directory. **They must be run in order.**

1.  **`1_EDA_and_Preprocessing.ipynb`**: Loads the raw data, performs exploratory analysis, cleans features, and saves the processed datasets required for the models.
2.  **`2_Deep_Learning_Model.ipynb`**: Builds, trains, and evaluates a deep learning model to predict loan default. It saves the trained model (`loan_default_model.h5`) to the root directory.
3.  **`3_Offline_RL_Agent.ipynb`**: Frames the problem for offline reinforcement learning, trains a CQL agent to learn an approval policy, and performs a critical comparison of its decisions against the deep learning model's policy.

---

## Summary of Key Findings

-   The **Deep Learning (DL) model** demonstrated strong predictive power, achieving an **AUC of 0.73** on the test set, effectively distinguishing between high-risk and low-risk applicants.
-   The **Offline Reinforcement Learning (RL) agent** learned a policy with a positive **Estimated Policy Value of ~$360 per decision**, indicating its potential to be profitable.
-   The comparative analysis revealed critical differences in decision-making: the DL model's policy is purely risk-averse, while the RL agent's policy is value-driven. The RL agent correctly identifies and approves some high-risk applicants that the DL model denies, specifically when the potential interest revenue is high enough to justify the calculated risk.

For a comprehensive discussion of the methodology, results, and strategic recommendations, please see the **`Final_Report.pdf`** located in the `report/` directory.
