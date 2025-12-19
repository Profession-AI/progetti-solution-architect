# Architettura di Data Governance per un’azienda farmaceutica

L'azienda **NovaCura Pharma** è una società farmaceutica orientata alla ricerca e sviluppo di terapie per malattie rare e alla conduzione di studi clinici internazionali. Il progetto mira a progettare una piattaforma di Data Governance e Knowledge Management a livello aziendale per supportare in modo sicuro, tracciabile e riproducibile progetti di AI (es. modelli per discovery, farmacovigilanza, arruolamento pazienti, stratificazione dei soggetti).

Il progetto copre le seguenti aree di alto livello:
- Policy e linee guida per la gestione dei dati aziendali (compliance, privacy, conservazione, accesso).
- Tracciamento del data lineage per garantire provenienza e riproducibilità dei dataset e dei risultati dei modelli.
- Data catalog e metadata management per rendere i dati facilmente scoperti e riutilizzabili.
- Knowledge graph per rappresentare entità biomediche, relazioni tra studi, soggetti, farmaci e concetti clinici.
- Integrazione di un flusso RAG (Retrieval-Augmented Generation) per supportare attività di generazione di conoscenza contestuale nella fase di ricerca e documentazione.
- Produzione di documentazione tecnica e diagrammi architetturali a supporto dell'adozione.

La consegna finale del progetto includerà componenti basate su SQL e artefatti pensati per ambienti Big Data (schemi, specifiche di pipeline, query di esempio e script di validazione), insieme alla documentazione progettuale.


Obiettivo concreto: supportare un programma di drug repurposing che integra dati di studi clinici interni, dataset di laboratorio (assay), annotazioni letteratura scientifica e report di farmacovigilanza. L'AI deve poter:
- Ricercare e aggregare evidenze rilevanti per un candidato farmaco.
- Fornire spiegazioni contestuali delle decisioni (provenienza dati, estratti testuali, relazioni tra entità).
- Consentire audit completo della pipeline dai dati grezzi al risultato finale per scopi regolatori.

Questo richiede governance dei dati, metadati ricchi, tracciamento del lineage e un knowledge graph che colleghi entità rilevanti; il flusso RAG permette al team di generare report contestuali e sintetici a partire da fonti verificate.

## Importanza per l'azienda
- Compliance regolatoria: garanzia di tracciabilità e auditabilità dei dataset e dei workflow AI.
- Accelerazione R&D: riduzione dei tempi di scoperta grazie a ricerca dati più veloce e riutilizzo di conoscenza interna.
- Qualità e fiducia dei modelli: dati governati e linee di provenienza migliorano la riproducibilità e l'affidabilità dei risultati.
- Riduzione del rischio: gestione centralizzata delle policy di accesso e conservazione dei dati sensibili.
- Valore strategico: creazione di un patrimonio conoscitivo riutilizzabile (knowledge graph) che aumenta il valore intellettuale aziendale.

## Benefici e valore aggiunto
- Accesso rapido e controllato ai dataset pertinenti.
- Riduzione del lavoro duplicato e miglior uso delle competenze interne.
- Migliore interpretabilità dei risultati AI grazie a riferimenti ai dati originali (lineage) e alla conoscenza strutturata.
- Supporto decisionale continuo per clinici e ricercatori con documentazione contestuale automatizzata.
- Potenziamento della collaborazione interdisciplinare (clinici, data scientist, regulatory).

## Ambito del progetto
- Catalogazione e metadatazione dei dataset clinici, di laboratorio, amministrativi e documentali rilevanti per R&D.
- Definizione di policy di data governance (accesso, retention, classificazione, anonimizzazione/ pseudonimizzazione).
- Specifica logica del data lineage end-to-end per flussi tipici (ingest → trasformazione → analisi → modello).
- Modello concettuale per un knowledge graph di dominio.
- Specifica funzionale per integrazione RAG (document store, retriever, interfaccia di generazione) a livello di requisiti e flussi informativi.
- Consegna di documenti, SQL e artefatti Big Data per dimostrare l'applicabilità delle specifiche.

Escluso:
- Implementazione operativa in ambiente di produzione.
- Scelta o configurazione di prodotti o tecnologie specifiche.
- Training operativo degli utenti oltre alla documentazione progettuale.

## Requisiti funzionali
1. Data Catalog
   - Scheda per ogni dataset con nome, descrizione, proprietario, sensibilità, formato, campi principali, aggiornamento e link a campioni.
2. Metadata Management
   - Standard minimo per metadati (definizione campi, semantica, tag semantici, versioning dei metadati).
3. Data Lineage
   - Tracciabilità delle trasformazioni, delle tabelle/collezioni sorgente, dei processi ETL/ELT logici e dei modelli che consumano i dati.
4. Policy Management
   - Documenti delle policy di classificazione dati, gestione degli accessi, conservazione e requisiti di compliance; mapping tra policy e dataset.
5. Knowledge Graph
   - Modello concettuale di nodi e relazioni per rappresentare entità cliniche, molecole, trial, endpoint e relazioni tra documenti e dati sperimentali.
6. Flusso RAG (alto livello)
   - Specifica del flusso informativo per retrieval (cosa si indicizza/recupera), criteri di selezione delle fonti e requisiti di tracciamento della provenienza per output generati.
7. Audit & Reportistica
   - Requisiti per audit trail sulle operazioni di accesso, modifica metadati e processo di generazione dei risultati AI.
8. Supporto SQL e Big Data
   - Requisiti per artefatti SQL (es. query di validazione e trasformazione) e definizione di schemi e specifiche per ambienti Big Data (e.g., partizionamento logico, formati di dataset, sample schemas).

## Requisiti non funzionali 
- Scalabilità: supportare crescita volumetrica e nuovi domini di dati.
- Sicurezza e privacy: requisiti generali di protezione delle informazioni sensibili e di segregazione dei ruoli.
- Affidabilità e disponibilità: definire livelli attesi di accessibilità delle risorse informative.
- Interoperabilità: metadati e schemi coerenti per facilitare integrazione tra team e strumenti.
- Manutenibilità: linee guida per versioning di dataset e metadati.
- Tracciabilità e auditabilità: conservare informazioni necessarie per ricostruire processi a fini regolatori.


## Artefatti richiesti per la consegna
Documentazione tecnica (documenti in formato leggibile):
- Documento di requisiti di alto livello.
- Policy di Data Governance (classification, access, retention, privacy, data sharing) — versione aziendale high-level.
- Specifica del modello di metadati (campi obbligatori/facoltativi, vocabolari, versioning).
- Specifica logica del data lineage (dizionari di trasformazione, attributi di provenienza).
- Modello concettuale del Knowledge Graph con esempi di nodi/relazioni.
- Specifica funzionale del flusso RAG: tipi di documenti indicizzati, criteri di retrieval, requisiti di tracciabilità per output.
- Piano di test e criteri di accettazione.

Artefatti tecnici (da fornire come file):
- Set di query SQL di esempio per: profilazione, validazione qualità, estrazione campioni e trasformazioni logiche; commentate e versionate.
- Schemi e specifiche per componenti Big Data: definizione logica di tabelle/collezioni distribuite, metadati di partizionamento e campioni di manifest; descrizioni di pipeline e job in forma astratta (flow diagrams e pseudocodice non eseguibile).

## Criteri di valutazione
- Completezza dei requisiti: copertura delle aree richieste (catalog, metadata, lineage, policy, KG, RAG).
- Chiarezza e coerenza della documentazione tecnica e dei diagrammi architetturali.
- Qualità e utilizzabilità degli artefatti SQL e Big Data (commenti, coerenza con il modello di metadati).
- Realismo del caso d'uso e corrispondenza delle soluzioni proposte al contesto regolatorio e aziendale.
- Tracciabilità: presenza di elementi che permettono di ricostruire il percorso dati → modello → output.
- Considerazioni di sicurezza e privacy a livello di policy e requisiti non funzionali.
- Facilità di adozione: chiarezza delle responsabilità e delle modalità di integrazione organizzativa.


## Esempi di contenuti attesi 
- Esempio di campi minimi della scheda Data Catalog: id_dataset, nome, descrizione, owner, steward, tag_semantici, sensibilità, frequenza_aggiornamento, schema_pointer, esempio_dati, lineage_reference, policy_reference.
- Esempio di attributi per una voce di Data Lineage: id_process, input_datasets, output_datasets, trasformazioni_descrizione, autore, timestamp, versione, link_documentazione.
- Esempio di elementi nel Knowledge Graph (concettuale): nodi = {Farmaco, Target Molecolare, StudiClinici, Biomarker, PazienteAggregato, Endpoint}; relazioni = {testa_in, associato_a, osservato_in, influenza}.
- Esempio di requisiti per il flusso RAG (alto livello): indicizzare solo documenti approvati, tracciare id_documento e offset testuale come fonte per ogni paragrafo restituito, includere riferimento al record di provenienza nel report generato.

