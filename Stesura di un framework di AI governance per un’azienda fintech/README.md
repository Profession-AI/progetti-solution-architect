# Stesura di un framework di AI governance per un’azienda fintech

L'azienda  **CrediPulse S.p.A.** è una fintech che offre soluzioni di credito digitale a PMI e microimprese. CrediPulse utilizza sistemi di intelligenza artificiale per l’analisi del rischio creditizio, che combinano dati transazionali bancari, informazioni contabili, dati di comportamento digitale e dati alternativi per supportare decisioni di scoring, pricing e monitoraggio continuo dei portafogli.

Obiettivo generale: definire un framework di governance ad alto livello che renda i sistemi di AI per il credit scoring conformi ai requisiti normativi (AI Act), coerenti con i principi di responsabilità e trasparenza, e adeguati a documentare e gestire i rischi legati all’uso di AI ad alto rischio.

Consegna: documento formale e allegati (template).

Caso d'uso primario: un modello di scoring automatico che determina una valutazione del rischio e una raccomandazione di offerta (approvazione, rifiuto, offerta condizionata) per richieste di finanziamento da parte di PMI. Il sistema è classificato come "AI ad alto rischio" ai sensi dell'AI Act per l'impatto sulle decisioni economiche dei richiedenti.

Impatto aziendale: il modello supporta le decisioni di credito su volumi significativi di pratiche, influisce su tassi di approvazione, pricing, accantonamenti e reputazione della società.

Perché questo progetto è importante per CrediPulse:
- Riduce il rischio regolatorio e legale derivante dall'uso di AI ad alto impatto.
- Migliora la tracciabilità e la responsabilità nelle decisioni di credito.
- Rafforza la fiducia di clienti, partner e autorità di vigilanza.
- Facilita integrazione e scaling di modelli AI con criteri di compliance definiti.

Valore aggiunto:
- Standardizzazione della documentazione e dei processi decisionali.
- Chiarezza dei ruoli e delle responsabilità per decisioni complesse.
- Diminuzione del rischio reputazionale e operazionale.
- Base per audit interni/esterni e per future certificazioni di conformità.

## Ambito del progetto 

Inclusi:
- Sistemi AI impiegati nella fase di scoring, pricing e monitoraggio del rischio creditizio.
- Processi di governance correlati (ruoli, accountability, documentazione).
- Mappatura dei rischi secondo categorie rilevanti dell'AI Act e preparazione di una simulazione di analisi di conformità per sistemi ad alto rischio.
- Produzione di template di documentazione (Model Card / FRIA / risk register / RACI).

Esclusi:
- Implementazioni tecniche, scelta o tuning di algoritmi specifici.
- Dettagli operativi di integrazione nei sistemi di produzione.
- Attività tecniche di mitigazione concrete (es. modelli, tecniche di preprocessing).

## Obiettivi specifici

1. Redigere un framework di governance di alto livello per i sistemi di credit scoring AI.
2. Definire ruoli e responsabilità (RACI) correlati all’intero ciclo di vita del modello.
3. Mappare i principali rischi legali, etici e operativi secondo i requisiti dell'AI Act e classificare la loro severità e priorità.
4. Preparare template per la documentazione di accountability: Model Card e FRIA.


## Deliverable 

- Documento principale: Framework di AI Governance (struttura, principi, processi di alto livello).
- Template RACI e matrice dei ruoli.
- Risk Register template con categorie di rischio e campi per evidenze.
- Model Card template per modelli di scoring.
- FRIA (Fundamental Rights Impact Assessment) template.


## Mappatura dei rischi (categorie secondo AI Act e governance)

Per ogni categoria di rischio il framework richiede: descrizione del rischio, possibili impatti sul cliente e sull’azienda, metriche/indicatori ad alto livello per monitoraggio, livello di severità previsto (Basso/Medio/Alto) e accountability organizzativa.

Categorie principali:
- Rischio di discriminazione e bias: impatti su gruppi protetti e non protetti; rischio reputazionale e legale.
- Accuratezza e affidabilità (performance): errori sistematici che portano a decisioni errate di credito.
- Trasparenza e spiegabilità: limiti nella capacità di comunicare motivazioni delle decisioni ai richiedenti e alle autorità.
- Protezione dei dati e privacy: trattamento dei dati personali, minimizzazione, conservazione e trasferimenti.
- Robustezza e resilienza operativa: rischio di degrado delle prestazioni nel tempo o di vulnerabilità a manipolazioni.
- Sicurezza informatica e integrità dei dati: compromissione dei dati o dell’integrità del modello.
- Rischio di governance e accountability: mancanza di responsabilità chiare o di processi decisionali documentati.
- Rischio contrattuale/fornitori terzi: dipendenza da fornitori esterni senza adeguate garanzie.
- Rischio sistemico e di mercato: impatti aggregati su portafoglio e stabilità finanziaria.
- Rischio normativo e di compliance: non conformità ai requisiti dell'AI Act e alle leggi finanziarie.

Il framework prevede la redazione di una mappa dei rischi per ciascun modello AI, con classificazione del rischio e assegnazione del proprietario.

## Documentazione di accountability (Model Card / FRIA) — contenuti ad alto livello

Model Card (contenuti richiesti):
- Identificazione del modello: nome, versione, data, ID.
- Scopo e uso previsto: descrizione dell’uso autorizzato e dei contesti proibiti.
- Proprietari e contatti: Model Owner, Model Steward, Data Owner.
- Dati: descrizione ad alto livello delle tipologie di dati usati (fonti, periodo temporale), politica di conservazione.
- Metriche di performance: indicatori principali, ambito di validità e condizioni di performance.
- Valutazioni di equità: sintesi delle valutazioni effettuate e aree di attenzione.
- Limitazioni note e condizioni di degrado.
- Requisiti di monitoraggio e frequenza delle revisioni.
- Requisiti di supervisione umana: descrizione del ruolo umano e delle responsabilità.
- Note normative/compliance: classificazione AI Act e riferimenti alle richieste documentali.
- Registro delle versioni e storico delle modifiche.

FRIA (Fundamental Rights Impact Assessment) — struttura ad alto livello:
- Contesto e descrizione del sistema AI.
- Diritti fondamentali potenzialmente impattati (es. non discriminazione, diritto alla protezione dei dati, diritto a un processo decisionale equo).
- Mappatura degli attori coinvolti e dei soggetti interessati.
- Valutazione del rischio per ciascun diritto fondamentale (probabilità, gravità).
- Misure organizzative previste a supporto della tutela dei diritti (policy, governance, accountability).
- Gap identificati a livello di conformità e responsabilità.
- Conclusioni e raccomandazioni di governance (non tecniche).
- Tracciamento del follow-up e responsabilità per azioni correttive.

Nota: entrambi i documenti sono concepiti come strumenti di accountability leggibili da auditor, autorità e stakeholder esterni/intermedi.

## Criteri di successo 

- Esistenza di un framework approvato dal Board che definisce ruoli e processi di governance.
- Template di Model Card e FRIA pronti e utilizzabili per i modelli in produzione.
- Completamento di una simulazione di compliance con gap identificati e owner assegnati.
- Piano di governance che consenta a CrediPulse di dimostrare lo sforzo di conformità a interlocutori interni ed esterni.
- Migliorata chiarezza su responsabilità e punti di controllo per le decisioni AI.

## Benefici per l’azienda

- Maggiore facilità di dimostrare conformità normativa e readiness verso audit e autorità.
- Riduzione dei rischi reputazionali e legali legati a decisioni creditizie automatizzate.
- Processi chiari che facilitano l’integrazione di nuovi modelli e la gestione del portafoglio.
- Aumento della fiducia di clienti e partner grazie alla trasparenza e documentazione di responsabilità.
- Miglioramento della governance interna che favorisce efficienza decisionale e resilienza operativa.
