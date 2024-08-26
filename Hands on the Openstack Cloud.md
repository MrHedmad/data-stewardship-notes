---
topic: Informatica Moderna
date: 2024-04-11
tags: cuap_data_steward, lecture_note
---
> Speaker: Prof. Marco Aldinucci

Definition of "cloud computing" from the National Institue of Standards and Technologies (NIST):
> Cloud computing is a model for enabling ubiquitous, convenient, on-demand **network access** to a **shared pool** of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be **rapidly provisioned** and released with **minimal management effort** or **service provider interaction**.
> This cloud model is composed of five essential characteristics, three service models, and four deployment models.
> NIST - https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-145.pdf

These "five characteristics" are:
- On demand self-service;
    - The user can autonomously purchase, access and use the cloud services, with (little to) no human interaction.
- Broad Network access;
- Resource Pooling;
    - The resources I'm using are shared with others, so access to CPU time might be an issue, as is data security and/or privacy.
- Rapid elasticity;
    - You can upscale or downscale rapidly what resources you have access to.
- Measured services;

The three service models are:
- Software (SaaS);
    - You get a ready-to-use deployed solution, like google drive.
- Platform (PaaS);
    - You get a series of software networked and configured together, like a webserver plus a database.
- Infrastructure (IaaS);
    - You get a (virtual) machine accessible on demand from remote.

The four deployment models:
- Private;
- Community;
- Public;
    - Google Cloud, Amazon Web Services, etc...
    - Public as is "The public can buy it"
- Hybrid;
    - Multiple clouds that offer some method of working together, such as a private cloud that works together with a public cloud, but work may be offloaded from (e.g.) the public cloud to the private cloud in high demand situations, for instance.
    - It's a bit of a weird definition, since these "deployment models" change based on which user you are.

There are many other definitions, some good (like the one on wikipedia), some more peculiar.

In modern time, cloud computing is pervasive: most consumer software generally connects to some cloud service to perform its functions. Cloud computing also comes with a cost, which is as pervasive in daily life as its functions.

- ! We have credentials on HPC4AI to run some experiments, if we so choose. Links, usernames and passwords are on the slides.

Ci sono vari tier di sicurezza per i datacenter. Ad esempio, un Tier 3 (come HPC4AI) è completamente ridondante: ogni servizio è almeno sdoppiato: un solo guasto non lo può rompere. Un tier 2 ha qualche ridondanza. Un tier 4 è resiliente anche alla completa distruzione di una delle strutture che contengono i server. Queste sono le classificazioni dell'uptime institute, uno degli enti che fa queste valutazioni.

Per creare una private cloud serve la piattaforma (il bare metal), e del software. Esempi sono openstack (che usa HPC4AI) e vmware.

---

Bottleneck importante nelle infrastrutture è il link tra la CPU e la memoria interna, sia RAM che di memoria fisica.

I server di HPC4AI costano dai 40k ai 350k ciascuno, e ce ne sono vari.

C'è software che impedisce la lettura out of bounds di regioni di memoria di altri processi: l'hypervisor.

Esempio di uso di HPC4AI:
- Gruppi di "tenants" possono avere projects diversi. Ogni Project ha una certa quantità di risorse per spawnare VM.
- I "Floating IPs" sono outbound-facing
- Ogni macchina ha il suo IP interno, sempre
- I security group sono firewall a livello di rete locale del cloud: ad esempio posso decidere di bloccare in principio tutto tranne la porta 22 in ingresso.
    - Questo per aumentare la sicurezza delle macchine.

#CUAP_data_steward