# Search Strategy

Structured following the PRISMA-S extension;

## Databases

| Database | Platform | Rationale |
|---|---|---|
| IEEE Xplore | ieeexplore.ieee.org | Journals and conferences in electrical engineering, computing and applied AI |
| Google Scholar | scholar.google.com | Multidisciplinary; used to capture articles in bioinformatics and computational genomics journals (e.g. Genome Biology, Briefings in Bioinformatics, Microbiome, PLOS Computational Biology, GigaScience) |

Rationale for the choice: the closest prior review searched PubMed only; this review adds sources that cover computing literature.

## Concept blocks

1. **Viral object:** "viral dark matter", "unknown viral sequences", "unclassified viral reads", "divergent viral sequences"
2. **Computational/AI:** "machine learning", "deep learning", "classification", "algorithm", "bioinformatics tool", "foundation model"
3. **Data domain:** "metagenomics", "virome", "metagenomic"

## Search strings

Because of the large initial yield and the polysemy of "dark matter", four strings of increasing specificity were applied sequentially.

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

**String 4, complementary variant**

```
"viral dark matter" AND ("machine learning" OR "deep learning") AND metagenomics AND "viral classification"
```

## Results per string (Google Scholar)

| String | Records |
|---|---|
| 1 | 1,100 |
| 2 | 581 |
| 3 | 128 |
| 4 | 64 |
| 4 (variant) | 46 |

## Screening of search results

Results were filtered by title and keywords, checking for an algorithmic component associated with viral metagenomics. The retained records were catalogued as E01-E46 in the control spreadsheet; 39 proceeded to full-text eligibility assessment.

## Other PRISMA-S elements

- **Limits and filters:** the temporal window (2021-2026) is applied through the eligibility criteria.
- **Deduplication:** identical records across databases are excluded under CE8. Records E25 and E43 share the same DOI and are treated as one article.
- **Supplementary methods:** none reported (no citation chasing or grey-literature searching). Seminal references cited in included papers were used only for the theoretical background.
- **Peer review of the search (PRESS):** not performed.
- **Documentation:** all strings are archived verbatim in this repository.
