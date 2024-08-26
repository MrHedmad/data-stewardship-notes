---
topic: Strumenti di Rappresentazione
date: 2024-04-04
tags: cuap_data_steward, lecture_note
---
> Speaker: Diego Magro, Dipartimento di Informatica, UniTO

## Identificatori
Il principio F1 recita "(Meta)data are assigned a globally unique and persistent identifier" e possiamo aggiungere anche "risolvibile". 
Un identificatore è un certo oggetto (un numero, una stringa, etc..) che identifica un altra cosa. Se è globalmente unico significa che esso indica solo e unicamente un singolo oggetto nello spazio e tempo. Questo "oggetto" può essere dei metadati, dati, vocabolari o altre entità o parti di essi, virtualmente qualsiasi cosa che abbia senso essere identificato.

Essere "globalmente unico" dipende da cosa è il "globo". Il numero di riga di ogni file di testo è un ID unico a quella riga *se consideriamo solo un documento*. Solitamente i veri identificatori "globalmente unici" sono quelli un cui il globo è proprio tutto il mondo (anche nel tempo). Un identificatore non univoco non è molto utile, e quindi solitamente nella definizione di identificatore ci casca già essere unici (ad un qualche livello).

L'autorità che assegna gli identificatore può essere diretta, in cui l'organizzazione in sè produce gli identificatori, o delegata, dove lo spazio identificativo globale è suddiviso in più sottospazi delegati ad altre entità, che possono dare identificativi o dividere i loro domini in ulteriori sottospazi e così via.

La *persistenza* di un identificatore è generalmente soggettiva. Dipende dal supporto che l'entità che emette l'identificatore da agli identificatori che crea. Ad esempio, potremmo dire che se l'identificatore rimane valido per almeno 50 anni è "persistente".
Per essere persistente sia l'identificare che l'oggetto che identifica devono essere preservati, immutati, nel tempo predisposto.

Ad esempio, un URL di una pagina web è effimero: non ci sono garanzie che un URL valido adesso sia valido allo stesso modo domani, o tra dieci anni. 

Gli identificatori persistenti sono detti PID (Persistent Identifiers).

Per creare un PID si può o creare un organizzazione che si impegna di mantenere gli identificatori persistenti, oppure ci si avvale di terzi che lo fanno per noi.
Ci sono un sacco di servizi che producono PID per noi, uno ad esempio è DOI, ma anche w3ID, OrcID, ARK, etc...

Per essere *risolvibili* gli identificatori possono essere de-referenziati automaticamente (o meglio, attraverso protocolli standard) in base al quale dato in input l'identificatore abbiamo in output la risorsa a cui l'identificatore indica, o anche solo parzialmente informazioni al riguardo.
Un esempio sono gli URL web.

Per essere risolvibile serve un'infrastruttura attorno all'identificatore che lo rende risolvibile, come ad esempio HTTP e l'hardware di internet.

In cosa risolve l'identificatore? Dipende. Per gli URL Https, ad esempio:
- La risorsa stessa (il file stesso);
- I metadati della risorsa, spesso con altri identificatori per la risorsa stessa.
Ad esempio, se avessi un identificatore "AAA-CCC" potrebbe risolvere in un *altro* identificatore (come un redirect), che risolve alla risorsa in se. "AAA-CCC" non da la risorsa in se, ma informazioni al riguardo.

Nota che [[Internet Resource Locators]], [[Internet Resource Locators]], [[Internet Resource Locators]] e [[Internet Resource Locators]] sono leggermente diversi.

Gli IRI Http(s) possono variare nel tempo, dato che le pagine web possono spostarsi. Ci sono dei servizi, come w3ID, che rimappano degli URL vecchi alle loro versioni nuove. L'url dato da w3ID è sempre quello, ma può essere configurato per ridirezionare chi lo segue alla vera pagina.

- ? What about layered vocabularies?
- ? What about including the vocabulary with the metadata itself?
- ? How much metadata is too much metadata?
- ? Composable metadata vocabularies?

W3ID è un organizzazione che mantiene una repository di redirect, con cui si possono coniare degli IRI persistenti che ridirigono a IRI effimeri.

Gli IRI https non sono gli unici, ma sono molto spesso utilizzati.

- ? Versione dell'oggetto nell'IRI?
    - Si, ci piace, ma anche il metadato dovrebbe avere la storia di tutte le versioni vecchie dello stesso oggetto. Sapendo l'IRI dell'ultima versione si riesce quindi a tornare a tutte le versioni vecchie.

Con degli identificatori si riesce a ridurre l'ambiguità delle risorse, anche riducendo la duplicazione del dato stesso.
Se esistono già identificatori globali che descrivono le stesse cose di un nuovo ID locale che mi serve (cosa che dovrebbe essere evitata), è cosa buona e giusta creare tabelle di mapping tra gli identificatori locali gli stessi identificatori globali.

## Creare i propri identificatori
Usare degli identificatori globali da terzi è quasi sempre meglio, ma se è necessario creare identificatori locali è consigliabile seguire qualche indicazione operativa:
- Creare nuovi identificatori per *nuovi* contenuti, usare gli ID vecchi per contenuti già esistenti, possibilmente nativi (cioè originali e da fonti autorevoli).
    - Questo riduce la duplicazione degli ID e rende tutto il sistema meno complicato possibile.
- Prediligere IRI Http(s) e conformarsi il più possibile a qualche standard, anche se solo inventato localmente.
    - Se chiamo AAA-Mese per il concetto di "mese", usare AAA-week per il concetto di "giorno" non è intuitivo, sarebbe da evitare.
- Per IRI https, specificare anche il prefisso per cui gli IRI possono essere rappresentati in maniera compatta (come i Compact URI, CURIE)
    - E.g. se definico `hero` uguale a `https://w3id/hero/`, allora `hero:HERO-TIME#month` è uguale a `https://w3id/hero/HERO-TIME#month`.
- Evitare di inserire nei propri identificatori informazioni che possono cambiare o soggetti a scadenza, come estensioni di file ("catalogo" al posto di "catalogo_html"), riferimenti a tecnologia ("catalogo.php"), parametri ("lang=it"), categorie ("resource" e non "student" o "teacher", dato che uno studente oggi potrebbe essere un teacher domani), etc...
- Evitare di inserire negli identificatori elementi di significato: la descrizione dell'entità deve avvenire attraverso metadati specifici, non attraverso l'identificatore.
    - In generale le ultime due sono riassumibili in "non includere informazioni effimere negli ID".
    - Questo vuol dire prediligere IRI "opachi", che non veicolano significato.
- Creare IRI machine-readable, quindi senza spazi, punteggiatura, caratteri speciali (?!=\\/...)
- Creare IRI generalmente poco confutabili, quindi non fare affidamento a differenze tra minuscole e maiuscole, mix di 0 e O, etc...
- Scegliere uno schema di rappresentazione e attenersene.
- Evitare di usare unicamente cifre per codificare l'ID, per non confonderne in un numero generico.
- Documentare i cambiamenti dell'entità o nel ID o nel metadato che l'ID sta indicando, ad esempio `some_id0123.1` e `some_id0123.2` per due versioni di `some?id0123` (che risolve sempre all'ultima versione).
    - L'identificatore generico dovrebbe essere subito reperibile da quello specifico (nell'esempio di prima basta togliere il punto finale)
- Se il target dell'ID sparisce, rimpiazzarlo con una "tombstone" che dice che non c'è più, senza fare fallire l'ID
- Non riassegnare mai ID già utilizzati a cose nuove, anche se le cose vecchie sono obsolete, cancellate, etc...
- Usare schemi chiari e semplici (obviousness)

> Ci sono letture sulle slide

- ~ Protegè - software per scrivere vocabolari e ontologie, scritte nel formato OWL (Web Onthology Language)

- ?  Esistono servizi per coniare identificatori univoci "locali"? Oltre ad UUID.
    - W3id riesce ad essere intelligente con gli URL, e ne mappa pattern in altre pattern. 
    - Anche modificare la sezione locale del w3id è attraverso pull request al loro github