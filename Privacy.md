---
topic: Privacy
date: 2024-05-09
tags: cuap_data_steward, lecture_note
---
> Ruggero Pensa - ruggero.pensa@unito.it

Un "dato personale" è qualsiasi cosa che può portare ad identificare una persona.

- ~ Altre definizioni nelle slide.

Some data, even when anonymized, can still be used to identify someone e.g. by correlating with publicly available, non anonymized data.

Pseudonymization is the process of anonymizing some data but at the same time save information to de-anonymize it back if needed.
E.g. when using patient data only the privacy manager has the information about the full data, while the data analyst only has access to pseudoanonymized data

I dati personali non dovrebbero proprio essere usati tranne se ci sono tre criteri:
- Trasperenti: il soggetto sa cosa e come
- Legitimate Purpose: il motivo per il quale si processano i dati è legittimo, utile e limitato a questo specifico caso (cioè i dati non devono essere riutilizzati per altri fini)
    - Sta cosa dei fini limitati è un pò una stronzata dato che non sempre si sa cosa si deve fare, e limita la riusabilità
- Proporzionalità: Il processing deve essere adeguato, rilevante e non eccessivo in rispetto agli scopi.

---

Analisi di rischio

"Rischio" di uso illecito per faulty sistemi informativi che fanno danno a persone o organizzazioni.
Quindi 2 dimensioni: le persone di cui i dati sono trattati e i titolari al trattamento.

La prevenzione e la previsione dei rischi è il risk management. La prima parte è il risk assessment, dove si trovano i rischi relativi alla privacy.

PMI -> Piccole Medie Imprese

- ~ Norme ISO e ENISA sulla privacy e sulla limitazione del rischio

---

Come abbiamo detto oggi il "right to be left alone" è stato il primo momento in cui è stato formalmente detto questo "diritto di rimanere indisturbati", negli Stati Uniti. La concezione giuridica di questo diritto si esprime anche in ambiti più laterali, come il diritto all'aborto ("Non puoi interferire con la mia decisione privata di abortire").

Nel mondo Europeo è stata declassata un pò diversamente: riconosciamo uno spazio assolutamente privato in cui la società non deve e non può penetrare: la casa, la vita sessuale, sanitaria, etc...
Una "sfera di opacità" che deve essere preservata quando ci si interfaccia con altri. Solo l'individuo in questione ha il diritto di esporre in parte o in totalità cosa è coperto da questa sfera.

Tanti fattori hanno fatto nascere il GDPR: digitalizzazione e Internet, intelligenza artificiale e maggiore capacità di processare dati in maniera automatica, necessità di far circolare liberamente anche i dati.

Il GDPR ha spostato un pò l'attenzione dal danno (dopo che la privacy è rotta) al rischio (cosa bisogna fare prima che il danno sia fatto).
Ad esempio, l'AI act (che è postumo e costruisce sui concetti del GDPR) trova vari livelli di rischio tra cui "rischio inaccettabile" che include 
- utilizzo di AI che sfruttano tecniche subliminali volte ad alterare comportamenti capaci di portare rischi alla vita di persone
- il riconoscimento facciale, tranne alcune eccezioni (anche grandi, tipo la polizia)
- il *social scoring*

I dati personali non sono coperti dal diritto di proprietà, che è una cosa diversa (e.g. sulle cose possiamo avere il potere di compravendita, usofrutto, alienazione e distruzione, diritto di esclusione dall'utilizzo di terzi).

Solitamente i diritti sono creati per proteggere cose che hanno valore. I dati solitamente hanno poco valore da soli, ma lo acquisiscono quando sono aggregati.

I dati personali sono protetti in quanto *parti della persona*.

Il GDPR ha due approcci: consensualistico e orientato al rischio. Consensualistico perchè chiede il consenso di tutte le persone interessate. Orientato al rischio perchè come detto prima si cerca di prevenire e non curare.
I principi sono quelli che danno la base legale del regolamento - il sè e il come.

Per prima cosa dobbiamo chiederci se possiamo trattare i dati personali. Se non abbiamo nessuna base legale per trattare i dati, non li possiamo trattare. Il GDPR trova sei possibili basi:
- Consenso: se ne abbiamo consenso, possiamo trattare i dati.
- Esecuzione di un Contratto: per eseguire un contratto posso posso processare dati personali (anche senza consenso)
- Adempimento di un obbligo: se la legge mi impone di fare qualcosa con dei dati personali, posso farlo.
- Salvaguardia di interessi vitali: ad esempio per emergenze mediche, per identificare la persona o avvisarne i parenti;
- Interesse Pubblico: se una legge o un ordinanza richiede l'uso di dati personali, si può fare. Se un ente di beneficio pubblico deve fare qualcosa con dati personali, può farlo. Qui è la legge locale che determina cosa è o non è interesse pubblico.
- Legittimo interesse: Non è stato identificato dal GDPR, quindi è stato interpretato. Per quanto riguarda una relazione, se io soggetto posso aspettarmi che ragionevolmente tu responsabile del trattamento usi i miei dati per i fini della relazione specifica, posso farlo. Ad esempio, se vado a confessarmi, posso aspettarmi che i miei dati personali sono trattati per il fatto della relazione stessa.

L'uso di dati in "contesto personale e domestico" non è protetto dal GDPR. Tutti i social scappano dentro questa eccezione (assieme al "legittimo interesse"), anche se è molto sottile.

E' importante definire la base giuridica utilizzata per ogni base giuridica. Ad esempio, una ricerca medica potrebbe cadere sotto l'interesse pubblico.

Se c'è una base giuridica, possono passare al come trattare i dati:
- Necessità: tratto solo i dati strettamente necessari al conseguimento della base giuridica.
- Finalità: devo esplicitare la finalità del trattamento e poi usare solo i dati per quella finalità. Per alcune basi giuridiche questa è ovvia (e.g. eseguire un contratto).
    - La finalità si può "automaticamente" estendere per finalità strettamente collegate o derivanti dalla prima.
- Proporzionalità: i dati strettamente necessari sono trattati e collezionati in quantità strettamente proporzionali e necessari allo svolgimento della base giuridica.
- Minimizzazione dei dati: Ci dovrebbero essere il meno copie possibile dei dati, e serve minimizzare al più possibile quanti dati sono collezionati.
- Qualità ed esattezza: I dati trattati devono mantenersi integri e di qualità. L'output dovrebbe al più possibile essere di qualità, accurato e non dannosi ai soggetti.

Tanti di questi concetti proprio concettualmente non si applicano alle finalità scientifiche (cosa è strettamente necessario se non conosco cosa posso scoprire dai dati prima che faccio lo studio?).

Spesso i dati creati "autonomamente", quindi i metadati (quando ho mandato un messaggio, etc...) sono spesso più importanti per determinare la persona che il dato vero e proprio.

---
2024-05-10

## Analisi del rischio

- Definire una metodologia di analisi
- Rifare almeno una volta l'anno o ogni volta che si cambiano i trattamenti o se ne aggiungono di nuovi

Per definire la metodologia dobbiamo iniziare a pensare a cosa dobbiamo fare attenzione:
- Quale è il contesto di riferimento? e.g. ricerca scientifica, marketing, sanità pubblica, etc...
    - Alcuni contesti sono più pericolosi di altri, come quello sanitario, finanziario, giuridico, se si coinvolge minori (ancora di più se sotto i 16 anni), etc...
    - Quali fattori incidono sull'attività? Sia interni che esterni?
        - Chi può toccare i dati? Chi li produce? Chi li stocca?
        - Chi è la governance della struttura (o le strutture) che tocca i dati?
        - Quante persone ci sono? Quanto tempo si ha? Quanto denaro si ha?
        - Quali sono le competenze specifiche delle persone involved?
        - Chi autorizza cosa? Che flow hanno i dati?
        - Chi internamente può avere interesse hai dati? Quali sono i loro valori? (e.g. trattamento di dati di aborti con anti-abortisti)
        - Quale è la cultura e l'etica dell'organizzazione?
            - L'organizzazione ha delle linee guida specifiche?
        - Quali sono le relazioni contrattuali tra le figure identificate? Quali obblighi hanno?
        - A che livello si sta operando? Quali leggi vanno rispettate in base a questo livello?
        - Quali sono i valori specifici della popolazione che produce i dati sensibili? Quali sono i potenziali rischi alla loro libertà legati a questi dati?
        - 
- Individuare le operazioni che modificano i dati personali, con particolare attenzione ad input dei dati.
    - Quali dati sono trattati? In quale mezzo? Come (accesso da casa o no?)? Quali categorie di persone sono interessate al trattamento? Dove sono conservati i dati?
    - Se esiste il registro dei trattamenti (che dovrebbe già esistere), si fa riferimento a quello.
- Classificare i fattori che determinano il rischio alla privacy
    - Il rischio è $R=PxI$, dove R è il rischio, P è la probabilità che un certo evento succeda e I è l'impatto che succede se quell'evento si realizza.
    - E.g. perdere una chiavetta con dati clinici di pazienti:
        - Impatto altissimo, probabilità alta:
    - per determinare la probabilità si può andare di buon senso, di report pregressi o di statistiche pubbliche.
    - Per determinare gli impatti (alta-media-bassa) si può andare a vedere la criticità dei dati personali, i requisiti normativi, l'importanza di business di quei dati, i diritti e le libertà degli individui impattati
- Calcolare il rischio privacy, con una formula
    - Il paradigma RID di ISO 27001
    - I dati devono essere integri, riservati e disponibili.
    - Integrità:
        - Basso: se i dati sono corrotti, non succede nulla (e.g. sbaglio la promozione).
        - Medio: se i dati sono corrotti, succede poco, come ad esempio perdite di introiti limitate.
        - Alto: si rompono leggi e/o si perde l'immagine dell'organizzazione, si ledono diritti degli individui o dell'organizzazione.
    - Disponibilità: chi ha bisogno del dato lo trova, chi non deve accederci no.
        - Basso: non succede nulla o non tanto se i dati sono inaccessibili per un pò di tempo (e.g. un server rotto)
        - Medio:
        - Alto: si hanno impatti sul business, o i dati non si possono ricollezionare, si rompono leggi o si lede alla libertà degli individui
    - Riservatezza:
        - Basso: se i dati diventano pubblici, succede poco o nulla.
        - Medio: si hanno ripercussioni sul business, non sulla persona
        - Alto: si hanno ripercussioni sulla persona, con imbarazzo o lesione della libertà personale.
    - L'impatto totale è il più alto dei tre individuati.
    - Anche la probabilità è alto/medio/basso. Basso: sarebbe sorprendente che questa cosa succeda. Medio: può succedere, anche 2 o tre volte l'anno. Alto: può succedere spesso o molto spesso.
    - Fai I x R (1/2/3):
        - Rischio alto se RI > 4
        - Rischio medio se RI 3, 4
        - Rischio basso se RI 1, 2
    - Seguire il manuale ENISA per trovare i punti critici di trattamenti per definire bene quali rischi ci sono e quanto gravi sono, vedi le slide. Si fa il calcolo di cui sopra per ogni punto della slide.
- Se il rischio è medio-alto, individuare misure di sicurezza appropriate (anche se è basso, ma con un pò meno attenzione)
    - Modifichiamo il rischio: troviamo misure di sicurezza ulteriori che abbassano il rischio (e.g. abbasso la probabilità)
    - Condividere il rischio: affido il trattamento ad attore esterno che mi garantisce un certo livello di sicurezza
    - Evitare il rischio: non faccio il trattamento.
    - Se il rischio è molto alto, bisogna comunicarlo al garante della privacy
    - Vedi Annex A ISO 27001 e ISO 27701 per alcuni spunti
- Approvare il metodo di analisi e l'analisi vera e propria del rischio dal responsabile alla privacy
    - Codifica l'accountability al responsabile del trattamento.

Se il rischio è alto e non minimizzabile bisogna fare la DPIA o la PIA al garante della privacy PRIMA che si inizia il trattamento. Il garante poi approva o no.

---

What discord has is RBAC - Role Based Access Model. The evolution of this is Attribute Based Access Control, which has increased features based on context:
- Role based, just like RBAC
- Time gated access (e.g. limit access during non-work hours)
- Location based access (either geolocation or device-based)
- How the information is accessed
- What information is trying to be accessed

ABAC is like RBAC but "evolved". ABAC works with policies, which are often expressed in natural-like language. E.g. "**Doctors** can **view** **medical records** of **any patient** in **their department** and **update** **any patient** **medical record** that is **directly assigned to them**, during **work hours** and **from an approved device**". The highlighted keywords can easily be translated to machine readable items.
ABAC (and RBAC) can also allow anonymous access (to some data).

Many DBs can do column encryption, where some columns are encrypted by the user and so are opaque to database managers.

Auditing: a formal review of the systems of some company/project/team/anything. It has a cost, but can provide a bunch of benefits. 
When some process is in production, so we have a result of some kind, we can start an audit. It has three phases: understand objectives, review the processes and their quality, and document the result.

We can do something similar with data. We can check what happened, when and by who, often when editing the file (but reading massive amounts of data should be audited). This is done by reading log files. However, log files can be very very large, often impossible to log everything for a long time.

I dati aggregati (Macrodata) possono essere di tipo frequenza o di tipo "media/mediana". Fare attenzione alle categorie con poche (o unico) pazienti, perchè potrebbero essere soggetti a cross-identification.
I microdati sono i dati specifici per ogni persona.
I microdati possono essere protetti con metodi di statistica "disclosure control". Queste manipolano i microdati in modo tale che essi non possano essere ricondotti a un singolo.
Alcune di queste tecniche sono:
- Sampling di campioni anonimi
- Regole per accedere ai dati in certe tabelle (e.g. solo in maniera aggregata).
- Random rounding, controlled rounding, confidentiality editing, cell suppression, etc...
Manipolando i dati, però, deve essere in ottica di tenere i dati utili per quello che bisogna farci (quindi non devono distorcere i risultati troppo).

"Linking Attack": cross-referencing different data tables to find the specific person with that data in another (not anonymous) dataset.
These "linker data" (e.g. birthdate, sex, zip code) are called "quasi identifiers" since they *almost* identify someone. They end up identifying someone when you combine them all together.

There are some techniques to prevent this as much as possible:
- k-anonymity: It encompasses generalization and suppression:
    - generalization: generalize a specific data point: e.g. year instead of full date, less specific zip code for a larger area.
    - suppression: delete some information
    - The "k" refers to how many people can be identified by any single combination of quasi identifiers in my table.
        - E.g. if k = 500, we can never identify less than 500 people at once when we group the data based on all its quasi identifiers.
            - We can express this in probability as 1/k to find some specific person given the data.
            - Of course this is the smallest possible group that can be found (e.g. if you combine 5 attributes and get a k=50 for almost all entries, except for one person who would be identified, the whole table is k = 1)
    - Generalization increases the k, while suppression decreases the amount of generalization needed to achieve a certain k.
        - We can suppress columns or rows or even a single cell, depending on what is the problematic bit.
        - We can generalize columns or single cells
    - It is clear that the choice of k is crucial. The balance is between the amount of data shared and its usefulness.
- Homogeneity of the sensible attributes is a problem in k-anonymity. If I know that some group has cancer (and all people in that group have cancer), I can still map people partially with the data and get that they have cancer.
    - This is positive and negative disclosure problems.
    - To combat this, we have to ensure *diversity*, l.
        - If a table is k-anonymous and l-diverse, it means that in any anonymous group we have at least l different sensible data.
        - The l classes should also be balanced in frequency (or it would be overwhelmingly likely that some person has one l instead of another).
        - Even if they are balanced, they might leak information, especially if one category is incredibly more frequent than another.
            - e.g. HIV+ or -, 99% are -: If we group them with a 50% probability we can still increase our knowledge of some individual (from 99% chance to 50%)
- The previous points are resolved with t-closeness, when the tolerance for similarity inside the l classes is measured, and only a certain tolerance is allowed.
- There are algorithms that explore the possible masks, and force a certain t,l,k-anonymity.
- "Differential privacy" is based on the concept by which two different datasets can be used to reach the same conclusions, independent on if a single individual is introduced or opts out from the study.
    - We can infer information from large-scale, subsequent queries that look at the *differences* between the queries.
        - When we add a single person (and we can do it with queries "artificially") and ask for aggregation metric, we can check for differences between this value and the value with the one extra person, therefore identifying the person.
        - To combat this, we return the aggregate, but instead of the real value we sample from a Laplace distribution centered on the actual value. This causes a random "noise" to be added to the metric, making detecting a difference of just a single person (almost) impossible.
    - This is codified as a value. An e-differential dataset respects this law:
      $e^{-\epsilon} \leq \frac{P(M(q,D) = R)}{P(M(q,D') = R)} \leq e^{\epsilon}$
      Where $D$ and $D'$ are adjacent datasets, meaning they differ of one row. $M()$ is applying a query $q$ to some dataset, with a result of $R$.
    - The global sensitivity of the query $q$, $GS(q)$, is the difference over $R$ that the change introduces, which might be a lot or not that much, depending on $q$. We can estimate this value.
        - The Laplace function that we sample often has $GS(q) / e$ variability, so that we increase the uncertainty the more sensible some query is.
    - The $\epsilon$ is the "privacy budget".