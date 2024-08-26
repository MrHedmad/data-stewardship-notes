---
topic: Informatica Moderna
date: 2024-04-11
tags:
  - cuap_data_steward
  - lecture_note
aliases: []
---
> Speaker: Alessia Antelmi - Dipartimento di Informatica - UniTO

Spesso è di altissima importanza comunicare i risultati, i dati, sottoforma di narrativa che riesca a comunicare il messaggio chiaramente, comunicare la conoscenza che è scaturita dai dati, e, eventualmente, di convincere chi ci ascolta.

Una buona presentazione è coerente, collegata e (il più possibile) interattiva.
Per creare una buona presentazoine è opportuno creare un singolo punto di accesso a tutte le rappresentazioni dei dati, con un "cruscotto informativo", che collega tutti i vari grafici e informazioni che servono per informare.

Oversemplicare il problema complesso è quasi sempre una brutta idea: se il problema - i dati - sono complessi, è opportuno far trasparire questa complessità.
In breve, è una cosa buona e giusta tenere le visualizzazioni semplici, ma attenzione a non far diventare la narrativa troppo sempliciotta o stupida.

La visualizzazione interattiva cattura i vari livelli di complessità o di granularità dei dati (ad esempio una mappa, in cui si può letteralmente zoommare per ottenere più dettagli per un area).

Tutti questi concetti cadono sotto il termine di "Data Storytelling". Il concetto è che, attraverso rappresentazioni accattivanti, storie connesse ai dati e infografiche belle possono far passare il messaggio meglio e questo è ritenuto di più.
See e.g:
- https://pudding.cool/2020/07/gendered-descriptions/
- https://whydocatsanddogs.com/
- https://rhythm-of-food.net/
- https://news.sky.com/story/better-for-brexit-how-uk-has-changed-since-leave-vote-11920143

## Data Dashboard
Una piattaforma, una rappresentazione, spesso interattiva, con una serie di grafici e visualizzazioni che spesso si possono adattare alla necessità di un utente.
Sono spesso sotto forma di pagine web.

Un esempio di piattaforma per creare queste rappresentazioni è Google Looker Studio, che è parte dell'ecosistema google (e si può connettere a vari altri servizi di Google).

## Basi di dati (o database)
Con "basi di dati" si intende un insieme organizzato e omogeneo di dati utilizzati per il supporto allo svolgimento delle attività di un ente pubblico o privato.
Un altra definizione è "un insieme di dati atomici, strutturati e persistenti, raggruppati in insiemi omogenei in relazione tra loro, organizzati con la minima ridondanza per essere utilizzati da applicazioni diverse in modo sicuro e controllato".

Esempio: ho due dataset, uno con i dati degli orari di lezione, l'altro con quelli degli orari di ricevimento. I dati sono collegati concettualmente (per esempio non devo mettere ricevimento quando ho lezione), ma non lo sono in due dataset separati.

Un altro aspetto, per cui i database sono stati creati, sono l'autorizzazione (io posso modificare, tu puoi vedere, tu non hai accesso) e il controllo della concorrenza (due persone modificano lo stesso file, che modifica prevale? come facciamo tutti a vedere le stessa versione?).

I software che amministrano i database e che ne permettono l'uso sono i Database Management Systems (DBMS).
Un DBMS solitamente ha delle caratteristiche:
- Linguaggi per definire schemi logici dei dati (Data Definition Language, DDL);
- Vincoli di integrità per i dati in input;
- Linguaggi per manipolare i dati (Data Manipulation Language, DML);
- E altri ma ha cambiato la slide

Ad esempio, MySQL è un DBMS, che usa come DML SQL. 

### Relational database
I database relazionali sono i più vecchi. Modellano i dati come tabelle, con delle relazioni (cioè colonne che si possono "fondere") tra tabelle. In queste tabelle ogni colonna è un attributo, e ogni riga è un dato.

Le tabelle sono *relazioni*, ognuno con uno *schema*, e con una serie di *tuple* (righe) che formano l'*istanza* della relazione (la tabella completa attuale).

Possiamo aggiungere vincoli dentro ogni relazione, in modo che le singole tuple rispettino qualche criterio.

```sql
CREATE TABLE acidtest (A INTEGER, B INTEGER, CHECK (A + B = 100));
```

La linea `CHECK` aggiunge uno di questi vincoli. Esistono anche vincoli inter-tabella (per mettere x in questa tabella deve esistere anche in quest'altra, ad esempio), spesso chiamati "vincoli di integrità".

Possiamo agire sulle tabelle con gli operatori. Alcuni operatori strani sono:
- Intersezione, unione o differenza: solo su tabelle con schemi identici.
- Prodotto cartesiano: crea tutte le combo di tutte le tuple di due relazioni
- Join: fa prima il prodotto cartesiano, e poi, su uno o più attributi, la tabella è filtrata tenendo (ad esempio), solo una copia della colonna di join, o solo gli oggetti nel join di una di due tabelle.

#CUAP_data_steward