# LLM-Verbalize-Sensor-Data

This project explores the use of Large Language Models (LLMs) to verbalize, interpret and predict sensor data in two application domains:
-   **Human Activity Recognition (HAR):**Classification of physical exercises using data from wearable sensors (wrist, pocket, leg), with evaluation of zero-shot, few-shot and Retrieval-Augmented Generation (RAG) techniques.
-   **Occupancy Estimation:** Predict sensor behavior, classify room occupancy, and generate descriptive explanations.

---

## 1. Human Activity Recognition (HAR)

This module classifies physical exercises using data from wearable sensors.

-   **Input:**
    -   Dataset in formato CSV: `RecGym.csv`
    -   Knowledge base opzionale per RAG: `knowledge_base.json`
-   **Output:**
    -   accuracy log: `results_log.csv`
    -   predictions: `results.json`

### Setup

1.  **Install dependencies:**
    ```bash
    pip install numpy pandas tqdm scikit-learn langchain-core nomic ollama
    ```

2.  **Log into Nomic:**
    ```bash
    nomic login --token <YOUR_NOMIC_API_KEY>
    ```

### Execution

To run the experiment:
```bash
python main.py
```

## 2. Occupancy Estimation

This module goes beyond simple classification, requiring models to perform a three-step analysis based on environmental sensor data:

FORECAST: Predict the numerical evolution of sensor values.
ANALYZE: Generate a textual analysis explaining the reasoning behind the prediction.
CLASSIFY: Classify the change in room occupancy.

Prerequisites
Dataset: Download the Occupancy_Estimation.csv file from the UCI Machine Learning Repository.

LLM Models:
Make sure you have downloaded the required models via Ollama.
```bash
# Main model for the experiment
ollama pull llama3.1:8b
# Alternative model for the experiment
ollama pull zephyr
# "Judging" model for qualitative evaluation
ollama pull llama3.1:70b
```
# Input:
File data: The dataset is in https://archive.ics.uci.edu/dataset/864/room+occupancy+estimation

# Output:
llm_forecast_results.csv: The complete file with the detailed results of each single query executed.
performance_summary.csv: A summary table with aggregate quantitative metrics for each experimental setup.
qualitative_evaluation_sample.csv: A file containing the quality scores (Relevance, Clarity, Consistency) and justifications assigned by the judge model to a sample of the results.
