# DRSM-corpus

An annotated literature corpus for NLP studies of 'Disease Research State' based on different categories of research (`DRSM` stands for `Disease Research State Model`). This corpus reflects our current state of manually-curated research data for this task combined with curation instructions and details about the curation process.

**Status:** Note that this project is in it's very early stages and should be considered `Unstable` _(Early, active development, and may lack sufficient end-user documentation, assistance, etc., for anything other than the earliest adopters)_.


## Getting Started

We provide access to a single corpus of primary research articles consisting of PubMed identifiers (`pmid`) with (A) one-or-more codes that are intended to designate the high-level type of research being performed in the paper (`codes`), and (B) MONDO URIs that designate a specific disease (see https://github.com/monarch-initiative/mondo) with the accompanying disease name (`MONDO_URI`, `Disease`). We include an additional column to denote irrelevant papers (i.e., papers that were included in the curation corpus but were excluded because they were off-topic, or were review articles: `irrelevant`). 

The codes are intended to reflect the primary foci of the paper in terms of the primary research being performed.

Data is distributed as tab delimited text file. 

## Current Category Model


## Code of Conduct 

This project adheres to [the Contributor Covenant code of conduct](https://www.contributor-covenant.org/), described in more detail here: [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to opensource@chanzuckerberg.com.


## Security 

Please note: If you believe you have found a security involving this project, please responsibly disclose by contacting us at security@chanzuckerberg.com.
