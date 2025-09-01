# LLM-Verbalize-Sensor-Data-

1) HAR
   


3) Occupancy Estimation

This project uses several open-source large-scale linguistic models (LLMs) to analyze, interpret, and verbalize time-series sensor data from a room occupancy monitoring        environment.

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

