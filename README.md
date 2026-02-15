# Analisi Dataset Assessing Mathematics Learning in Higher Education (AMLHE)

## Autori
* Simone Manunza (2156783) - manunza.2156783@studenti.uniroma1.it
* Allegra Berardi (2116628) - berardi.2116628@studenti.uniroma1.it 
* Sofia Bruno (2146543) - bruno.2146543@studenti.uniroma1.it 

---

## Istruzioni per runnare il codice
Per runnare il codice ed ottenere i risultati attesi si carichi su colab, o la piattaforma utilizzata il file "dataset_IA_corretto.csv". Una volta caricato questo, far runnare il programma dalla prima cella di importazione librerie, così facendo i risultati saranno generati correttamente. 

---

## Abstract
Il progetto analizza un dataset relativo agli studi matematici di studenti delle scuole superiori in diversi paesi. Attraverso l'Exploratory Data Analysis (EDA) sono state studiate le domande, i livelli di difficoltà e le performance per nazione. Successivamente, sono stati addestrati modelli di Machine Learning (Random Forest e Logistic Regression) per prevedere la correttezza delle risposte degli studenti.

---

## Descrizione del Dataset
* **Titolo**: Assessing Mathematics Learning in Higher Education (AMLHE).
* **Dimensioni**: 9.546 osservazioni e 8 feature.
* **Feature**: Student ID, Student Country, Question ID, Type of Answer, Question Level, Topic, Subtopic, Keywords.
* **Preprocessing**: È stato necessario correggere un errore di encoding relativo ai caratteri di apostrofo utilizzando uno script Python per identificare la posizione del carattere errato e cambiarlo.

---

## Analisi Esplorativa dei Dati (EDA)
Dall'analisi dei dati sono emersi i seguenti risultati:
* **Risposte**: 4.470 risposte corrette (46,8%) e 5.076 errate (53,2%).
* **Livelli**: 7.844 domande di livello Basic e 1.702 di livello Advanced.
* **Performance per Paese**: La Slovenia ha registrato la percentuale di successo più alta (68,7%), mentre la Russia la più bassa (34,6%).
* **Topic critici**: Linear Algebra è il topic più frequente (5.726 domande). I topic più difficili risultano essere Differentiation (34,2% successo) e Real Functions (35,4%).

---

## Metodi e Modelli
Sono stati implementati due modelli di classificazione:
1. **Logistic Regression (LR)**: Modello che calcola la probabilità tramite funzione sigmoide, efficace per dataset linearmente separabili.
2. **Random Forest (RF)**: Metodo basato sulla combinazione di molti alberi decisionali per catturare interazioni complesse tra le variabili.

### Configurazione del Training
* **Split**: 80% Training Set e 20% Test Set.
* **Stratificazione**: Utilizzata per mantenere bilanciata la proporzione tra risposte corrette ed errate nei due set, dato lo sbilanciamento delle feature riscontrato nell'EDA.
* **Feature Engineering**: Applicazione di One-Hot Encoding per le variabili categoriche e Natural Language Processing (CountVectorizer con 30 max features) per la colonna Keywords.

---

## Valutazione e Risultati
Il confronto ha mostrato che la Logistic Regression ha ottenuto risultati leggermente più accurati rispetto alla Random Forest, con una differenza di 4 predizioni corrette in più.

| Metrica | Random Forest | Logistic Regression |
| :--- | :--- | :--- |
| **Accuratezza** | 56,75% | **56,96%** |
| **Predizioni Corrette** | 1.084 | **1.088** |



---

## Conclusioni e Limiti
* **Preprocessing**: La codifica tramite Label Encoding e One-Hot Encoding è risultata fondamentale per l'analisi computazionale.
* **Bias**: Il dataset presenta sbilanciamenti tra risposte correte ed errate, la stratificazione è stata impiegata per mitigare questo effetto, ma comunque risulta esistere un bias nell'addestramento dei modelli.

---
