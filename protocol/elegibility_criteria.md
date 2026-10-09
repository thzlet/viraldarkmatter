# Eligibility Criteria

Criteria were defined before full-text assessment to ensure reproducibility and limit selection bias. One criterion (CE6) was added during full-text assessment; see the amendments section of the [protocol](review_protocol.md).

## Inclusion criteria

| Code | Criterion | Definition |
|---|---|---|
| CI1 | Computational methodological scope | The article proposes, implements or empirically evaluates a computational method, algorithm or tool for classifying or detecting divergent or uncatalogued viral sequences, with demonstrated application to metagenomic or virome data. |
| CI2 | Temporal window | Published between 2021 and 2026, to capture contemporary tools and the most recent methodological transition. |
| CI3 | Peer review | Published in an international peer-reviewed scientific journal. |
| CI4 | Accessibility and language | Full text available for detailed analysis, written in Portuguese or English. |

## Exclusion criteria

| Code | Criterion | Definition |
|---|---|---|
| CE1 | No original algorithmic component | Purely laboratory, biological, clinical or ecological studies without systematic development or evaluation of a computational component. |
| CE2 | Lack of generalisation | Studies restricted to the epidemiology or diagnosis of a single viral species/group, without an algorithmic proposal generalisable to broad taxonomic diversity. |
| CE3 | Literature reviews without primary data | Narrative, bibliometric or prior systematic reviews with no own algorithmic implementation or new computational experiments. |
| CE4 | Grey and preliminary literature | Conference abstracts, master's and doctoral theses, conference proceedings without journal expansion, and non-peer-reviewed manuscripts on preprint servers. |
| CE5 | Non-primary genomic data | Studies that do not operate directly on viral nucleotide or protein sequences. |
| CE6 | Competing non-viral classes | Tools designed to classify several mobile genetic element classes concurrently in the same predictive task (for example viruses and plasmids). |
| CE7 | Repositories without an original classifier | Descriptive articles on genomic databases, ecological catalogues or functional-annotation servers that use third-party classifiers and propose no new classification methodology. |
| CE8 | Duplicates | Identical records retrieved repeatedly across the consulted databases. |

## Notes on application

- Historical baselines outside the window (VirFinder, 2017; DeepVirFinder, 2020) are not included in the synthesis (CI2) but are discussed in the theoretical background as reference points.
- Database and review articles excluded under CE3/CE7 may still be cited for context (e.g. IMG/VR v4, MetaVR, Krishnamurthy & Wang 2017).
- General-purpose multi-species genomic models (e.g. DNABERT-2) are not viral detection tools and are excluded under CE6/CI1.
