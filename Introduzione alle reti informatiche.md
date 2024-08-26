---
topic: Informatica Moderna
date: 2024-03-22
tags: cuap_data_steward, lecture_note
---
> Speaker: Alessia Antelmi - Dipartimento di Informatica - UniTO

Una rete è una serie di macchine, o nodi, che comunicano tra di loro.
Possiamo saggiare le prestazioni di una rete con tre criteri: prestazioni, affidabilità, ...
- Prestazioni
	- Ritardo - tempo che un messaggio ci mette ad arrivare a destinazione
	- Tempo di risposta - ping
	- Throughput: quanti dati possono essere invitati
	- Influenzate da varie cose:
		- Numero di nodi,
		- Hardware usato (e.g. cavo, velocità macchine...)
	- Solitamente throughput e delay sono inversamente proporzionali: più dati sono spediti, più tempo ci si mette.
- Affidabilità
	- La combinazione di quanto è facile che la rete si rompa per quanto è facile ripararla.
- Sicurezza
	- I messaggi inviati tra diversi nodi dovrebbero essere leggibili solo dai due nodi che inviano e ultimamente ricevono il messaggio.

Una [[LAN]], o Local Area Network, è una rete limitata spazialmente. Una [[WAN]], un Wide Area Network, è invece una rete molto estesa nello spazio, con molti nodi, che solitamente incolla assieme varie LAN.
I protocolli tra LAN e WAN sono diversi, come anche l'hardware tra i due.
Ad esempio, varie LAN di una azienda possono essere connesse tra di loro con una WAN.

Una internet è una inter rete, una rete che connette altre reti. Internet è LA internet globale. Internet è una architettura decentralizzata: i protocolli di comunicazione per accederci sono standard e pubblici.
Non è proprio globale: ad esempio cina e Nord Korea hanno le proprie internet, più o meno da Internet.

Dal punto di vista di un utente, il web è una collezione di *risorse*, solitamente ipertesto: vedi HTTP. I web browser sono programmi che possono richiedere ed interpretare gli ipertesti da Internet.

I protocolli di internet sono nati al CERN di Ginevra, dato il bisogno di mandarsi i dati e le informazioni dentro i loro centri.

Ogni risorsa è univocamente identificata dagli [[Internet Resource Locators|Universal Resource Locator]]. Sono più o meno maschere dei veri indirizzi IP.

Un URL ha questa forma:
```
https://www.alpha.beta.gamma.it/some_page
https - protocollo
            alpha - Nome del sito
                  beta.gamma.it - dominio di terzo.secondo.primo livello
			                   /some_page -- path nel FS locale
```

L'architettura più semplice è la comunicazione di un client e di un server. Un server è un programma che può ricevere richieste dall'esterno e rispondere adeguatamente.
Un server (o meglio un architettura server) può essere monolitico, con un solo programma (e macchina) a cui è affidata tutta la logica, oppure distribuito (a microservizi).

Con il termine *cloud* ci riferiamo di solito a gruppi di server anche distribuiti nello spazio che sono altamente integrate tra di loro e offrono solitamente una serie di servizi in modo concertato, in genere:
- Software as a service (SaaS)
	- Io pago per un software che è fornito da una cloud (e.g. Google Drive, Office 365)
- Platform as a service (PaaS)
	- Io scrivo il software, ma la cloud si preoccupa di eseguirla scalarla globalmente se c'è il bisogno e mantenerla sicura.
- Infrastructure as a service (IaaS)
	- Pago per l'uso dell'hardware, ma sono cazzi miei su cosa ci installo e come la mantengo (e.g. aggiornamento OS, software...)

I cloud si prestano bene ai microservizi. Piccoli container possono lavorare più separati tra di loro, comunicando solo le informazioni.
Per enormi software, ogni microservizio può essere scalato attivando più microservizi del suo stesso tipo, mantenendo gli altri invariati. Questo può essere fatto in modo reattivo al bisogno. Magico.

## Sicurezza Informatica
Ci sono tre "pilastri" della sicurezza informatica:
- Riservatezza: la capacità di escludere persone che non devono accedere all'informazione
- Integrità: mantenere le informazioni inalterate se non espressamente modificate da utenti autorizzati
- Disponibilità: le informazioni sono sempre disponibili

La crittografia è la disciplina che studia come cifrare un informazione e trasmetterla ad altri attraverso un canale non sicuro, cioè che il messaggio può essere intercettato da terzi che non sono il diretto destinatario.

Un algoritmo di cifratura è un algoritmo che prende un messaggio e lo modifica per renderlo non leggibile se non da chi ha l'algoritmo di de-cifratura associato.
Un esempio è il **cifrario di Cesare**, che usava una chiave segreta per criptare i messaggi: solo con la stessa chiave si può decodificare il messaggio.
Un altro esempio è la macchina enigma utilizzata dalla Germania Nazista.

Il problema della chiave privata è che *anche essa deve essere inviata al destinatario*, quindi stiamo solo spostando il problema a come cifrare la chiave di cifratura. Questo è perchè sono algoritmi *simmetrici*, la stessa chiava e usata sia da me che da te.
Solitamente generiamo le chiavi con algoritmi come RSA e SHA.

Si risolve tutto con gli algoritmi a chiave segreta e pubblica, anche detti *asimmetrici*.
La chiave pubblica può essere data liberamente, perchè solo utilizzabile per *criptare* i messaggi. La corrispondente chiave segreta è invece utilizzabile per decriptare i messaggi.

Quindi: mi scambio le chiavi pubbliche con il canale non sicuro, e le uso per criptare i messaggi. Solo il mittente ha la chiave privata, quindi può leggere il messaggio.

La firma digitale funziona così: il file assieme alla chiave privata è criptato (si fa un hash del file, che è poi criptato dalla chiave) e allegato al file originale. Chiunque può usare la chiave pubblica per decifrare la firma, e ottenere l'hash del file. Comparando gli hash del file che ho ricevuto con la firma decriptata posso sapere se il file è l'originale.

## Cyberattacchi
Ci sono tre tipi di cyberattacchi:
- Accesso o perdita di dati sensibili o personali
- Modifica dei dati
- Distruzione dei dati

### Ransomware
Programmi che bloccano il PC chiedendo un riscatto (ergo il nome).
Se affetti da un ransomware, non si può fare tanto: scollegare il PC dalla rete e riformattare il dispositivo.
Se succede a dispositivi aziendali o universitari, notificare l'ufficio IT del garante della privacy.

Si diffondono come al solito con email di spam o phishing.

### Phishing
Se siamo vittime di un attacco phishing, bisogna cambiare password potenzialmente affette e sporgere denuncia per furto di identità.

Attenzione ai social: phishing può essere anche ritagliato sulla persona guardando i vostri social.

Cosa sono le VPN

## Estrarre conoscenza dai dati
I dati possono essere pensati in diversi "tier":
- Il dato grezzo è la misurazione, il primario record.
	- Foto, descrizioni, video, numeri
- L'informazione è un dato messo in un contesto, una collezione di dati.
	- Una visualizzazione dei prezzi di hotel al centro di Parigi è un informazione.
- La conoscenza è la rappresentazione astratta di una o più informazioni prese assieme, filtrata e modulata dalla conoscenza personale di chi assorbe le informazioni.

*Datum* significa ciò che è fornito, la base per il calcolo. La parola grafico deriva da "scrivere": la rappresentazione "scritta" dei dati.

Uno dei più vecchi esempi di acquisizione e uso dei dati è quello dell'epidemia di colera del 1854 a Soho a Londra. John Snow, medico, cercò di capire la causa.

Essenzialmente il video di map men

John ha essenzialmente estratto dai dati grezzi (dove si sono ammalate le persone) informazione, contestualizzando, utilizzando gli outlier in modo intelligente (le persone che non si sono ammalate in birreria, la zia ammalata molto lontano dalla fonte, etc...). Nei suoi documenti dettaglia accuratamente anche le variabili confondenti e i possibili errori commessi.

Carta di Minard sull'avanzata di Napoleone in Russia: in una sola cartina abbiamo posizione, numero di soldati, spostamenti datati, morti, temperatura, etc...

Attenzione che correlazione non è necessariamente sintomo di causalità: l'esempio di Snow aiuta. La birreria, ad esempio, è stata la proverbiale eccezione che conferma la regola.

## Open data
Cosa sono gli open data? Ne abbiamo parlato un pochino ieri, ma possiamo dare una definizione:
> Dati che possono essere liberamente utilizzati, riutilizzati e ridistribuiti da chiunque, soggetti eventualmente alla necessità di citarne la fonte e di ricondividere con la stessa licenza.
> - Open Knowledge Foundation

La presenza di una licenza è essenziale: l'assenza di licenze implica i "all rights reserved". Le cose possono essere pubbliche ma non aperte.

L'apertura può essere sia *legale* che *tecnica*. L'apertura legale è il fatto di essere con una licenza aperta, avere i permessi, eccetera. L'apertura tecnica è riferita al formato: la codifica del file deve essere aperta e gratuita (essere "machine-readable").

Gli open data sono principalmente prodotti dal governo per il beneficio della collettività, ma in generale qualunque entità li può creare.

Esempi:
- Mappa delle toilette a Copenhagen, basata su dati aperti;
- Utilizzo delle tasse, visualizzazione basata su dati aperti governativi;
- Tempo di percorrenza di 1 ora dal centro di londra, con dati pubblici di tempistiche del public transport;
- La "mappina" (che in dialatto è anche "cencio"), che mappa murales, negozi, manifestazioni;
- FixMyStreet, dal comune di Manchester, dove i cittadini possono caricare i problemi che notano per strada. Questo è un esempio di citizen data, o citizen science.

Anche le regioni italiane hanno dei portali di open data. Ci sono anche portali nazionali, ad esempio l'ISTAT (ma che pubblica quasi solo PDF o report più o meno pre digeriti...), o data.gov.it.

La *qualità* degli open data però è un noto problema, soprattutto quando le operazioni devono essere automatizzate. Esempio di sin:
- Uso di abbreviazioni (S.MARIA.C.V. per Santa Maria Capo Verde);
- Typo
- Uso inconsistente di nomi (Casalnuovo vs Casalnuovo di Napoli)
- Formati errati (esempio DD-MM-YY vs MM-DD-YY)
- Duplicazioni
- Dati incompleti (con codifice diverse delle incompletezze)
- Diverse formattazioni di numeri (1.2m per 1.2 milioni assieme a 800000)

### Visualizzare i dati
Bisogna sempre pensare a chi parliamo (non parliamo ugualmente ad adulti e bambini, ad esempio), a cosa (quanto in depth?) e a come (come ci si comporta quando si comunica? In che formato?)

Se possiamo NON visualizzare, solitamente è meglio (un grafico per solo due numeri, ad esempio). Ad esempio, si possono usare pop up o infografiche puramente testuali al posto di semplicissimi grafici.
Le tabelle sono utili, ma attenzione ad information overload. Un esempio di grafico/tabella sono le heatmap: aiutiamo il lettore a leggere la tabella con il colore.

Il grafico visuale può fornire molte più informazioni in modo molto più rapido rispetto al semplice testo.

> Inserisci super carrellata di grafici diversi:
> - A barre, per dati numerici aggregati in categorie.
> - Istogrammi, per mostrare distribuzioni di variabili *continue*.
> - Grafico a linee, per i trend di una variabile rispetto ad un altra, spesso il tempo.
> - Scatterplot, per mettere in relazione due variabili, anche per vedere se c'è correlazione tra due variabili.
> - Grafico geografico.
> - Organigramma.
> - Grafici ad albero, per dati di tante categorie e sottocategorie.
> - Grafici a radar (o spider), super amazing se sono interattivi. Utili per variabili temporali.
> - Boxplot
> - Grafici brutti da non usare: a torta, in 3D, donut


#CUAP_data_steward