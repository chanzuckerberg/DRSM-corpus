# DRSM-corpus

An annotated literature corpus for NLP studies of 'Disease Research State' based on different categories of research (`DRSM` stands for `Disease Research State Model`). This corpus reflects our current state of manually-curated research data for this task combined with curation instructions and details about the curation process.

## How was this dataset collected? How has it been processed?:

The corpus was generated by manually curating titles and abstracts of primary research papers that were queried from the CZIF's knowledge graph based on searches for disease names and synonyms. The classification scheme was devised in house in consultation with external experts from external ontologies, rare disease organizations, drug companies, and other CZI team members (and is undergoing revision as we progress with this work). Curation as performed by members of an internal CZIF biocuration team.

**Status:** Version 1 of this curation work is now complete. Note that this project is under development and should be considered `Unstable` _(Early, active development, and may lack sufficient end-user documentation, assistance, etc., for anything other than the earliest adopters)_.

## V1 Corpus

We provide access to a corpus of primary research articles expressed as several `*.tsv` files:

We use the service provided by [`Centaur Labs`](https://centaurlabs.com/) to scale up curation for these categories. This provides a dataset with the following columns. 

* **Index** - The PubMed Identifier of the paper
* **Labeling_State** - `Gold Standard` if label generated from our in-house team, `Labeled` if generated by CentaurLabs annotators. 
* **Explanation** - Explanations for gold standard labels provided by our in-house team. 
* **Correct_Label** - Primary category as described above. 
* **Agreement** - A score from 0.0-1.0 showing how much agreement there was for the label from CentaurLab annotators. We only use data with agreement > 0.6.
* **TITLE** - the title of the paper
* **TRIMMED_ABSTRACT** - the abstract of the paper trimmed to 400 words, preserving the trailing text of the abstract.  

At present, this dataset consists of **1,144 'Gold Standard' articles** labeled by our in-house curation team and **16,951 articles labeled by CentaurLabs annotators**. This provides a corpus of **18,174 rare-disease primary research articles** labeled for relevance and the type of research. 

### Provenance / Additional Data Files

We perform in-house curation to define an 'initial_gold standard' set with the following columns: 

* ID_PAPER - The PubMed Identifier of the paper 
* TITLE - The title of the paper
* ABSTRACT - The abstract of the paper
* PRIMARY CATEGORY - The category designated to indicate the primary contribution of the paper (based on our in-house curation scheme). 
* SECONDARY CATEGORY - The category indicating a secondary role of the paper (based on our in-house curation scheme). 
* IRRELEVANT - boolean tag that denotes if this paper is a primary research article (not a review or a conference report, etc)
* DISEASE_NAME - Name of the disease queried from Meta's paper repository

The codes are intended to reflect the foci of the paper in terms of the primary research being performed. 

[See this wiki page for the latest categorization used to denote different classes of disease research paper.](../../wiki/Category-Model)  

Note - due to the complexity of this model, we are restricting ourselves to a subset of categories in our initial work, see [this wiki page](../../wiki/Initial-Curation-Task) .

### We include all available curated data for provenance and transparency

We provide access to all curated data being used. This includes data taken across multiple curators within a team, filtered for consensus, and then checked and edited by a senior curator. This data is available as a `*.tsv` file (labeled 'raw_data'), with the same columns as above with three additional data columns:  

* CURATOR - An anonymized code for each curator / checker  
* COMMENTS - Curation comments for this task  
* TIMESTAMP - The date + time that the CATEGORY score for this record was entered

## V2 Corpus - Specialized Subtypes of Paper 

We developed a model to determine if a given research study belongs to a broader, specialized type of paper. The types of these papers include the following categories judged to be of high priority to rare disease research:

* Quality of Life (file: `v2/qol_all_2022_12_15.tsv`)
* Natural History Study
* Diagnostic/Treatment Guidelines
* Disease Models/Assays
* Biomarkers (dx/disease progression/treatment evaluation)
* Therapeutic targets/approaches
* Partnerships with pharma/IP agreements
* Clinical trials 
* Approved/repurposed drugs

We are currently working through datasets for each of these categories to support the development of specialized classifiers that can recognize these types of papers from their titles + abstracts alone. We have completed the data for the studies involving Quality of Life studies as shown.

The annotation schema we use for these studies conforms to the following basic design:

| Code | Explanation |
|---|---|
| -1 | the paper is not a primary experimental study in disease | 
| 0 | The study does not directly investigate the phenomena of interest |
| 1 | the study investigates the phenomena of interest but not as its primary contribution |
| 2 | the study's primary contribution centers on investigating the phenomena of interest |

The stucture of the data is as shown below: 

| Column | Definition |
|---|---|
| PMID | The Pubmed ID of the annotated paper | 
| Labeling_State | `Gold_Standard` or `Labeled` for whether the paper was annotated in-house by CZI staff or by CentaurLabs annotators | 
| Correct_Label | The correct label for this document |
| Agreement | The agreement score generated by CentaurLabs curators |
| Title | The title of the paper |
| Abstract | The abstract of the paper |
| vector | a 4-value vector denoting the different weights for different categories generated by the CentaurLabs annotation process |
 
## Code of Conduct 

This project adheres to [the Contributor Covenant code of conduct](https://www.contributor-covenant.org/), described in more detail here: [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to opensource@chanzuckerberg.com.

## Primary Contact 

Please direct any questions or feedback for this work to Gully Burns (CZIF Research Scientist) at gully.burns@chanzuckerberg.com 
