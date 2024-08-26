---
topic: Strumenti di Rappresentazione
date: 2024-04-24
tags: cuap_data_steward, lecture_note
---
> Speaker: Diego Magro, Dipartimento di Informatica, UniTO

Vari dei punti dei principi FAIR implicano o comunque sono risolvibili con l'uso di vocabolari e ontologie.

Immaginiamo di avere un dataset, con una serie di metadati. Se rappresentiamo i metadati come testo, dobbiamo per forza usare dei termini.
In questo contesto entrano in gioco vocabolari e ontologie:
- Con "vocabolario" intendiamo un insieme condiviso ma poco formalizzato di termini;
- Con "ontologia" intendiamo un insieme condiviso di termini per i quali è formalmente specificata la semantica, spesso attraverso teorie logiche;
Non c'è una distinzione netta tra i due, ma c'è uno spettro tra i vocabolari non formalizzati e le ontologie assiomatizzate.
Un ontologia è *esplicita* (vanno formalizzati tutti i termini, anche banali), *formale* e *condivisa*.

Un esempio di questo continuum:
- Gruppo di parole;
- Gruppo di parole con definizione in linguaggio naturale (un comune vocabolario);
- Gruppo di parole con definizione in linguaggio naturale e insieme di relazioni tra di esse (sinonimia, antonimia, versione più specifica di, più generale di, etc...), questi sono i cosiddetti "tesauri"

I vocaboli che usiamo per descrivere i metadati sono l'ontologia che ci serve per essere FAIR.
Quando usiamo ontologie di (meta)dati aumentiamo la Findability (grazie alle macchine che cercano i dataset in giro) e Interoperability (possiamo leggere i metadati) e Reusability (per lo stesso motivo).

Come scegliamo i termini da usare?
- Per le cose che sono denotate, e.g. "Torino", riusare denominatori già presenti;
    - Se non esistono, crearne di nuovi;
- Esprimere queste relazioni adottando degli standard, se ce ne sono
    - Esempio, le date in formato ISO `YYYY-MM-DD`
- Per le cose che denotano, e.g. "Luogo di nascita":
    - Usare vocabolari già esistenti, o parti di essi
    - Creare nuovi vocabolari e salvarli come FAIR data, se non ne esistono già (di soddisfacenti).

I metadati in RDF possono essere aumentati a piacere: ad. es. se `dcterms:creator` non è abbastanza per me, posso aggiungere `foaf:affiliation` di un certo `dcterms:creator` con una nuova tripla, ad es:
```
this dataset - dctermis:creator - some_orcid
some_orcid - foaf:affiliation - the_university_of_turin
```

- ? Come si sommano gli RDF una volta "risolti"?
    - Spesso gli IRI che si risolvono vanno ad un endpoint SPARQL, che spesso è programmato per ritornare tutte le triple con un certo IRI come soggetto. Quindi possono spesso appiccicare direttamente le triple che ricevo quando risolvo un IRI dentro il mio RDF e ne ho più informazioni.

Non esiste un unico vocabolario per i (meta)dati:
    - Ogni dominio applicativo ha dei suoi vocabolari
    - In uno stesso ambito possono esserci esigenze leggermente diverse
    - E' difficile dare uno standard globalmente condiviso in ogni ambito specifico, ed è difficile anche solo in un contesto generale
    - La tentazione di fare un proprio vocabolario è fortissima, ma spesso ripete (parzialmente) vocabolari e ontologie già in uso, con conseguente aumento di frammentazione.

Spesso nella frammentazione ci sono possibilità di tradurre termini da uno all'altra definizione, quindi possiamo "appiccicare" il mapping dentro agli RDF e poi normalizzare il tutto successivamente.

## Esempi di vocabolari
- CIDOC
    - Una ontologia per l'interscambio di dati in ambito "beni culturali".
- RDF
    - Lo schema di W3 per tutti i grafi RDF, che specifica una serie di relazioni di base tipo "questo è di questo tipo". E' usata in praticamente tutti gli schemi RDF.

## Esempio - creare un vocabolario

Partiamo da una lista di termini con associata definizione in linguaggio naturale. Possiamo partire da una lista di concetti (oggetti) e di relazioni, con le associate descrizioni. Già così è un punto di partenza, ma ha una serie di drawback, ~vedi slide.

Ora possiamo tradurre tutte le parole del vocabolario nelle associati IRI. Spesso risolvere questi IRI risolve in tutto il vocabolario (se non è gigantesco) o nella landing page del vocabolario.

Possiamo progressivamente aggiungere complessità:
    - Alcuni termini denotano *classi* o *tipi*;
    - Le classi possono avere relazioni tra di loro, un esempio detto in cinquanta modi diversi:
        - A è sovraclasse di B
        - B è sottoclasse di B
        - L'insieme di A è sovrainsieme di B
        - Tutti i B sono A
            - Il concetto di B sussume al concetto di A
        - Se X appartiene a B, allora X appartiene ad A
- La prima tassonomia che posso fare è la tassonomia delle cose
    - Definiamo una "cosa" generica e poi iniziamo a specificare
    - Un "libro" è una "pubblicazione_scientifica", ad esempio
- La seconda tassonomia che possiamo fare è delle proprietà, delle relazioni:
    - Possiamo trovare object properties, che legano assieme i "soggetti", mentre le data properties legano gli oggetti e i tipi di base 
        - Se una cosa ha "autore_principale", allora è anche "autore" della stessa cosa.
    - Anche qui possiamo creare gerarchie tra le relazioni, e abbiamo bisogno di una "radice delle gerarchie" che mi dice che queste sono proprietà.
    - Una data property possiamo avere un termine di "vocabolario controllato", che ammette solo un gruppo di possibili valori
        - Ad esempio, "Argomento" può prendere solo uno di 10 possibili argomenti...
        - Si può esprimere in OWL e RDFs (un tipo di RDF)

Possiamo formalizzare ancora di più definendo il dominio e il codominio delle "funzioni" che sono le relazioni:
- Il "dominio" della relazione è l'insieme di oggetti che possono avere una certa relazione:
    - Se X ha "ucciso" Y, allora per forza "X" è parte della categoria "coloro che uccidono". "coloro che uccidono" e' il dominio di "ucciso".
    - Se X ha "allattato" Y, allora "X" è necessariamente parte della categoria "mammiferi". "mammiferi" e' il dominio di "allattato"
- Il "codominio" è la restrizione che una certa relazione dà a cosa è affetto da essa:
    - Se X ha "fatto nascere" Y, allora Y per forza è nel gruppo "cose che possono nascere"
    - Se X ha "ucciso" Y, allora Y per forza è "mortale".

Possiamo definire tutte queste cose con formalismo di assiomi in una teoria logica, ad esempio $(\forall X)(B(x) \rightarrow A(x))$ per dire "Tutti gli elementi di B sono anche elementi di A".
Questi assiomi possono porre limitazioni, vincoli sui termini:
- $(\forall x)(vocab:pubblicazioneScientifica(x)) \rightarrow (\exists Y)(vocab:haTitolo(x,y))$
    - Ogni pubblicazione ha almeno un titolo.
- ~ Vedi altri esempi nelle slide.

Tutte queste relazioni sono esprimibili in formato OWL.

Ogni assioma cerca di esplicitare la semantica dei termini. Questo implica ed è scaturito dal fatto che ci sono dei vincoli se si vuole usare dei termini in un modo sensato.

- ! Il check di coerenza degli assiomi (che un certo dato rispetti una serie di assiomi) è computazionalmente molto complessa
- ! Sono molto più comuni vocabolari non assiomatizzati che ontologie fortemente assiomatizzate.

Ogni assioma cerca di far aderire lo spazio delle possibilità di un concetto al concetto vero.

DBpedia -> versione DB di wikipedia

## "Functional Properties"
- That something is an functional property means that a given individual can have at most one value for it.

---
Day 2 - 2024-04-24

https://lov.linkeddata.es/dataset/lov/ è un esempio di una serie di ontologie più o meno usate, anche se non è 100% aggiornato o accurato.

In the "OWL" you can find "Individuals", which are proper class instances.
"Datatypes" are the various types that Data Properties can take.

The "Annotation Properties" are those properties made for the humans, to describe in a natural language the various entities in the ontology.
These are generally accepted terms that can be used to e.g. show the human-readable name of the object (the "rdfs:label", for instance).

I cosiddetti "reasoner" possono controllare varie cose, tra cui capire se esistono assiomi che si contraddicono. Se noi appiccichiamo i dati in RDF con la loro ontologia, possiamo usare il reasoner per controllare se tutti gli assiomi (solo dell'ontologia, dato che i dati solitamente non aggiungono assiomi) sono consistenti (con i dati, dato che sono già consistenti dentro l'ontologia) tra di loro.

Questi check però hanno il problema che dicevamo prima, che sono computazionalmente molto pesanti.
Anche solo aggiungendo una tripla bisogna ricontrollare tutto il grafo per avere il check di consistenza.

---
Cosa è opportuno specificare nei metadati?
- Nome e titolo del dataset
- **Identificatore**
    - In FAIR, l'identificatore è essenziale e (quasi) l'unico esplicitamente obbligatorio.
- Descrizione
- Ambiti scientifici di riferimento
- Parole chiave o tag
- Data di creazione
- Data ultima modifica
- Data di pubblicazine
- Frequenza di aggiornamento
- Versione e versioni precedenti
- Dimensione
- Alteri aspetti qualitativi o quantitativi
- Autori
- Editore o persona che ha pubblicato
- Contatto
- Riferimento a dataset che contengono questo qui
- Riferimento a dataset contenuti da questo
- Citazione o riferimento ad "artefatti" legati a questo dataset
- Licenze
- Tipi di autenticazione richiesti per l'accesso
- Provenance
- URL che descrive questa pagina.
- Indirizzi alternativi per questa pagina
- Indirizzi da cui scaricare il dataset
- Tipo di contenuto (grezzo, elaborato, sintetico...)
- Standard usati per esprimere i dati
- Struttura dei dati (e.g. schemi, modelli usati, dettagli sulle variabili misurate, etc...)
- Formati di codifica
- Tipo di compressione dei dati
- Tecniche di misurazione
- Aspetti spaziali (coordinate di regioni spaziali descritte, dove sono state fatte le osservazioni, etc...)
- Aspetti temporali (periodo di tempo descritto dai dati.)

Ovviamente non tutti sono rilevanti in tutti i dataset.

## Principali ontologie
- DublinCore
    - Molto noto e diffuso per i metadati, dalla Dublin Core Metadata Initiative.
    - Se si notano IRI equivalenti dentro a Dublin core stesso sono sinonimi ad altre versioni con quella corrente.
- Schema.org
    - Hanno delle definizioni un pò più da "programmatore", ma in realtà sono uguali quello delle ontologie normali.
    - Ha il concetto di "DataDownload" che serve per specificare l'URL di download della risorsa.

Omeka-S


## Linked Data
The original linked data principles described by Tim Berners-Lee were:
- Use IRIs as names for things;
- Use HTTP(s) IRIs, so that people can lookup those names;
- When someone looks up an IRI, provide useful information, and use the standards of RDF and SPARQL;
- Include links to other IRIs, so that people can discover new things.

An example is [DBpedia](https://dbpedia.org), which fulfills all four of these principles.

