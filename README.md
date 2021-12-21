# DRSM-corpus

An annotated literature corpus for NLP studies of 'Disease Research State' based on different categories of research (`DRSM` stands for `Disease Research State Model`). This corpus reflects our current state of manually-curated research data for this task combined with curation instructions and details about the curation process.

## How was this dataset collected? How has it been processed?:
The corpus was generated by manually curating titles and abstracts of primary research papers that were queried from the CZIF's knowledge graph based on searches for disease names and synonyms. The classification scheme was devised in house in consultation with external experts from external ontologies, rare disease organizations, drug companies, and other CZI team members (and is undergoing revision as we progress with this work). Curation as performed by members of an internal CZIF biocuration team.

**Status:** Note that this project is in it's very early stages and should be considered `Unstable` _(Early, active development, and may lack sufficient end-user documentation, assistance, etc., for anything other than the earliest adopters)_.

## Getting Started

We provide access to a corpus of primary research articles expressed as a `*.tsv` file ([final_data.tsv](https://github.com/chanzuckerberg/DRSM-corpus/blob/main/final_data.tsv)) with the following columnns:

* PMID - The PubMed Identifier of the paper 
* TITLE - The title of the paper
* ABSTRACT - The abstract of the paper
* CATEGORIES - a comma-delimited set of categories used to classify the paper 
* IRRELEVANT - boolean tag that denotes if this paper is a primary research article (not a review or a conference report, etc)
* DISEASE_NAME - Name of the disease queried from Meta's paper repository
* URI - MONDO URI of the disease being characterized (see https://github.com/monarch-initiative/mondo, codes are reused MONDO's CC-BY 4.0 licsense).  

The codes are intended to reflect the primary foci of the paper in terms of the primary research being performed. 

[See this wiki page for the latest categorization used to denote different classes of disease research paper.](../../wiki/Category-Model)  

Note- due to the complexity of this model, we are restricting ourselves to a subset of categories in our initial work, see [this wiki page](../../wiki/Initial-Curation-Task) .

## We include all available curated data for provenance and transparency

We provide access to all curated data being used. This includes data taken across multiple curators within a team, filtered for consensus, and then checked and edited by a senior curator. This data is available as a `*.tsv` file ([curated_data.tsv](https://github.com/chanzuckerberg/DRSM-corpus/blob/main/curated_data.tsv), with the same columns as above with three additional data columns:  

* CURATOR - An anonymized code for each curator / checker  
* COMMENTS - Curation comments for this task  
* TIMESTAMP - The date + time that the CATEGORY score for this record was entered

## Code of Conduct 

This project adheres to [the Contributor Covenant code of conduct](https://www.contributor-covenant.org/), described in more detail here: [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to opensource@chanzuckerberg.com.

## Primary Contact 

Please direct any questions or feedback for this work to Gully Burns (CZIF Research Scientist) at gully.burns@chanzuckerberg.com 
