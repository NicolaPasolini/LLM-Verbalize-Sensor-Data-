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
    -   Log delle performance: `results_log.csv`
    -   Predizioni in formato JSON: `results.json`

### Setup

1.  **Install dependencies:**
    ```bash
    pip install numpy pandas tqdm scikit-learn langchain-core nomic ollama
    ```

2.  **Eseguire il login a Nomic:**
    ```bash
    nomic login --token <YOUR_NOMIC_API_KEY>
    ```

### Esecuzione

Per avviare l'esperimento, eseguire lo script principale:
```bash
python main.py
```

## 2. Occupancy Estimation

Questo modulo va oltre la semplice classificazione, richiedendo ai modelli di eseguire un'analisi in tre fasi basata sui dati dei sensori ambientali:

FORECAST: Prevedere l'evoluzione numerica dei valori dei sensori.
ANALYZE: Generare un'analisi testuale che spieghi il ragionamento alla base della previsione.
CLASSIFY: Classificare la variazione nell'occupazione della stanza.

Prerequisiti
Dataset: Scaricare il file Occupancy_Estimation.csv da UCI Machine Learning Repository.

Modelli LLM: 
Assicurarsi di aver scaricato i modelli necessari tramite Ollama.
```bash
# Modello principale per l'esperimento
ollama pull llama3.1:8b
# Modello alternativo per l'esperimento
ollama pull zephyr
# Modello "giudice" per la valutazione qualitativa
ollama pull llama3.1:70b
```


