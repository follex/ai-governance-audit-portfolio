# AI Governance Audit — Portfolio

Raccolta di case study su verifiche indipendenti di sistemi di intelligenza artificiale (data quality, fairness, explainability, robustness, documentazione), condotte secondo un metodo strutturato e allineato a EU AI Act (Reg. UE 2024/1689), NIST AI RMF e ISO/IEC 42001.

Ogni case study è realizzato su modelli e dataset pubblici, a scopo dimostrativo del metodo. Per ciascuno sono disponibili i deliverable prodotti (report, registro delle evidenze, working paper di test), nello stesso formato usato in un incarico reale.

> Il codice di analisi non è pubblicato in questo repository: fa parte del know-how professionale utilizzato per produrre i risultati. Ogni case study documenta comunque, in modo dettagliato, gli strumenti impiegati e il metodo seguito.

## Chi sono

Alessandro Littera, AI Auditor indipendente specializzato in conformità, governance e gestione del rischio dei sistemi di intelligenza artificiale — EU AI Act, ISO/IEC 42001, ISO/IEC 23894, GDPR applicato a sistemi AI.

## Case study

| Case study | Cosa verifica | Modello/dataset |
|---|---|---|
| [Data Quality Audit — Adult Income](./case-study-data-quality-audit-adult-income) | Completezza, duplicati, rappresentatività, sbilanciamento del target | Adult Income Dataset (UCI) |
| Fairness Audit — COMPAS *(in arrivo)* | Demographic Parity, Equalized Odds, False Positive Rate per gruppo | COMPAS two-years (ProPublica) |
| Explainability Audit — Titanic *(in arrivo)* | Spiegabilità globale e locale (SHAP, LIME) | Titanic (Kaggle) |
| Robustness Audit — MNIST *(in arrivo)* | Robustezza a rumore e ad attacco avversariale (FGSM) | MNIST |
| Bias & Robustness Audit NLP — DistilBERT *(in arrivo)* | Bias su gruppi demografici, stabilità a perturbazioni testuali | DistilBERT (sentiment analysis) |
| Audit end-to-end — German Credit *(in arrivo)* | Verifica completa multi-asse, simulazione di incarico reale | German Credit Dataset (Statlog) |

## Metodo

Ogni verifica segue lo stesso processo, tracciabile e basato su evidenze:

1. Inquadramento del sistema (tipo, decisione supportata, soggetti impattati, accesso disponibile, livello di rischio)
2. Pianificazione dei controlli e dei criteri di riferimento
3. Esecuzione di test tecnici con strumenti riconosciuti del settore (ydata-profiling, Great Expectations, Fairlearn, AIF360, SHAP, LIME, ART, ecc.)
4. Registrazione delle evidenze raccolte
5. Reportistica con esito, livello di rischio e raccomandazioni

## Contatti

*(email / LinkedIn / sito web)*
