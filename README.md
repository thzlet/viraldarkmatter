# Viral Dark Matter: A Systematic Review of Computational Methods for Classifying Divergent Viral Sequences in Metagenomic Data

Companion repository of the undergraduate thesis *"Matéria Escura Viral: uma Revisão Sistemática de Métodos Computacionais para Classificação de Sequências Virais Divergentes em Dados Metagenômicos"*. It holds the protocol, search strings, screening decisions, and extracted data of the review so that every step can be inspected and reproduced.

- **Author:** Letícia Rosemberg Sousa
- **Advisor:** Felipe Bastos Nunes
- **Co-advisor:** Odara Sena dos Santos Feitosa
- **Institution:** Instituto Federal de Educação, Ciência e Tecnologia do Ceará (IFCE), B.Sc. in Computer Science

## Research question

> Which computational approaches have been developed to classify viral dark matter in metagenomic data, and how do they compare in terms of **scalability**, **sensitivity**, and **generalisation capacity**?

"Viral dark matter" denotes viral sequences that cannot be recognised by current tools because they share little or no detectable homology with known references. Depending on the sample type, an estimated 40-90% of sequences in viral metagenomic analyses fall in this category (Galeeva et al., 2025).

## Review design

| Item | Description |
|---|---|
| Reporting guideline | PRISMA 2020 (Page et al., 2021), complemented by Kitchenham & Charters (2007) and SEGRESS (Kitchenham et al., 2023) |
| Databases | IEEE Xplore and Google Scholar |
| Search | Four sequential Boolean strings (plus one complementary variant), see [`protocol/search_strategy.md`](protocol/search_strategy.md) |
| Window | 2021-2026 |
| Core method families | Sequence alignment, k-mer based, profile hidden Markov models, deep learning. Genomic foundation models are treated in the Discussion as an emerging trend |
| Analytical dimensions | Sensitivity, scalability/computational cost, generalisation |

## Selection flow (PRISMA 2020)

| Stage | n |
|---|---|
| Records catalogued after the sequential searches (IDs E01-E46) | 46 |
| Excluded at title/abstract screening | 7 |
| Full-text assessment for eligibility | 39 |
| Excluded after full-text assessment | 31 |
| **Studies included in the synthesis** | **8** |

Diagrams: [`docs/figures/prisma_2020_flow_diagram.jpg`](docs/figures/prisma_2020_flow_diagram.jpg) and [`docs/figures/study_selection_flowchart.jpg`](docs/figures/study_selection_flowchart.jpg). Details: [`docs/prisma_flow.md`](docs/prisma_flow.md).

## Repository structure

```
.
├── README.md
├── LICENSE
├── CITATION.cff
├── .gitignore
├── protocol/
│   ├── review_protocol.md          # question, scope, design, synthesis plan, amendments
│   ├── eligibility_criteria.md     # CI1-CI4 and CE1-CE8
│   └── search_strategy.md          # databases, strings, PRISMA-S items
├── data/
│   ├── README.md                   # data dictionary
│   ├── search/search_log.csv       # every string x database, counts, dates
│   ├── screening/study_register.csv    # E01-E46 with stage and final decision
│   └── extraction/data_extraction.csv  # standardised extraction of the 8 included studies
├── docs/
│   ├── prisma_flow.md              # flow counts and reasons for exclusion
│   ├── prisma_2020_checklist.md    # item -> location in this repository
│   ├── open_items.md               # information still to be recorded
│   └── figures/
├── scripts/
│   └── validate_counts.py          # checks that the CSVs agree with the PRISMA flow
├── papers/                         # local PDFs (git-ignored, copyright)
└── .github/workflows/validate.yml  # runs the validation on every push
```

## Reproducing the checks

Requires Python 3.9+ and no external packages.

```bash
python scripts/validate_counts.py
```

The script verifies that the study register contains 46 records, that 39 reached full-text assessment, that 31 were excluded with a documented reason code, that 8 were included, and that the extraction table covers exactly the included studies.

## Using the data

- `data/screening/study_register.csv` is the single source of truth for decisions. Every exclusion has a criterion code (see [`protocol/eligibility_criteria.md`](protocol/eligibility_criteria.md)) and a reason.
- `data/extraction/data_extraction.csv` follows the extraction form described in the protocol; field definitions are in [`data/README.md`](data/README.md).
- Metrics are reported as published by each study's authors. Values obtained by tool developers on their own benchmarks are not directly comparable with independent benchmarks (see the rigour appraisal in the protocol).

## Copyright note

Full-text PDFs of the reviewed articles are **not** distributed here. Use the DOIs in the study register to retrieve them and place them under `papers/` (ignored by git).

## How to cite

See [`CITATION.cff`](CITATION.cff). Suggested citation:

> SOUSA, Letícia Rosemberg. *Viral dark matter: a systematic review of computational methods for classifying divergent viral sequences in metagenomic data* (data and protocol). Undergraduate thesis, IFCE, 2026.

## References (selected)

- Page, M. J. et al. The PRISMA 2020 statement: an updated guideline for reporting systematic reviews. *BMJ* 372, n71 (2021). https://doi.org/10.1136/bmj.n71
- Kitchenham, B.; Charters, S. *Guidelines for performing systematic literature reviews in software engineering.* EBSE-2007-01 (2007).
- Kitchenham, B. A.; Madeyski, L.; Budgen, D. SEGRESS: Software Engineering Guidelines for REporting Secondary Studies. *IEEE Trans. Softw. Eng.* 49, 1273-1298 (2023). https://doi.org/10.1109/TSE.2022.3174092
- Krishnamurthy, S. R.; Wang, D. Origins and challenges of viral dark matter. *Virus Res.* 239, 136-142 (2017). https://doi.org/10.1016/j.virusres.2017.02.002
- Galeeva, J. et al. Bioinformatics tools and approaches for virus discovery in genomic data: a systematic review. *Viruses* 17, 1538 (2025). https://doi.org/10.3390/v17121538

## License

Code: MIT ([`LICENSE`](LICENSE)). Documents and data: Creative Commons Attribution 4.0 International (CC BY 4.0). Third-party articles remain under their own licences.
