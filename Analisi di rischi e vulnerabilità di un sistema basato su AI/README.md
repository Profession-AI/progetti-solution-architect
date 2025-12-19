# Analisi di rischi e vulnerabilità di un sistema basato su AI


Obiettivo generale: condurre un’analisi completa della sicurezza di un ecosistema AI per la visione artificiale in ambito urbano, valutando rischi e vulnerabilità (data poisoning, attacchi adversarial, furto di modelli), proponendo contromisure ad alto livello allineate alla triade CIA (Confidentiality, Integrity, Availability) e analizzando la conformità normativa a GDPR, AI Act e NIS2. Include un incident report simulato come esercitazione pratica.

Consegna: documento finale contenente relazione principale, registro dei rischi, analisi di conformità, e report d’incidente simulato.

## Caso d'uso 

UrbanSight fornisce ai comuni una piattaforma di visione artificiale per il monitoraggio urbano: analisi del flusso veicolare, riconoscimento delle situazioni di pericolo (incidenti stradali, ingorghi), rilevazione di comportamenti pedonali a rischio (attraversamenti pericolosi), gestione intelligente dei semafori in tempo reale e dashboard per la pianificazione urbana.

Importanza del progetto per l’azienda:
- Mitigare rischi che possono causare danni a persone, perdite contrattuali e danni reputazionali.
- Dimostrare conformità normativa per contratti con enti pubblici.
- Migliorare resilienza operativa e fiducia degli stakeholder (municipalità, cittadini, assicurazioni).

Benefici e valore aggiunto:
- Riduzione del rischio legale e operativo.
- Migliore posizionamento commerciale attraverso evidenze di governance della sicurezza e compliance.
- Supporto alle decisioni strategiche e alla continuità di servizio.

## Obiettivi specifici
- Mappare l’ecosistema AI (componenti, dati, flussi, interazioni con terze parti) a livello concettuale.
- Identificare e classificare rischi e vulnerabilità rilevanti per la visione artificiale in ambito urbano.
- Valutare impatti e probabilità per ciascun rischio (criteri qualitativi).
- Proporre contromisure ad alto livello basate su CIA.
- Verificare requisiti di conformità con GDPR, AI Act e NIS2, individuando gap di alto livello.
- Redigere un incident report simulato che illustri la gestione e le implicazioni di un evento significativo.
- Fornire raccomandazioni organizzative, di governance e di processo (non tecniche).

## Ambito e esclusioni
Ambito:
- Componenti analizzati: telecamere / sensoristica, pipeline dati (acquisizione, memorizzazione, training), modelli AI (addestramento, inference), interfacce operative (dashboard, API), integrazioni con sistemi di controllo urbano.
- Tipologie di minaccia considerate: data poisoning, attacchi adversarial, furto/estrazione di modelli, insider threat, compromissione di supply chain algoritmica, violazioni di riservatezza dei dati sensibili.

Esclusioni:
- Non sono previste implementazioni tecniche o codifica di contromisure.
- Non si svolgeranno penetration test tecnici o exploit attivi (solo analisi teorica e simulazioni a livello di scenario).
- Non si forniranno istruzioni operative per attacchi.

## Catalogo dei rischi e vulnerabilità da considerare
- Data poisoning: inserimento deliberato di dati malevoli nel set di training che altera il comportamento del modello.
- Attacchi adversarial alla fase di inference: input manipolati per indurre errori di classificazione.
- Furto di modelli / model extraction: esfiltrazione dei pesi o replica del modello tramite accessi non autorizzati o query.
- Esfiltrazione di dati personali e immagini riconducibili a individui (violazione della riservatezza).
- Compromissione della pipeline di labeling (errore sistematico o manipolazione dei label).
- Insider threat: accessi o modifiche non autorizzate da personale interno.
- Dipendenza da terze parti e supply chain risk (fornitori di modelli pre-trained, servizi cloud).
- Denial of Service su componenti critici di inference o raccolta dati (impatti su disponibilità).
- Errata correlazione e inferenze discriminatorie (rischio legale e reputazionale).
- Incompletezza o mancata tracciabilità delle decisioni (mancanza di auditability).

Per ciascun rischio va stimata la probabilità (bassa/medio/alta) e l’impatto (basso/medio/alto) in un registro dei rischi.

## Contromisure ad alto livello secondo la triade CIA
Nota: le contromisure sono descritte a livello organizzativo e di governance, non come istruzioni tecniche.

Confidentiality (Riservatezza)
- Politiche di classificazione dei dati e regole di minimizzazione per immagini e metadati.
- Limitazione degli accessi privilegiati e principi di least privilege su persone e terze parti.
- Processi contrattuali e di due diligence per fornitori che trattano dati o modelli.
- Procedure di anonimizzazione e pseudonimizzazione dei dataset quando applicabile.

Integrity (Integrità)
- Governance del ciclo di vita del dato e dei modelli (linee guida per raccolta, labeling e gestione delle versioni).
- Processi di validazione e revisione periodica dei dataset e dei modelli (audit e tracciamento delle modifiche).
- Controlli organizzativi per gestire rischi di manipolazione dati e vulnerabilità nell’addestramento.
- Definizione di criteri per la verifica dell’evoluzione dei modelli prima del rilascio in produzione.

Availability (Disponibilità)
- Piani di continuità operativa e procedure di fallback per perdita temporanea del servizio di inference.
- Definizione di SLA e strategie organizzative per il mantenimento del servizio (ridondanza applicativa a livello contrattuale, accordi con fornitori).
- Procedure per la gestione degli incidenti che minimizzino l’interruzione dei servizi critici alla sicurezza stradale.

## Analisi di conformità normativa 
Per ciascuna normativa indicare aree da valutare, non prescrivere implementazioni:

GDPR
- Valutare basi giuridiche per il trattamento delle immagini e dei dati personali (es. legittimo interesse, consenso, gestioni per sicurezza pubblica).
- Verificare obblighi di minimizzazione, limitazione della finalità, storage limitation, diritti degli interessati (accesso, cancellazione, opposizione).
- Valutare DPIA (Data Protection Impact Assessment) per i trattamenti ad alto rischio (sistemi di sorveglianza e profiling).
- Controllare responsabilità condivise e contrattualistica con fornitori (data processors).

AI Act (regolamentazione UE sulle AI)
- Classificazione del sistema secondo il rischio previsto dall’AI Act (es. high-risk se applicabile a infrastrutture critiche o sicurezza pubblica).
- Valutare requisiti di governance e documentazione tecnica, valutazioni di rischio pre-mercato e misure di mitigazione richieste dal Regolamento.
- Identificare obblighi di trasparenza e informazioni da fornire agli utenti finali e alle autorità.

NIS2 (direttiva sulla sicurezza delle reti e dei sistemi informativi)
- Verificare se UrbanSight rientra tra gli operatori o fornitori di servizi essenziali/critici soggetti a NIS2.
- Valutare obblighi di gestione del rischio, incident reporting e misure di resilienza operativa.
- Analizzare requisiti di cooperazione con le autorità nazionali e di notificazione degli incidenti.

Per ciascuna normativa si produrrà una check-list di conformità e un gap analysis ad alto livello.

## Deliverable
- Documento principale: executive summary, mappatura ecosistema, analisi rischi, contromisure ad alto livello, compliance gap analysis, raccomandazioni organizzative.
- Registro dei rischi (allegato nel documento): elenco rischi, probabilità, impatto, priorità.
- Checklist di conformità per GDPR, AI Act, NIS2 (tabella riassuntiva ad alto livello).
- Incident report simulato (sezione dedicata).
- Roadmap di massima per attività successive di approfondimento (es. DPIA, audit tecnici).
- File: link Google Docs con permessi di consultazione/commento (secondo indicazioni del docente).


## Criteri di valutazione 
- Completezza della mappatura dell’ecosistema e dei flussi dati.
- Copertura e qualità del catalogo rischi (rilevanza e prioritarizzazione).
- Adeguatezza e coerenza delle contromisure proposte a livello organizzativo/CIA.
- Qualità della gap analysis normativa (GDPR, AI Act, NIS2) e chiarezza dei punti di non conformità.
- Completezza e realismo del report d’incidente simulato (timeline, impatti, stakeholder, azioni immediate e comunicazioni).
- Chiarezza dell’esposizione, struttura del documento e qualità dell’executive summary.


## Valore aggiunto e benefici attesi
- Maggiore capacità di prevenzione e gestione degli eventi che possono compromettere sicurezza e privacy.
- Migliore posizionamento contrattuale e gestione del rischio verso enti pubblici.
- Strumenti decisionali per pianificare investimenti in controlli, formazione e audit.
- Documentazione utile per future richieste di conformità e gare d’appalto.

## Allegati consigliati per la consegna
- Template registro rischi (tabella con rischio, descrizione, probabilità, impatto, priorità).
- Template checklist GDPR / AI Act / NIS2 (item per item ad alto livello).
- Modello di incident report standardizzato da riempire in caso di eventi reali.
- Executive summary pronto per stakeholder non tecnici.
