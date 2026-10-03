# Data Quality Audit — Adult Income Dataset

Verifica indipendente della qualità e rappresentatività del dato in ingresso, condotta come precondizione a qualunque controllo successivo (fairness, explainability) su un modello addestrato su questi dati.

*Case study realizzato su dataset pubblico (UCI Machine Learning Repository), a scopo dimostrativo del metodo.*

## Contesto

| | |
|---|---|
| Sistema analizzato | Modello tabellare di classificazione binaria (reddito annuo ≤/> 50.000$) |
| Dataset | Adult Income / Census Income Dataset — UCI ML Repository, 32.561 osservazioni, 15 variabili |
| Decisione supportata (nel dominio originale) | Predizione di soglia di reddito — proxy di decisioni reali come idoneità a credito o benefit |
| Riferimento normativo | Art. 10, Regolamento UE 2024/1689 (EU AI Act) — requisiti di rappresentatività, completezza e assenza di errori dei dataset di addestramento |

## Metodo

Verifica condotta su quattro assi:

- Completezza — identificazione e trattamento dei valori mancanti (inclusi placeholder non standard presenti nel dataset originale)
- Duplicati e coerenza — controllo di righe duplicate e valori fuori range
- Rappresentatività — distribuzione delle variabili sensibili (sesso, etnia) rispetto alla popolazione descritta
- Sbilanciamento del target — distribuzione delle classi della variabile da predire

Strumenti impiegati: profiling automatico (fg-data-profiling), definizione e validazione di regole di qualità formali (Great Expectations), controlli manuali di verifica incrociata sui risultati automatici — inclusa verifica indipendente sul file sorgente grezzo, al di fuori di qualunque libreria di parsing.

## Esito

Nessuna anomalia bloccante (soglia di riferimento: 30% di missing su una singola colonna; massimo osservato 5,66%). Tre osservazioni non bloccanti:

- 4.262 valori mancanti concentrati su 3 colonne (workclass, occupation, native-country) — severità bassa, gestibile in fase di modellazione.
- 24 righe duplicate (0,07%) — severità bassa.
- Rappresentatività demografica non uniforme su sesso ed etnia, con un divario di oltre 2,5 volte nel tasso di reddito elevato tra i gruppi (30,57% contro 10,95%) — severità media, raccomandato un Fairness Audit dedicato prima di qualunque utilizzo del modello in un contesto decisionale reale.

## Contenuto della cartella

| File | Descrizione |
|---|---|
| `Data-Quality-Report.pdf` | Report di sintesi con esito e raccomandazioni |
| `data_quality_report.html` | Output tecnico del profiling automatico |
| `Evidence-Register.xlsx` | Registro delle evidenze raccolte durante la verifica |
| `Testing-Workpaper.xlsx` | Dettaglio dei singoli test eseguiti, popolazione coperta ed esito |
