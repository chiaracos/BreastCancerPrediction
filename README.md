# Breast Cancer Prediction

Progetto di **Machine Learning** per la classificazione del cancro al seno come benigno o maligno, sviluppato come primo approccio al campo dell'Intelligenza Artificiale nell'ambito del corso di **Fondamenti di Intelligenza Artificiale**.

---

## Obiettivo

Costruire un modello di classificazione binaria in grado di predire, a partire da caratteristiche cliniche di un tumore, se esso sia **benigno (B)** o **maligno (M)**.

Gli obiettivi principali includono:
- Analisi approfondita dei dati clinici
- Identificazione delle feature più rilevanti per la diagnosi
- Implementazione e confronto di modelli di Machine Learning per la classificazione

---

## Dataset

Il dataset utilizzato è il **Breast Cancer Wisconsin Dataset**, disponibile su Kaggle:
🔗 [https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)

- **569 campioni**, **32 colonne** (caratteristiche cliniche del tumore)
- Variabile target: `diagnosis` → **B** (benigno) o **M** (maligno)
- Distribuzione: 357 B (62,7%) e 212 M (37,3%) → dataset sbilanciato

---

## Pipeline del progetto

Il progetto segue la metodologia CRISP-DM, articolata nelle seguenti fasi:

### 1. Data Understanding
- Esplorazione del dataset e analisi della distribuzione delle classi
- Individuazione di problemi di qualità: sbilanciamento delle classi, colonna completamente nulla

### 2. Data Preparation
- **Data Cleaning**: rimozione della colonna nulla, codifica della variabile target (B→0, M→1), verifica di valori nulli e duplicati
- **Train/Test Split** prima dello scaling (per evitare data leakage)
- **Feature Scaling**: normalizzazione Min-Max delle feature
- **Feature Selection**: analisi della matrice di correlazione (heatmap) ed eliminazione delle feature ridondanti multicollineari
- **Data Balancing**: applicazione di **Random Undersampling** sulla classe maggioritaria per bilanciare il dataset

### 3. Modellazione
Confronto empirico tra due algoritmi di classificazione:

| Algoritmo | Variante scelta | Motivazione |
|-----------|-----------------|-------------|
| **Naive Bayes** | Gaussian NB (GNB) | Migliori performance tra MNB, GNB e BNB |
| **Decision Tree** | DTC (max_depth=3) | Ottimizzato tramite ricerca empirica della profondità |

### 4. Evaluation
- Metriche usate: **Accuratezza**, **Precisione**, **Recall**
- Curva **ROC-AUC** per valutare il trade-off tra sensibilità e specificità
- Il **Decision Tree (DTC)** ha ottenuto le migliori performance complessive, con **AUC = 0.96**

---

## Tecnologie utilizzate

| Strumento | Ruolo |
|-----------|-------|
| Python | Linguaggio principale |
| scikit-learn | Modelli ML, preprocessing, valutazione |
| Pandas | Gestione e analisi del dataset |
| Matplotlib / Seaborn | Visualizzazione dati e risultati |
| Jupyter Notebook (PyCharm) | Ambiente di sviluppo |
| GitHub | Versionamento |
| Overleaf (LaTeX) | Documentazione |
| Canva | Presentazione |

---

## Struttura del repository

```
BreastCancerPrediction/
├── BreastCancerPrediction.ipynb   # Notebook completo: dati, modelli, risultati
├── BreastCancerPrediction.tex     # Documentazione in LaTeX
├── data.rar                       # Dataset (Breast Cancer Wisconsin)
├── Documentazione/                # Documentazione PDF
└── Presentazione/                 # Slide della presentazione
```

---

## Come eseguire

1. Clona il repository:
```bash
git clone https://github.com/chiaracos/BreastCancerPrediction.git
```

2. Installa le dipendenze:
```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
```

3. Apri il notebook:
```bash
jupyter notebook BreastCancerPrediction.ipynb
```

---

Progetto sviluppato nell'ambito del corso di **Fondamenti di Intelligenza Artificiale** come primo approccio al Machine Learning. Il tema scelto — la predizione del cancro al seno — è clinicamente rilevante: una diagnosi precoce e accurata può migliorare significativamente la prognosi e le possibilità di sopravvivenza dei pazienti.

---

