---
topic: Strumenti di Rappresentazione
date: 2024-04-04
tags: cuap_data_steward, lecture_note
---
> Speaker: Diego Magro, Dipartimento di Informatica, UniTO

Il "modello di dati" è l'insieme di concetti e e relazioni per mezzo dei quali i (meta) dati possono essere organizzati e rappresentati. Ad esempio, il modello "tabellare" unisce vari concetti, come "riga", "colonna", "cella", "titolo", etc... Un altro esempio è la grafica rasterizzata: una griglia di "pixel" ognuno con un "colore".

La concretizzazione dei modelli di dati sono i *formati di codifica*: un modello tabellare può essere concretizzato nel formato *comma delimited value*.
I formati sono una serie di convenzioni per codificare il dato in campo informatico. L'esempio del CSV è un file UTF-8 con una serie di righe... (anche il formato UTF-8 è un altro tipo di codifica).

Uno stesso modello è concretizzabile in vari modi: di un modello tabellare potrei usare un file word, un excel, un csv, persino un immagine JPG (o qualsiasi altro formato)! Ma non tutti i formati sono della stessa qualità.

Un modello può essere tradotto in altri modelli equipollenti. Ad esempio un ontologia OWL può essere rappresentata in RDF, un RDF può essere descritto in XML, l'XML è un file di testo, codificabile in UTF-8, etc...
- ~ Tipo `pandoc`. Questa cosa di "squagliare" e "ricastare" i dati (e i metadati) è molto interessante.

A volte i (meta) dati possono essere inclusi nel file di dati direttamente, detti "embedded metadata". I formati JPG, ad esempio, arrivano con dei metadati direttamente. Le pagine web arrivano spesso con del "markup", dei metadati che descrivono i vari pezzi della pagina. Microdata, RDFa, JSON-LD sono tutti esempi di embedded metadata.
Spesso si usano questi approcci per essere appetibili sia agli umani (che vedono la pagina web) che le macchine (che digeriscono il markup).

- ? Si può iniettare metadato in qualsiasi formato, o serve che il formato sia estendibile con in metadati *ab initio*?

Example, su schema.org ci sono vari esempi di usare i loro schemi nel formato HTML: https://schema.org/Person#eg-0001

Nello stesso modo, si possono avere gli stessi dati in modi diversi, ad esempio uno per gli umani e uno per le macchine. Il protocollo HTTP offre il meccanismo di *negoziazione del contenuto* (content negotiation), cioè il client può chiedere al server la stessa risorsa in formati diversi, più adatta per i suoi scopi. Questa varianza può essere sia in termini di modello che di formato, se ne sono possibili più versioni.

- ? Una singola versione "vera" poi deserializzata e riserializzata?
    - Si, ma anche no: il server può fare quel cazzo che vuole per rispondere alle query: sia averli pre-renderizzati (ma poi attenzione se si desincronizzano) o rigenerarli on-the fly.

Addirittura si possono chiedere versioni diverse della stessa cosa in sequenza di preferenze: preferirei CSV, oppure XLXS, oppure XML, oppure qualsiasi altra cosa.

### CSV
E' un formato per il modello tabellare. Ha varie caratteristiche:
- Ogni file ha una singola tabella;
- E' un formato testuale, generalmente in UTF-8
- Ogni riga della tabella è una riga del file;
- Gli elementi di ciascuna riga sono separati da una virgola.

### JSON
Vabbè

### XML
Un formato un pò incasinato con una struttura ad albero annidato. L'ha inventato il W3C (World Wide Web Consortium). 
- Sempre un formato di testo, i "documenti XML";
- E' formato da tag con pattern `<(.*?)>` per quelle di apertura e `<//$1>` per quelle di chiusura
    - Ad esempio `<autori>` e `</autori>`
    - E' identico a HTML, ma la parola chiave dentro il tag è arbitraria - è "extensible".
        - Alcune eccezioni ci sono, per tag che hanno un significato speciale.
- I tag esprimono cosa è dentro ad ogni campo.
- Esistono i tag vuoti, con pattern `<(.*?)//>`, tipo `<autore/>`
    - I tag vuoti non hanno closing tag.
- Dentro ai tag possono esserci degli attributi dopo il nome del tag:
    - `<autore tipo="individuo">Mario Rossi</autore>`

### RDF
Il Resource Description Framework, o RDF, è anche esso una specifica del W3C. L'ultima versione è 1.1, ma si sta lavorando per la prossima. 
E' un modello di dati in cui essi sono rappresentati in triple, le "triple RDF".
- Ogni tripla è anche detta "statements" o "assertions".
- Ogni tripla ha un soggetto, un predicato un oggetto, SPO (Subject, Predicate, Object)
- Ogni tripla significa che il soggetto S ha per il predicato P il valore O.
- Un qualcosa nel mondo è una "Resource":
    - `(Mario Rossi, professione, "Avvocato")`
        - In questo caso, "Mario Rossi" è una Risosorsa, e ha come `professione` il valore di stringa `"Avvocato"`.
    - Specificamente, una risorsa è una [[International Resource Identifier|IRI]] o un literal.
        - Un literal è di un qualche tipo, una stringa, un numero, etc...
- Spesso una tripla è rappresentata come un grafo.
- Gli oggetti possono essere elementi (tipo una stringa) *o altre risorse*.
    - Questo causa la possibilità di creare un vero e proprio grafo, con l'RDF visto come una edgelist.
    - Tecnicamente un "Directed labelled cyclic graph"
    - Per questo spesso il formato RDF è detto "RDF Graph".
- Il fatto che l'RDF sia un grafo non è a caso: si può usare tutta la matematica dei grafi sopra per estrarne informazione

Tecnicamente, un Soggetto è per forza un IRI (o un "blank node", ma i blank node non dovrebbero essere usati). Il predicato è per forza un IRI. L'oggetto può essere un IRI, un letterale o un "blank node".
Usiamo IRI ma riferito all'universo di un singolo file, quindi in poche parole devono essere unici dentro il singolo documento RDF.
I predicati sono sempre binari: è una relazione tra soggetto e oggetto. 
I predicati sono potenziali oggetti, quindi possono essere descritti dentro all'RDF in sè, anche se spesso si tende a dividere i due livelli "ideologici" di ontologia e dato.

Possiamo portare all'estremo la definizione di IRI riutilizzando gli identificatori già specificati, ad esempio quelli di *wikidata*, che contiene un sacco di definizioni sia di "canonici" oggetti (e.g. "Mario Rossi"), di "canonici" predicati ("coniuge di", "morto a"), e di "canonici" soggetti (e.g. "Torino").

I dataset RDF possono contenere più grafi RDF separati.
Si possono memorizzare i dataset RDF in database. In teoria si possono usare database relazionali tradizionali (un unico tabellone SQL, con tre colonne), ma esistono anche i cosiddetti *triplestore*, dei Database management systems appositamente fatti per memorizzare RDF. Possono essere sia nativi, cioè veramente fatti apposta, oppure su una "fondazione" di database relazionale, con uno strato software sopra.
I grafi RDF sono anche direttamente salvati in file.

I triplestore possono essere interrogati con un query language specifico: SPARQL (SPARQL Protocol and RDF Query Language). E' uno standard anche questo di W3C, e definisce protocollo di accesso, linguaggio di manipolazione e di interrogazione. 
Uno SPARQL endpoint è un servizio web che può interpretare richieste SPARQL su un protocollo SPARQL.

Ci sono i namespace anche qui, nell'header posso dire che `wd:...` è uguale a `https://wikidata/term/...`, ad esempio.

Ci sono varie possibilità di serializzazione di RDF, in tanti tipologie di file diversi, sia specifici (e.g. Turtle), ma anche JSON-LD (per "linked Data"), RDF/XML, RDFa (un modo di ficcare dati RDF in pagine HTML o XML, ma tenendo l'HTML/XML valido), etc...

- ! Spesso gli IRI usati negli RDF possono essere risolti sia per gli umani che per le macchine, con quel meccanismo di "content negotiation".

- ~ GraphDB è uno di questi?

- ~ F-UJI - Automated FAIR data Assessment Tool
    - E' molto superficiale.


Per "esame": cerca e descrivi o un ontologia specifica oppure usare FUJI o simili per determinare quanto FAIR sono i dataset in giro.