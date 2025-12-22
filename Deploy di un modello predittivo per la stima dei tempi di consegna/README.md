# Deploy di un modello predittivo per la stima dei tempi di consegna

## Descrizione del progetto

L'azienda **LogiFast Solutions** è un fornitore logistico che gestisce consegne urbane e interurbane per e-commerce e rivenditori. Il caso d'uso è la previsione del tempo di consegna (time-to-delivery) per ciascun ordine dal ritiro alla consegna finale, al fine di informare clienti e operatori, ottimizzare le rotte e ridurre costi operativi e reclami.

Obiettivo didattico: sviluppare, validare ed effettuare il deploy di un modello di machine learning che predice i tempi di consegna, esponendolo tramite una API REST implementata in Flask. Il progetto integra elementi di base di MLOps (versionamento, automazione e monitoraggio) e simula un flusso realistico di ML in produzione.

## Valore per l'azienda e benefici

- Migliore esperienza cliente: previsioni di consegna più accurate aumentano la trasparenza e la soddisfazione.
- Operazioni più efficienti: previsione precisa consente assegnazione dinamica delle risorse e pianificazione delle rotte.
- Riduzione dei costi: meno reinvii, ritiro di ordini e gestione dei reclami.
- Insight aziendali: monitoraggio e versionamento consentono miglioramenti continui del processo decisionale.
- Valore aggiunto: tracciamento del modello e alert su degradazione delle performance favoriscono affidabilità e scalabilità.

## Ambito e vincoli 

- Input: informazioni disponibili all'atto della presa in carico dell'ordine (es. luogo di ritiro, luogo di consegna, dimensioni/peso del pacco, metodo di spedizione, orario e data di ritiro, informazioni storiche del corriere, finestre di consegna attese, indicatori di traffico/condizioni meteo storiche o sintetiche).
- Output: stima del tempo di consegna (espressa in minuti/ore), con eventuale intervallo di confidenza o score di affidabilità.
- Requisiti non funzionali: latenza di risposta adeguata per uso operativo, interfaccia REST accessibile, logging minimo delle richieste e delle predizioni.
- Consegna tecnica: applicazione Flask che espone le API e un pacchetto di documentazione e artefatti (vedi sezione consegna).

## Modello 

Il modello è disponibile in formato Pickle a questo link: [https://github.com/Profession-AI/progetti-solution-architect/blob/main/Deploy%20di%20un%20modello%20predittivo%20per%20la%20stima%20dei%20tempi%20di%20consegna/delivery.pkl](https://github.com/Profession-AI/progetti-solution-architect/blob/main/Deploy%20di%20un%20modello%20predittivo%20per%20la%20stima%20dei%20tempi%20di%20consegna/delivery.pkl)

Il modello riceve in input i campi:

- pickup_location (stringa con la città di origine)
- delivery_location (stringa stringa con la città di destinazione)
- pickup_datetime (stringa con data/ora)
- weight (numero in virgola mobile)
- service_type (stringa "Express" o "Premium")

## Obiettivi del progetto 

1. Modello predittivo addestrato e valutato su dati di test, con report delle metriche.
2. API REST in Flask che espone:
   - endpoint di predizione per singole richieste e batch,
   - endpoint di health/status,
   - endpoint per ottenere versione del modello e metadati.
3. Documentazione che descrive schema dei dati, formato delle richieste/risposte, metriche e criterio di versione.
4. Artefatti di alto livello:
   - strategia di versionamento per dati e modelli,
   - flusso di automazione proposto (build/test/deploy concettuale),
   - piano di monitoraggio in produzione (metriche, alert, drift detection).
5. Report finale che illustra analisi esplorativa, scelta delle metriche, valutazione e piano di rollout.

Importante: la consegna tecnica deve essere implementata tramite Flask (API REST). Non è richiesta una pipeline di deploy reale, ma la soluzione deve esplicitare come i componenti verrebbero integrati in un flusso di produzione.

## Specifica API REST (alto livello)

- POST /predict
  - Input: JSON con i campi necessari per la predizione (pickup_location, delivery_location, pickup_datetime, weight, service_type)
  - Output: JSON contenente la stima del tempo di consegna (unità specificata), intervallo di confidenza opzionale, score di affidabilità.
- POST /predict/batch
  - Input: lista di record come sopra.
  - Output: lista di predizioni correlate agli input.
- GET /health
  - Output: stato operativo del servizio (OK/ERROR) e timestamp.


## Elementi MLOps da includere 

- Versionamento:
  - strategia per versionare dataset (snapshot o identificatori) e artefatti del modello (ID/versione).
  - tracciare metadati del training (parametri, metriche, data, commit).
- Automazione:
  - pipeline concettuale per qualità dati, training, test e validazione.
  - processi automatizzati per test di regressione modello e validazione pre‑deploy.
- Monitoraggio:
  - logging delle richieste e delle predizioni, raccolta delle metriche runtime e delle metriche di qualità.
  - alerting su degrado prestazioni o drift significativo.
- Governance:
  - criterio per rollback a versioni precedenti del modello.
  - piano per ri‑addestramento (trigger basati su degrado o nuova disponibilità dati).

Nota: il progetto richiede la progettazione e la documentazione di questi elementi; non è necessario implementare un intero ecosistema MLOps reale.

## Criteri di accettazione (alto livello)

- Il servizio Flask risponde correttamente agli endpoint documentati.
- Documentazione completa che include: schema dei dati, specifica API, strategia di versionamento, piano di automazione e monitoraggio.
- Fornitura di test di integrazione elementari che dimostrano l'esecuzione dell'API (descritti e forniti, non necessariamente automatizzati).
- File di consegna contenente: codice Flask (senza dipendenze specifiche hardcoded), notebook di esplorazione/validazione, modello serializzato/artefatto e README con istruzioni di avvio di alto livello.
