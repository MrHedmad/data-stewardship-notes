---
created_on: 2024-07-04
---
> Speakers: Alessia Bardi e Paolo Manghi, CNR

- Scientific infrastructure necessarily has to follow the changing needs of researchers
    - With the growing need to publish data and code, infrastructure must adapt

- DSpace in an example of a repository platform

There are many types of data sources:
- PID registries: E.g. DataCite, Crossref, ORCID, ROR.org each with a different use case
- Digital repository or archive (the two terms are interchangeable): Platforms that manage and provide free access to research outputs for the benefits of all.
    - See the COAR Repository Toolkit
    - Some examples are biorxiv, arxiv, textgrid (for text data from the humanities), Europe PMC, PANGAEA (for environmental and earth sciences).
    - Some national repositories are HAL (for French production), the DataVerseNL (Netherlands)
    - Some catch all repositories are Zenodo, figshare, DRYAD, etc...
- Scientific databases are more specifically those repositories with specific architectures for specific data types, that can do something special with them
    - Some examples of scientific databases are UniProt, FlyBase, pubchem, etc...
- Aggregators are platforms that aggregate metadata from various sources.
    - They can be either "traditional" with just a list of resources, or follow the Scientific Knowledge Graph (SKG), where the aggregated information is represented in the form of a graph.
    - Some examples are OpenAIRE Graph, google scholar, BASE, OpenAlex

There are Repositories of repositories, like OpenDOAR, ROAR and r3data (for open access repositories, generic and of research data, respectively).
    - re3data has a bunch of filters which might be interesting to see what aspects of data repositories are more relevant

[D4Science](https://d4science.org) - un virtual research environment

CRIS: Current Research Information System: a way to keep track of funding, people, projects, devices, publications, other outputs, etc... in an institution 
    - See [Wikipedia](https://en.wikipedia.org/wiki/Current_research_information_system)

## Interoperability protocols
We'll talk about OAI-PMH, SWORD, COAR Notify and Signposting.

- OAI-PMH: Open Archive Initiative - Protocol for Metadata harvesting
    - Exchange protocol for matadata, based on HTTP
    - Can exchange many types of metadata, by default (and by requirements) the Dublin Core
    - Like REST APIs, OAI-PMH can be used to exchange metadata information
    - Each real resource is an *item*. Each item may have one or more records. The Dublin core metadata record must be present in each item.
        - Each record is a file with a specific header, XML metadata and about section.
            - The header has record metadata, like the ID, the modification date, the set (collection) of this record, and its status (e.g. "deleted").
                - The header serves as a fast way for APIs to keep each other updated on what has changed in the database
            - The metadata is some metadata blob that follows some schema (like dublin core)
            - The about section is again an XML blob with provenance information of this record.
    - Like REST, OAI-PMH has verbs to describe what it can do
        - Identify: Describe this repo
        - ListMetadataFormat, ListSets: list available metadata formats and available sets
        - ListRecord, getRecord, etc...: request data from an endpoint
- The url can be found in the registries aggregators, like OpenDOAR. It is https://zenodo.org/oai2d
- ? Perche' hanno trattato i "set" in maniera speciale?
    - Bho, non sembra ci sia un motivo
- The full protocol is available online [here](https://www.openarchives.org/OAI/openarchivesprotocol.html)
- SWORD is another such protocol
    - It stands for Simple Web-service Offering repository Deposit
    - It can be used to deposit something
- COAR Notify and Signposting
    - They are used to tell aggregators that there is something new to fetch. They help interoperability between data repositories and between data repositories and aggregators

---

