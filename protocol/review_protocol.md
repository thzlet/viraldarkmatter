# Review Protocol

**Title:** Viral Dark Matter: A Systematic Review of Computational Methods for Classifying Divergent Viral Sequences in Metagenomic Data
**Type:** Systematic literature review (exploratory-descriptive, qualitative categorisation with quantitative extraction of reported metrics)
**Reporting guideline:** PRISMA 2020 (Page et al., 2021), combined with Kitchenham & Charters (2007) and SEGRESS (Kitchenham, Madeyski & Budgen, 2023)

## 1. Rationale

Viruses lack a universal marker gene comparable to bacterial 16S rRNA and mutate rapidly, so similarity-based identification fails for a large share of sequences in metagenomic data. This unclassified fraction is called *viral dark matter* (Krishnamurthy & Wang, 2017). Large reference collections such as IMG/VR v4 (over 15 million uncultivated virus genomes) and MetaVR (24 million) show that the problem persists and grows.

The closest prior work, Galeeva et al. (2025), followed PRISMA 2020 but searched PubMed only and did not place viral dark matter at the centre of the analysis. This review:

1. adds databases that index computing literature (IEEE Xplore, Google Scholar);
2. focuses on divergent/unclassified viral sequences; and
3. compares methods along three explicit axes: sensitivity, scalability and generalisation.

## 2. Objectives

**General objective:** systematise and compare computational methods for classifying viral dark matter in metagenomic data.

**Specific objectives**

- a) Map the evolution of computational methodologies (alignment, hidden Markov models, k-mers, machine/deep learning) for viral dark matter classification.
- b) Categorise the selected studies by their main classification approach.
- c) Identify the performance metrics reported and compare their relevance for practical use.
- d) Identify frequent limitations and gaps reported by the authors of the included studies.
- e) Discuss promising trends (including genomic foundation models).

## 3. Research question and scope

> Which computational approaches have been developed to classify viral dark matter in metagenomic data, and how do they compare in terms of scalability, sensitivity and generalisation capacity?

| Dimension | Definition |
|---|---|
| Object | Divergent viral sequences or sequences with undetectable homology in reference databases |
| Methodological approaches | Sequence alignment, k-mer frequencies, profile HMMs, deep learning |
| Comparisons | Direct, empirical comparison between algorithmic paradigms |
| Analytical dimensions | Predictive sensitivity, scalability/computational cost, generalisation to divergent sequences and heterogeneous biomes |
| Context and window | Metagenomic and virome data; studies published 2021-2026 |

## 4. Information sources and search

See [`search_strategy.md`](search_strategy.md). Databases: IEEE Xplore and Google Scholar. Four sequential strings of increasing specificity (plus one complementary variant of the last string) were applied; the filters were applied progressively to narrow the result set.

## 5. Eligibility criteria

See [`eligibility_criteria.md`](eligibility_criteria.md).

## 6. Selection process

1. **Identification.** Run the strings in both databases.
2. **Screening.** Records are screened by title and keywords for a computational component applied to viral metagenomics. Clinical-diagnostic, botanical or agronomic records without computational development are discarded. Retained records receive a unique identifier (E01-E46) in the control spreadsheet.
3. **Eligibility.** Full texts of the pre-selected records are checked against CI1-CI4 and CE1-CE8. Each decision and its justification is recorded in [`../data/screening/study_register.csv`](../data/screening/study_register.csv).
4. **Inclusion.** Studies meeting all inclusion criteria and no exclusion criterion form the primary corpus.

## 7. Data collection

Data were extracted into a standardised form (spreadsheet, exported here as [`../data/extraction/data_extraction.csv`](../data/extraction/data_extraction.csv)) with 16 core fields:

1. Study identifier
2. Authors and year
3. Title
4. Journal and source database
5. Method/tool name
6. AI/ML paradigm and architecture
7. Central objective
8. Datasets (training, validation, test)
9. Genomic material type (DNA virus, RNA virus, both)
10. Sequence length evaluated
11. Experimental validation design (k-fold CV, independent split, leave-family-out, progressive synthetic mutation)
12. Reported effectiveness metrics (AUROC, AUPRC, accuracy, recall, precision, F1, MCC)
13. Treatment of divergent sequences
14. Application to real metagenomic data
15. Scalability reporting (hardware, run time, memory)
16. Code availability

The repository table additionally records comparators, stated limitations and free-text notes.

## 8. Analytical dimensions

**Dimension 1 - Sensitivity and detection efficacy.** Recall/TPR = TP / (TP + FN); precision = TP / (TP + FP); F1 = 2PR / (P + R); AUROC and AUPRC (important under class imbalance, as the viral fraction in metagenomes can be below 5%); MCC = (TP x TN - FP x FN) / sqrt((TP + FP)(TP + FN)(TN + FP)(TN + FN)).

**Dimension 2 - Scalability and computational efficiency.** Run time as a function of input size, memory and CPU/GPU demand, and degradation of performance or cost with sequence length (reads below 500 bp to contigs above 10 kb).

**Dimension 3 - Generalisation.** Behaviour on sequences with low identity to references (below about 35%), across biomes (soil, ocean, gut, plant viromes) and under mutations and sequencing noise (substitutions and indels).

## 9. Rigour appraisal (risk of bias)

Because medical risk-of-bias tools do not fit computational studies, rigour was appraised on three criteria:

1. **Independence of training and test data**: partitioning at taxonomic-family or whole-organism level to avoid leakage from fragmenting one genome into both sets.
2. **Empirical ground truth versus simulation**: studies relying only on reference genomes (e.g. NCBI RefSeq) are biased towards similarity-dependent tools; physical size fractionation (0.22 um filters) or mock communities provide stronger validation.
3. **Neutrality of comparative experiments**: independent benchmarks (authors not involved in developing the compared tools) receive additional weight.

## 10. Synthesis plan

Qualitative and quantitative synthesis organised by methodological category: alignment-based (baseline), k-mer based (VirFinder lineage), profile HMMs (vFams, VIRify), deep learning (recurrent, convolutional, graph-based, hybrid, attention/transformer). Genomic foundation models are analysed in the Discussion as a frontier trend, not as a fifth core category. Results are tabulated per study and compared along the three analytical dimensions; no meta-analysis is planned because of heterogeneous datasets and metrics.
