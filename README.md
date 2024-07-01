# Project 1: Analysis of the implementation of the Cholesky method in open source programming environments.

Il progetto di Metodi del Calcolo Scientifico ha l'obiettivo di analizzare l'implementazione di un solutore basato sul metodo di Cholesky per la risoluzione di sistemi lineari con matrici sparse, simmetriche e definite positive. Il fine ultimo è di confrontare le implementazioni in Matlab e Python in termini di tempo di esecuzione, accuratezza dei risultati, utilizzo della memoria, facilità d'uso e qualità della documentazione. Le matrici sparse, caratterizzate da un elevato numero di elementi nulli, consentono di ridurre i costi computazionali, rendendo il metodo di Cholesky particolarmente efficiente e adatto a questo tipo di problemi.

### Tecnologie Utilizzate

**Matlab:**
- **Versione:** R2022a
- **Funzionalità:** Matlab offre una vasta gamma di funzioni di algebra lineare, tra cui la fattorizzazione di Cholesky, senza la necessità di dipendenze aggiuntive. È utilizzato per la sua capacità di risolvere matrici sparse, simmetriche e definite positive in modo efficiente.

**Python:**
- **Versione:** 3.10
- **Librerie:**
  - **SciPy (1.9.0):** Impiegata per le sue avanzate funzioni di algebra lineare, in particolare `scipy.sparse` per la gestione delle matrici sparse e `scipy.sparse.linalg` per la risoluzione di sistemi lineari.
  - **NumPy (1.22.4):** Fondamentale per la manipolazione di array multidimensionali e operazioni matematiche.
  - **Memory Profiler (0.61.0):** Utilizzata per l'analisi dettagliata dell'uso della memoria.
  - **Pandas (1.4.3):** Essenziale per la gestione e l'analisi dei dati.
  - **Matplotlib (3.5.1):** Utilizzata per la visualizzazione dei dati e la creazione di grafici.

Il progetto fornisce un'analisi dettagliata e un confronto tra le soluzioni implementate in Matlab e Python, valutando le prestazioni su diverse piattaforme operative, utilizzando matrici reali provenienti dalla SuiteSparse Matrix Collection. Questo lavoro offre una panoramica approfondita delle capacità e delle limitazioni delle diverse tecnologie di calcolo scientifico, giustificando l'utilizzo di ambienti open source rispetto a quelli proprietari.

# Project 2: Compression of gray tone images using the Discrete Cosine Transform (DCT2) in an open source environment.

Questo progetto esamina la compressione di immagini in toni di grigio utilizzando la Trasformata Discreta del Coseno bidimensionale (DCT2) in un ambiente open source. Il lavoro si articola in due componenti principali: un'analisi comparativa delle prestazioni della DCT2 e lo sviluppo di un algoritmo di compressione basato su DCT2, simile a JPEG ma senza l'uso di una matrice di quantizzazione.

## Obiettivi
1. Implementare una versione custom della DCT2 e confrontarne le prestazioni con l'implementazione della libreria dell'ambiente utilizzato (SciPy).
2. Condurre un'analisi comparativa dei tempi di esecuzione su array quadrati di dimensione N x N, variando N.
3. Sviluppare e analizzare un algoritmo di compressione di immagini ispirato a JPEG, utilizzando la DCT2 senza matrice di quantizzazione.
4. Creare un'interfaccia utente che permetta la selezione di un'immagine in formato .bmp in toni di grigio, l'inserimento dei parametri F e d, e la visualizzazione dell'immagine originale e compressa per confronto.

## Tecnologie Utilizzate
- **Linguaggio di Programmazione**: Python
- **Librerie Scientifiche**: NumPy, SciPy
- **Analisi dei Dati**: Pandas
- **Visualizzazione**: Matplotlib
- **Elaborazione Immagini**: PIL (Python Imaging Library)
- **Interfaccia Utente**: PySimpleGUI
- **Controllo Versione**: Git



