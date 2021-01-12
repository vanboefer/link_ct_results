Link_CT_results
===============

The repo contains the results of an experiment which attempts to link EMA drug authorizations to related clinical trials ([CTgov](https://clinicaltrials.gov/)) and related publications ([PubMed](https://pubmed.ncbi.nlm.nih.gov/)).

The three methods used in the experiment approach the task from different routes:

- The **EPAR_CTgov** method extracts protocol numbers from EMA authorizations, and uses them to search the CTgov register. It then utilizes cross-references from CTgov to PubMed to identify related publications.
- The **PubMed_API** method extracts drug and disease names from EMA authorizations, and uses them to query PubMed. It then utilizes cross-references from PubMed to CTgov to identify related clinical trials. The code for this method can be found [here](https://github.com/vanboefer/pubmed_search).
- The **CUI_grouping** method extracts and normalizes drug and disease names from the free text of records from all three sources. It then groups together records that mention the same disease and drug names. The code for this method can be found [here](https://github.com/vanboefer/cui_grouping).

The experiment is described in detail in the [report](report/).

The results are found in [data](data/).

The [`explore_results.ipynb`](explore_results.ipynb) notebook shows how to load the results into a pandas DataFrame and shows a visualization example.
