# Fairness Audit — COMPAS

Simulazione di audit di fairness su un sistema reale di scoring del rischio di recidiva (COMPAS), condotta su dati pubblici di terzi. Non è un incarico commissionato né un giudizio ufficiale sul prodotto commerciale.

## Cosa contiene

| File | Contenuto |
|---|---|
| Fairness-Audit-Report.pdf | Rapporto tecnico: metodo, metriche con intervalli di confidenza, calibrazione, confronto con un modello di riferimento, interpretazione e limitazioni |
| Evidence-Register.xlsx | Registro delle 10 evidenze raccolte, con fonte, data e requisito collegato |
| Testing-Workpaper.xlsx | 5 test eseguiti, con campione, risultato ed esito |
| Finding-Register.xlsx | 4 rilievi con gravità, rischio e azione correttiva proposta |

## Sintesi

| Domanda | Risposta |
|---|---|
| Che cosa è stato verificato | Se i punteggi di COMPAS e un modello semplice senza la razza tra gli input producono errori diversi per gruppi diversi (African-American e Caucasian) |
| Esito principale | Lo squilibrio storico documentato da ProPublica si riproduce: i non recidivi African-American sono classificati ad alto rischio circa 1,9 volte più spesso (FPR 0,4485 contro 0,2345) |
| Robustezza | I divari di FPR e FNR non cambiano escludendo le righe con etichette anomale (886 su 6.150, dopo il 01/04/2014) e compaiono anche in un modello senza la razza in input |
| Rilievi | 2 Major (etichette anomale; disparità di FPR e FNR), 2 Observation (calibrazione; licenza dei dati non dichiarata) |

## Metodo in breve

Due livelli di audit: A, i soli output di COMPAS (come in un incarico senza accesso al modello); B, una regressione logistica a cinque variabili per confronto. Metriche calcolate con due librerie indipendenti più un controllo manuale, intervalli di confidenza bootstrap al 95%, ripetizione su 20 divisioni train/test, replica esatta delle matrici pubblicate da ProPublica come validazione.

## Limiti

Due soli gruppi, una contea e un biennio; l'etichetta misura il riarresto, non la recidiva effettiva; sul livello A si dimostra lo squilibrio ma non se ne spiega la causa; nessuna mitigazione testata. Dettagli nel report.

## Fonti e dati

Dati e analisi di riferimento: ProPublica, «Machine Bias» e «How We Analyzed the COMPAS Recidivism Algorithm» (github.com/propublica/compas-analysis). I dati grezzi non sono inclusi in questo repository. Il repository di origine non dichiara una licenza: sono stati applicati in via prudenziale i termini del Data Store ProPublica (nessuna ridistribuzione dei dati, citazione della fonte).
