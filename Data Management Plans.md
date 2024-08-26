---
date: 2024-06-06
aliases:
  - DMP
---

> [!NOTE]
> These notes were originally taken from a Lecture by Elena Giglia.
> The following was taken from a lecture of Dott. Valentina Pasquale on the 2024-05-24 and redacted to filter out the duplication from above

> It all starts with a good plan


Data management plans are formal documents that define the terms and ways that will be used for handling data during a project. Creating this document (and following its directives) assures data integrity and potentially its FAIRness.

When using DMPs, research becomes data-centric. Having clear rules on how data is handled is key when managing data: it reduces potential errors, it prevents legislative actions and prevents compatibility problems down the line.

A DMP is a living document, meaning it has to change during the project. As new types of data are added and/or new processing becomes necessary, the DMP has to be updated accordingly.

A series of things are specified in the DMP:
- Estimate the types of processed data
- Estimate the amount of data produced
- Estimate the costs of data management and storage
- What methodology is applied on the data to extract information from it.
    - What is used to gather the data, where protocols are saved, how data is manipulated, how data is filtered, how data quality is evaluated
- How the data is handled during and after the project
- Justification of the choices of sharing data in open or closed form, privacy considerations, etc.
- How data will be curated and preserved, in which formats and on which platforms.

A DMP is not difficult to create: the challenging aspect is determining how to manage data in a FAIR and responsible way. The DMP is just the textual form of these considerations.

The most useful workflow when starting out filling a DMP is:
- Run a Preliminary interview to establish a common ground and gather information on what data will be handled (similar to what the data stewardship wizard does). Examples of what to ask:
    - What types of data are generated?
    - Are there GDPR or ethical issues regarding the data?
        - If there are, the Data Protection Officer should be consulted on how to best handle the data in this case.
        - There is also a legal office that deals with these topics.
    - Explain the logic of "As Open As Possible". How open can the data be? How will they be made open? When can they be made open?
    - Provide indications on which specific tools exist for managing data in a FAIR way.
        - Usually, these tools are domain-specific, so there is a domain aspect and domain knowledge of the data steward that is important.
    - Who does what? Who has the responsibility to do the things that are said will be done in the DMP?
    - ~ Be sure to check out all questions that can be asked during a DMP interview, to have some ideas.
        - For example, a source of this is the [[Data Stewardship Wizard]].
- Extract some points that have emerged from these questions and 
- Review the DMP once it has been written.

A workflow can be followed for these questions. For example, the "Data Management Workflow" created by the Data Stewards of the University of Bologna: https://zenodo.org/records/7190005

The DMP is generally very concise and specific. It is good practice to use bullet points and tables.

In the DMP, it is permissible not to know. It is acceptable not to specify some aspects if they are not relevant or if they cannot be estimated at the time of drafting. Since the DMP is dynamic, when these aspects are determined, it gets updated.

The DMP is legally binding. Therefore, it is pointless to write particularly incredible things if they are not practically implemented.

The DMP has common and distinctive sections (these are those of Science Europe, see [https://zenodo.org/records/4915862](https://zenodo.org/records/4915862)):
- Data description and collection or reuse of existing data
- Documentation and data quality
- Storage and backup during the research process
- Legal and ethical requirements, codes of conduct
- Data sharing and long-term preservation
- Data management responsibilities and resources
    - Also include "in kind" support, e.g. unpaid man-hours.

In the same guide, there are the "Core Requirements" of how to translate the answers into a formal DMP (and/or what to ask more specifically).

On RDM Kit, there are domain-specific solutions, focus on the roles of each person in the data process, and there are groupings of tools, specifically in the "bio" area. There are not many things from other domains.

The abstract of the DMP should be related to the project, yes, but data-centric.

This is how prof. Giglia describes a dataset:
- Macroarea: the type of data, like textual or tabular
- Type: the more specific type of data, like the kinds that are collected during the project (e.g. positional data of subject)
- Format (ongoing): the format used during the research process
- Format (preservation): the format deposited for long term preservation
- Software or code?
- GDPR sensible?

Giving a code for each type of data can be beneficial when referencing them in the body of the text.

- ~ How does the Data Stewardship Model work?
- ~ Which are the most important questions asked by the DSW Knowledge model?

While a DMP is often a requirement for getting grants, it is more than that: it can be a very useful tool to not get lost in the sea of data.

Top tips for a DMP of quality:
- Be synthetic
- It's nice to have a DMP that is machine readable (at some level)
- The thing about DMPs is that they are quite complicated and span many different areas (legal, IT, Finance, etc...)
- The European Commission (EC) has a DMP template for Horizon Europe applicants, since in HE the DMP is mandatory
    - "As open as possible, as closed as necessary"
- The EC DMP follows closely FAIR principles
    - Introduction
    - How will you make your data F / A / I / R?
    - Data protection and ethics
        - This is for personal data
    - Other research outputs
        - What other things will be created (code, protocols, items) that are created and that needs to be conserved and highlighted
    - It's mostly focused about the end of the project, for the benefit of the community.
- There are more general DMP templates, that also cover a lot of steps other than FAIR
    - Data summary
        - This is really the crucial point: a list of all the (homogenous) kinds of data that is produced in the research. It's really important to think of all the kinds of data that are produced and analysed by the project.
        - In this point we also take into account the metadata that is generated around the data
        - How can we know if this data is of high quality?
            - This also bleeds into the part of "save only what needs to be saved"
        - A lot of this stuff is automatic in a researcher's brain but it's not spelled out
    - Documentation & data quality
    - Storage and backup during the research process
        - Where are the data stored?
        - Is there space to store this data?
        - How is this data backed up? Does all of it need to be backed up?
    - Legal and ethical requirements
        - Are there humans involved (of any kinds, even people who work in the lab themselves)? Does this cause legal implications? Are there consents that need to be gathered?
    - Data sharing and long term preservations
        - How much data is produced?
        - Can we store all of this data for a long time?
        - How much is the cost of making all the data available?
- How did the IIT set up its DMP writing support service (for level 1 "compliance")?
    1. They made a group of specialists (Project Office, RDM support, ICT, Legal affairs, Technology transfer / terza missione on demand)
    2. They made a single contact point in the form of an email: dmp@iit.it
    3. They made a microsoft teams group to share data and coordinate
        - Generally the data steward is the first point of contact and they share the requests with who is the best office to solve the problem.
    4. The Project Office coordinates the researcher with the financier entity and the RDM
        - They made a workflow on how to internally manage a DMP with the actual steps to follow by PIs and they made specific templates to fill out
- There are both individual projects and multi-partner projects. For multi-partner projects, the DMP is created by the project coordinator.
- What forms did they make?
    - Dataset Questionnaire Form (DQF)
        - It asks researchers questions about every section of the more general DMP from before, making them consider all aspects of the research
        - It has many question rows, and one column per homogenous data types
    - The DMP template of it IIT
        - They have this template that can be edited with the information from the various DQFs that are gathered for the project
        - It's mostly copy-pasted from the Horizon Europe one
        - They condense the information from the DQFs
        - The DQFs have the relevant sections of the DMP template that are highlighted to be relevant
    - They made guidelines for PIs for all of these sections
- These templates are however a bit scattered. There are online tools.
    - They found the tools not satisfactory
    - They also had problems when you have many partners
    - A nice one is DMP Online
    - Other examples are argos (https://argos.openaire.eu)
        - This is dataset centric, and is started to be adopted by the university of Bologna
    - The data stewardship wizard is complex but very potent
        - It also separates between the data input and the creation of the DMP proper.
- The data stewardship wizard has a "Knowledge Model" which is really long and really complete with all the information related to the DMP
- FAIR-Wizard is a paid for solution based on the Data stewardship wizard that provides additional functionalities to manage many DMPs (for a data steward of some company/university)
    - It has a 10 user maximum free tier
    - The CUAP FAIR wizard instance will close in a bit
    - It allows you to make new knowledge models
    - You can split your questions in different phases (during planning, while analyzing the data, after the end of the project, etc...)
    - You can tag your questions as you like, so you can select which sections are more relevant to be filled out