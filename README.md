# LLM-Verbalize-Sensor-Data

This project explores the use of Large Language Models (LLMs) for **verbalizing, interpreting, and predicting sensor data** across two domains:

- **Human Activity Recognition (HAR):** Classification of exercises from wearable sensors (wrist, pocket, leg), with evaluation of zero-shot, few-shot, and Retrieval-Augmented Generation (RAG) techniques.  
- **Occupancy Estimation (Environmental Monitoring):** Prediction of sensor trends, classification of room occupancy, and generation of descriptive explanations.

---

## 1. Human Activity Recognition (HAR)

- **Input:** CSV dataset (`RecGym.csv`) + knowledge base (`knowledge_base.json`)  
- **Output:** Accuracy logs (`results_log.csv`) and predictions (`results.json`)  

### Setup
```bash
pip install numpy pandas tqdm scikit-learn langchain-core nomic ollama
nomic login --token <YOUR_API_KEY>
### Run
'''bash
python main.py


2) Occupancy Estimation

The primary task goes beyond simple classification, requiring the models to perform a three-stage analysis:

PREDICT: Predict the numerical evolution of the sensors.

ANALYZE: Generate a textual analysis that explains its reasoning.

PREDICT: Classify the change in room occupancy.

The project includes quantitative performance analysis (accuracy, MAE, execution time) and automated qualitative evaluation of the textual analyses using an LLM-as-a-Judge approach.

Prerequisites
  * File data: the dataset Occupancy_Estimation.csv is in https://archive.ics.uci.edu/dataset/864/room+occupancy+estimation
  * Model : Download the LLM Templates: Run the cell that executes the ollama pull commands. The required templates are:
            llama3.1:8b (Template for the experiment)
            zephyr (Template for the experiment)
            llama3.1:70b (Template "judge" for qualitative evaluation)

Result 

This run generates the files :
   llm_forecast_results.csv : The complete file with the detailed results of each single query executed (input, model output, times, etc.).
   performance summary.csv : a summary table with aggregated quantitative metrics for each experimental configuration.
   qualitative_evaluation_sample.csv : Containing the quality scores (Relevance, Clarity, Consistency) and justifications assigned by the judge model to a sample of the results.

