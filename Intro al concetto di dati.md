---
topic: Strumenti di Rappresentazione
date: 2024-04-04
tags: cuap_data_steward, lecture_note
---
> Speaker: Diego Magro, Dipartimento di Informatica, UniTO

Cosa sono i dati? Ci sono tante definizioni. EOSC Glossary li da come "reinterpretable digital representation of information in a formalized manner suitable for communication, interpretation or processing".

Rappresentazione (anche digitali), simbolica, non interpretata di fenomeni, eventi, fatti o concetti.

Il concetto di "interpretazione" è importante. Il dato in sè è generalmente meaningless, ma in base alla sua interpretazione esso può avere significato.
Questo si può applicare essenzialmente a tutto: queste sono lettere, ma sapendo leggere si interpretano come concetti.

I *meta*dati sono dati relativi a dati. Descrivono caratteristiche dei dati, di qualsiasi tipo:
- Modello dei dati,
- Formato di rappresentazione,
- autori, responsabili,
- data di creazione, modifica,
- processo di creazione,
- vocabolari utilizzati,
- politiche di accesso, licenze,
- tipologia di contenuto.

EOSC la definisce come "Data defining and describing other data".

I metadati sono anche loro *dati*, quindi possono essere a loro volta descritti da altri metadati.
In senso stretto anche il nome delle colonne di una tabella sono metadati.

La relazione dato-metadato può essere vista dal punto di vista ontologico, come essere genitore o figlio.

Un **dataset** è una collezione di dati omogenei. In EOSC è definito come "logically meaningful group of data". Ad esempio una tabella di espressione è un dataset: i dati di campioni simili sono raggruppati assieme.

## FAIR Data
I [[FAIR principles|principi FAIR]] sono delle caratteristiche che i dati dovrebbero avere per diventare "first-class citizens" nel panorama accademico. Sono solo caratteristiche, e non sono prescrittive sul come ottenere queste caratteristiche.
Si può essere più o meno conformi ai principi FAIR, e meglio essere un pò FAIR che non esserlo per nulla.

I principi FAIR sono enfatizzati sul ruolo delle macchine nella ricerca e uso dei dati stessi. Il goal sarebbe di avere software e dati che riescono a utilizzare dati per cui non sono stati originariamente programmati di "comprendere".

I principi FAIR si possono anche applicare ad algoritmi, strumenti, workflow che hanno prodotto o che analizzano dati.

### Findable
Persone e **macchine** dovrebbero poter (facilmente) trovare i dati. Questo vuol dire che i (meta)dati siano ritrovabili in piattaforme pubbliche e standard, in un formato per cui il lettore possa capire che tipo di dati sono e che cosa contengono.

### Accessible
La pathway di come ottenere i dati deve essere ben chiara, e deve essere fruibile con protocolli aperti, gratuiti e universalmente implementabili.
Questo non preclude l'esistenza di dati non pubblicamente accessibili o a pagamento.

Il metadato è l'unico che dovrebbe essere sempre accessibile in perpetuity, anche prima che i dati sono pubblici (ad es. per embargo), e anche dopo che i dati non sono più pubblici (per costi di mantenimento o per distruzione, ad esempio).

### Interoperabile
Qui cade l'asino. Per essere interoperabili, i dati devono poter essere integrati con altri dati e elaborati da applicazioni con il minimo sforzo, anche in ambiti diversi da quello di origine e in circostanze non inizialmente previste.

E' qui che è importante l'uso di modelli, linguaggi e vocabolari (tassonomie, tesauri, ontologie) il più possibile "standard", formalmente definiti e aperti. 
Collegare tra loro i (meta)dati consentirebbe di delinearne il contesto, ne facilita la comprensione e l'interoperabilità, come il "web of data".
Ad esempio, al menzionamento di una posizione geografica, potrei legare la stessa ad un collegamento ad un altro dataset, ad esempio di posizioni.

### Reusable
L'utente che vuole usare il dato deve sapere cosa ci possa fare e come farlo. Questo si traduce in utilizzare licenze appropriate e inoltre utilizzare standard aperti per il formato di file e formattati seguendo standard riconosciuti e aperti.

Inoltre l'utente deve poterne valutare la qualità, quindi bisogna definire bene la provenienza dei dati, includendo le persone, i processi, le macchine che li hanno prodotti o che ne hanno contribuito.

Findability e Accessibility possono essere soddisfatti al livello dei metadati. Quelli di interoperability e Reusability sono sia legati al dato vero e proprio che ai metadati.