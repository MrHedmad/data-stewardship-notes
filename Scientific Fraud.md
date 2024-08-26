---
topic: Etica e Integrità
date: 2024-05-17
tags: cuap_data_steward, lecture_note
---
> Speaker: Enrico Bucci, PhD 

## Introduction
- Pressure to publish sets up the preconceptions for scientific fraud
    - This is exacerbated by simple metrics like # of publications, instead of quality of content.
- Find standards and conventions to check and protect against fraudulent behaviour
- Some recent examples of scientific fraud
    - Obokata and Sasai: STAP procedure to create STEM cells, published on Nature. Data was fabricated and falsified.
        - Sasai, although being only the supervisor, killed himself.
    - Polderman on the usage of bis-propolol before cardiac surgery to increase post-operation recovery. Seven clinical trials were falsified, while bis-propolol caused an *increase* in death after surgery.
    - Chiranjeevi, many papers in synthetic chemistry over many years, from 2003 and 2007, all completely false.
        - When caught, he denied wrongdoing
    - Shoen, claimed to have found room temperature superconductors.
        - Falsified results as he was the only one in Bell labs that used a machine
        - Got his PhD retracted
    - Thong, copy-pasted astrophysics photos and claimed new discoveries
        - He added people's names as co-authors without their consent.
    - Stapel, falsified many many papers in social psychology
        - He was found out when He published a Nature paper in 2011, where he linked ambient disorder and racism
        - He confessed everything and wrote a book describing his own fraud and what brought him to do it
    - Reinhart and Rogoff, claimed that high public debt hinders economic growth.
        - Data was cherry-picked and statistics was improperly used, invalidating everything.
    - Hunton, on methods to detect accounting fraud.
        - His data was fraudulent, and was detected with Benford's analysis.
    - Hyo Park and Ki Hoo, retracted five papers in engineering where they manipulated images.
        - They eventually admitted fraud and retracted all manipulated papers.
- The FFP standard - Fabrication, Falsification and Plagiarism
    - Fabrication: the experiment was not performed, the data is created: fa
    - Falsification: The experiment was performed, the data is modified without justification (data point are modified, excluded or created)
    - Plagiarism: The experiment was performed, the data is copied many times over or copied over from other sources without proper recognition
        - The damage is that we inflate the evidence of some phenomena improperly.
- There is a degree of fraudulent behavior, from least to most serious
- Bona fide errors are actually good - they are a sign that the scientific study is falsifiable and therefore truly scientific.
    - Falsehood due to errors is *physiologic*
    - Falsehood due to fraudulent data is *pathologic*
- It's easy to produce fraudulent data, but it might be very hard to perform experiments to disprove the fraudulent data, so bad data is very pernicious.
- How to demonstrate a fraud
    - If the FFP standard is violated, it is *misconduct*.
    - Misconduct might be due to negligence, it is an error. If there is intent, however, it is *scientific fraud*.
    - If the scientific fraud has also broken some laws or caused harm, it is a *crime*.
        - Some jurisdictions classify scientific fraud as a crime in itself.

- ? Standard FFP, ma come è nato? Come abbiamo deciso che quella è la riga?

## The history of scientific fraud
- Scientific fraud is not a new invention.
    - Case of Johann Beringer, who published a book in 1725 based on false fossils found in the nearby forests which were planted by colleagues of his as a joke.
    - In 1783, a dutch surgeon, Foersch, claimed and published the existence of trees in some islands that killed anything in a 15 mile radius thanks to poisonous substances.
    - A 70 amber fossil of an ancient insect was found to be fake in 1852 by a student.
    - In 1872, Prescott Jernegan claimed that through electrolysis he could extract gold from the sea.
    - In 1912, Charles Dawson claimed that humans originated in the UK, not in Africa, basing his claims on a cranium he supposedly found in UK. He fabricated the cranium from a modern human combined with an orangutan jaw.
- Famous scientists accused of fraud
    - Sir Isaac Newton was accused of fraud when he claimed of a formula to predict the propagation of sound through the air. The formula was correct but for a multiplicative factor, which skewed the predictions from the data. He created some ad-hoc explanations to fit his prediction with the data, which were lately proven to be incorrect.
        - There was no FFP breach, so these accusations fell. It was just (slightly) *incorrect*, but not fraud.
    - John Dalton was the father of modern chemistry with his atomic theory. Some of his experiments were impossible to replicate today, so there was a claim of fraud
        - However, these claims did not take into account the apparatus used by Dalton, which leaked and therefore allowed the results as described
        - Therefore, the experiment was wrong, but Dalton committed no fraud.
    - Mendel was accused by Fisher (that Fisher, the nazi statistician) that some of the characteristics that he showed were not purely Mendelian in transmission (as we would say today), so that Mendel must have trimmed some of the results by omitting data points that did not agree with his explanations.
        - The claims by Fisher were disproved in two ways, one that Fisher misunderstood the experiment, and that sometimes the phenotype analysed by Mendel could be confused with others, so all of his experiments held up to scrutiny.
- ~ He claims, or wants to claim, that the past is better than the present, since his thesis is that something changed from then to now, but he's showing no hard data so It's a bit meh

## Fraud: Scientific images
- Le prime immagini scientifiche erano disegni presi a mano - non esistendo la fotografia.
    - Darwin con gli animali e i fiori
    - Muller con le immagini al microscopio
    - Galileo con i disegni della luna
- Le immagini possono essere di due tipi:
    - Descrizione di un fenomeno
        - Una fotografia di un oggetto
        - Una scansione microscopica
        - Un disegno della luna
    - Concettualizzazione di un idea o di un fenomeno
- Le immagini descrittive furono democratizzate e standardizzate con l'avvento della fotografia
- Le foto possono anche essere misurate in vari modi, e rendono possibile misurare cose che non possono essere misurate ad occhio nudo (e.g. intensità di stelle invisibili ad occhio nudo)
    - Le immagini sono perciò dati.
- Data manipulation is therefore data manipulation.
- In modern times, digital images are very easily manipulated.
- Subtle image manipulation is often impossible to notice by the naked eye, due to both limitations in our eye and by our behavior of not noticing hidden or distorted patterns
- Software was created to do the job for us, both to check plagiarism and distortions of the figures, and to check for actual data fabrication or fraud

## Fraud: Numerical data
- All the FFP apply here, but we can add a new one about Manipulative Statistics, where statistics, used artfully but in the wrong context, are used to justify some conclusion.
- E.g. the case of Schoen, where he created new data and re-used the same data in different studies.
- Michael Dansinger tried to publish a paper in Annals of Internal Medicine was rejected. He later found his data published in another journal by Carmine Finelli, an italian researcher and part of the editor board of Annals of Internal Medicine, which claimed the data was sourced in southern Italy, not in Germany.
- A very common form of manipulative statistics is spurious correlation.
- Usually, natural processes follow power laws. Benford's law applies this principle to the frequency of the last digit of numbers: 1 is about 30%, 2 is about 17%, and so on, in a power-law like decreasing way.
    - The law often applies, but often does not apply either.
- The Grim test (Granularity-Related Inconsistency of the Mean) is a way to check if calculations were really done as reported.
    - E.g. you have 28 kids, with integer ages. Someone reports that their average age is 5.19. Their total age sum is from 28 to 196 (by definition of "Kid"). Not one value (from 1 to 196 divided by 28) can be 5.19 exactly: the mean is not continuous, so if we can determine possible granularity values we can check if the reported measures are false.
- The SPRITE test checks for similar features. If you have reported that $K$ numbers have mean $\mu$ and sd $\sigma$, you can check the largest value that you'd expect one kid to have given some assumed distribution. In one example case, some kids would have gotten 70 carrots per meal, so the data was found to be fraudulent.
- One needs to be especially careful with p-values which may easily be easily manipulated.
    - Software like staticheck can be used to try and find these manipulations.

## Fraud: Text
- Plagiarism, or text-based fraud, is a pretty complicated topic.
- Plagiarism is taking another's work and claiming it as one's own.
- May or may not imply copying verbatim another's text, without proper attribution.
- May or may not imply copyright infringement.
- May or may not imply (scientific) misconduct.
- Some examples of text plagiarism:
    - Arshad Ali published a paper which was 85% identical to another. He was the president of the higher education committee of Pakistan.
        - Pakistan sets an arbitrary 19% threshold of text identity to be called plagiarism
    - Meucci could not patent the "talking telegraph", but the "telephone" was published and patented by Bell a few years later (from the same lab as Meucci). He sued and almost won, but then died.
- Copyright infringement can still occur even if the source is cited. Plagiarism does not occur if the source is cited.
- Copyright infringement is against the copyright holder (which is not necessarily the author), while plagiarism is always an offense against the author.
- Explicit permission to use the content by the copyright holder does not shield from plagiarism, if the source is not cited properly.
- We can check the corpus of some discipline to see the average plagiarism in all the text. Then we can compare the single document against the rest of the corpus, to see if it's significantly different.
- The practice of "bibliometric fingerprinting" is checking the order of citations between two documents. There is little chance that two unrelated papers cite the same other documents *in the same order*.
    - This catches paraphrases and translations attempts.
- What is NOT considered plagiarism?
    - Matches between text in the same document in other databases;
    - Author information;
    - References;
    - Overlap with correct citation;
    - Overlap with master or PhD theses of one of the authors;
    - Overlap with unpublished working copies of other papers;
    - Overlap with articles published after the publication date of the studied article;
    - Overlap with methods with correct citations;
- How do we check for plagiarism?
    - Scanning the internet
    - Scanning side-by-side with another (suspect) document
    - Matrix-pair confrontation between many different documents.
        - Such a matrix is not necessarily symmetrical: the differences in length between text has a weight.
            - e.g. 100 lines vs 1000 -> 100 / 1000 = 10%
            - 1000 lines vs 100 -> 100 / 100 = 100%
- Different scientific sectors have different baseline plagiarism rates.
    - Generally, humanities reuse a lot of text, while "hard" sciences do it less.

## The aftermath of fraud
- Fraud causes several damages:
    - Damage to science, in its reputation and in the reuse of fraudulent data
        - If even just 1% of all Pubmed papers is false, it has a large effect due to the many many papers that are on PubMed and given how many times they are downloaded.
        - Many papers cite retracted papers, which are then cited and so on, so the wrong information spreads quite quickly.
    - Economic costs
        - In 2014 Stern et. al. estimated about 400'000 dollars lost (in funding and projected damage) per each retracted paper due to fraud.
        - In Italy alone, from the start of the PubMed record, it's estimated that about 2 billion euro have been lost to fraudulent papers
    - Effects on public life
        - For a long time, tobacco companies knew about the health risks but covered it up, also through false claims in published research.
            - Only in 1964 the US Surgeons General advocated for a stop in smoking due to cardiovascular damage caused by smoking.
            - Prof. Rylander published a ton of papers to invalidate the methods used by other scientists who claimed that smoking caused damage. Later, it was found that Prof. Rylander was payed by the tobacco industry to author ghost-written papers.
            - It is projected that if the USSG had spoken before, tens of billions of dollars could have been saved.
        - Stephanies Seneff often uses spurious correlation of usage of gyphosate pesticides with... anything. This has caused famines is some states that have stopped using some products after these (false) claims.
    - Effects on personal life
        - In 1974, Barry Gaudette claimed to have a method of matching hairs based on shape with almost perfect precision to catch criminals. This became the standard for many years. 
            - Once DNA evidence could be examined, re-analysis confirmed that about 95% of cases were wrongly accused. Out of 268 such cases, 14 innocents were executed.
- The career of researchers which perform fraud often end when they are caught. Sometimes this triggers the retraction of their PhD, is severe cases.
- Rarely, fraud is linked to crimes, and researchers are arrested.
    - Dong-Pyou Han was jailed for 5 year after fraud on an HIV vaccine study. The judge cited the possibility of him reiterating the crime for such a punishment.
    - Cina allows even the death penalty for serious fraud in a clinical trial setting.

## Causes of Fraudulent Research
- The psychological incentives to fraud are many
    - The "fraud triangle" has three points, where fraud can grow:
        - Motivation: Opportunistic sizing of a personal gain, or being forced to (e.g. to renew visas)
        - Rationalization: Narcissism, "My theory is correct, no questions. Others will see that I am right"
            - Often, a researcher might believe that their hypothesis is correct, no matter what. This gives then the right to fake data, in their mind.
            - Many feel that they are "invisible", and their fraud will never be spotted in a sea of papers.
            - They might also feel that nothing too bad will happen if they get caught eventually.
        - Opportunity: "I am in control of my data.", "I'm alone, no one will see me"
- Most researchers blame the pressure to publish as the reason for questionable research practices.
- "Homophily" is the tendency of similar individuals to group together, either due to external forces or to internal affinity.
    - This phenomena is seen with fraudulent authors, they tend to collaborate with each other.
        - This might be due to fear of being discovered if collaborating with non-fraudulent researchers.
        - Senior researchers might transmit to underlings fraudulent behaviors
        - Fraudsters are positively selected in the current system

## How to combat fraud
- We will take a look at what strategies we could use to limit fraud
- First of all, we should stop the publish or perish attitude.
    - Peter Higgs (that Higgs, of the boson), famously said that he wouldn't be a professor in today standard.
    - There are two opposite positions, one where bibliometrics are seen as absolute evil, and the other where they are seen as objective and fair.
        - "When the metric becomes a goal, it ceases to be a good metric" - Goodhart's law
- There have been attempts to reform metrics
    - Australia changed from H-index to other metrics (like social impact), but this has resulted to be even worse as a metric.
    - Sweden performed some self-evaluation of quality measures and worked directly with researchers to find particular points and strategies of evaluation. They found this to be particularly effective, and quality measurements are done every few years to check the scientific output and update the standards.
- Create ethic consensus on research integrity and standardize what is taught in such courses.
- Raw data connected to publications should be available to check the work after publication, and preserved for at least a few years.
- COPE is a congregation of journals which have come to an agreement to what is research misconduct
- ORCID to identify the person so that "fake" people are not counted, severely impeding citation milling.
- The EU has created several regulations for research integrity, but they are not legally binding.
- Universities should set up ethical codes and panels of experts to review output and check for fraud before publication
    - Something like this was set up in Canada, however such boards have little power

