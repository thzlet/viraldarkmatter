# Review Protocol

Systematic literature review conducted following PRISMA 2020 (Page et al., 2021), with the recommendations of Kitchenham & Charters (2007) and SEGRESS (Kitchenham, Madeyski & Budgen, 2023) for search strings and the data extraction form.

## 1. Research question

Which computational approaches have been developed to classify viral dark matter in metagenomic data, and how do they compare in terms of scalability, sensitivity and generalisation capacity?

## 2. Scope

- **Object:** viral sequences that are divergent or have undetectable homology to reference databases (viral dark matter).
- **Method families:** sequence alignment, k-mer frequencies, profile hidden Markov models and deep learning.
- **Analytical dimensions:** predictive sensitivity, scalability / computational cost, and generalisation to divergent sequences and heterogeneous biomes.
- **Context:** metagenomic and virome data, studies published between 2021 and 2026.
- **Genomic foundation models** are discussed as an emerging trend, not as a core category.

## 3. Information sources and search strategy

Databases: **IEEE Xplore** and **Google Scholar**.

Four sequential Boolean strings were applied, each more specific than the previous one, because of the high number of initial hits and the ambiguity of the term "dark matter".

**String 1 (exploratory)**
```
("viral dark matter" OR "unknown viral sequences" OR "unclassified viral reads" OR "divergent viral sequences") AND ("machine learning" OR "deep learning" OR "classification" OR "algorithm" OR "bioinformatics tool" OR "foundation model") AND ("metagenomics" OR "virome" OR "metagenomic")
```

**String 2 (machine learning and viral classification)**
```
("viral dark matter" OR "unknown viral sequences") AND ("machine learning" OR "deep learning" OR "viral classification") AND (metagenomics OR virome)
```

**String 3 (classification and virus identification)**
```
("viral dark matter" OR "unknown viral sequences") AND ("machine learning" OR "deep learning") AND (metagenomics OR virome) AND ("viral classification" OR "virus identification")
```

**String 4 (deep learning and metagenomics)**
```
"viral dark matter" AND "deep learning" AND metagenomics AND "virus identification"
```

Complementary variant:
```
"viral dark matter" AND ("machine learning" OR "deep learning") AND metagenomics AND "viral classification"
```

## 4. Eligibility criteria

### Inclusion

| Code | Criterion |
| --- | --- |
| CI1 | The article proposes, implements or empirically evaluates a computational method, algorithm or tool for classifying or detecting divergent or uncatalogued viral sequences, with demonstrated application to metagenomic or virome data. |
| CI2 | Published between 2021 and 2026. |
| CI3 | Published in a peer-reviewed international journal. |
| CI4 | Full text available, written in English or Portuguese. |

### Exclusion

| Code | Criterion |
| --- | --- |
| CE1 | No original algorithmic component (purely laboratory, biological, clinical or ecological studies). |
| CE2 | Focus on the epidemiology or diagnosis of a single viral species, without a generalisable algorithm. |
| CE3 | Literature reviews (narrative, bibliometric or systematic) without primary data or original computational experiments. |
| CE4 | Grey literature: conference abstracts and proceedings without journal extension, master's dissertations, doctoral theses, and non-peer-reviewed preprints. |
| CE5 | Studies that do not operate directly on viral nucleotide or protein sequences. |
| CE6 | Tools designed to classify several mobile genetic elements concurrently in the same task (e.g. viruses and plasmids). |
| CE7 | Database, catalogue or annotation-server papers that use third-party classifiers and propose no new classification method. |
| CE8 | Duplicate records. |

## 5. Selection process

1. **Screening:** records returned by the four strings were screened by title and keywords, checking for an algorithmic component associated with viral metagenomics. Records were catalogued with IDs E01 to E46.
2. **Eligibility:** the 39 pre-selected articles were assessed in full text against CI1-CI4 and CE1-CE8.
3. **Inclusion:** 8 studies met all criteria.

Reasons for exclusion at the full-text stage (n = 31):

| Criterion | n |
| --- | --- |
| CE3: reviews without primary data | 10 |
| CE4: preprints, dissertations, conference proceedings | 8 |
| CE7: databases and repositories | 4 |
| CE1/CE5: ecological / environmental virome studies | 3 |
| CE6/CI1: competing classes or non-viral models | 2 |
| CI2: outside the time window | 2 |
| CE2: single-virus focus | 1 |
| CI4: full text unavailable | 1 |

VirFinder (2017) and DeepVirFinder (2020) fall outside the time window and are used only as historical baselines in the theoretical background.

## 6. Data extraction

Each included study was described using the following fields: study ID, authors and year, title, venue, tool name, paradigm and architecture, central objective, datasets used, type of genomic material, sequence length, validation design (k-fold, independent split, leave-family-out, progressive synthetic mutation), reported metrics (AUROC, AUPRC, accuracy, sensitivity, precision, F1, MCC), treatment of divergent sequences, application to real metagenomic data, scalability evaluation (hardware, runtime, memory) and code availability.

## 7. Analytical dimensions

- **Sensitivity and detection efficacy:** sensitivity (recall), precision, F1-score, AUROC, AUPRC and MCC. AUPRC and MCC are emphasised because viral DNA often represents less than 5-10% of a metagenome, so accuracy alone can be misleading.
- **Scalability and computational efficiency:** runtime, memory (RAM/VRAM), CPU/GPU requirements, and behaviour across sequence lengths, from short reads (<500 bp) to long contigs (>10 kb).
- **Generalisation:** performance on sequences with low identity to known references (<30-35%), across heterogeneous biomes, and under synthetic mutations and indels.

## 8. Methodological rigour appraisal

Included studies were appraised on three points:

1. **Training/test independence:** whether the split was done at the taxonomic family or whole-organism level, avoiding leakage from fragments of the same genome appearing in both sets.
2. **Empirical ground truth vs simulation:** studies based only on reference genomes (e.g. NCBI RefSeq) carry historical representation bias. Studies using physical size fractionation (0.22 µm filters) or mock communities provide stronger validation.
3. **Independent benchmarking:** extra weight was given to benchmarks where tools were run under identical conditions by authors not involved in developing them.

## References

- Page, M. J. et al. The PRISMA 2020 statement: an updated guideline for reporting systematic reviews. *BMJ* 372, n71 (2021). https://doi.org/10.1136/bmj.n71
- Kitchenham, B.; Charters, S. *Guidelines for performing systematic literature reviews in software engineering.* EBSE-2007-01 (2007).
- Kitchenham, B. A.; Madeyski, L.; Budgen, D. SEGRESS: Software Engineering Guidelines for REporting Secondary Studies. *IEEE Trans. Softw. Eng.* 49, 1273-1298 (2023). https://doi.org/10.1109/TSE.2022.3174092
