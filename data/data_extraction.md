# Data Extraction

Characteristics of the 8 studies included in the synthesis. Values are reported as published by each study's authors.

## General characteristics

| ID | Tool | Authors | Year | Venue | Paradigm | Code availability |
| --- | --- | --- | --- | --- | --- | --- |
| E01 | RNN-VirSeeker | Liu et al. | 2022 | IEEE/ACM TCBB | Recurrent neural network (LSTM) | Open (GitHub) |
| E02 | VirHunter | Sukhorukov et al. | 2022 | Frontiers in Bioinformatics | Hybrid: CNN + Random Forest | Open (GitHub) |
| E03 | PhaGCN2 | Jiang et al. | 2023 | Briefings in Bioinformatics | Graph convolutional network (GCN) | Open (GitHub) |
| E05 | Multi-biome benchmark | Wu et al. | 2024 | Genome Biology | Independent empirical benchmarking (9 tools) | Open (Snakemake/Zenodo) |
| E06 | VirRep | Dong, Chen and Zhao | 2024 | Genome Biology | Hybrid language representation (BERT + BiLSTM) | Open (GitHub/Zenodo) |
| E29 | VirSorter2 | Guo et al. | 2021 | Microbiome | Multi-classifier, expert-guided (Random Forest) | Open (Bioconda/Bitbucket) |
| E31 | NextVir | Robertson, Consul and Vikalo | 2025 | PLOS Computational Biology | Genomic foundation models (DNABERT-S, Nucleotide Transformer, HyenaDNA) | Open (GitHub/Zenodo) |
| E38 | IPEV | Yin et al. | 2024 | GigaScience | Deep learning (2D-CNN) | Open (GitHub) |

## Data and validation

| ID | Tool | Genetic material | Sequence length | Validation data |
| --- | --- | --- | --- | --- |
| E01 | RNN-VirSeeker | Viral DNA | Short reads (~500 bp) and fragments up to 5,000 bp | NCBI RefSeq; CAMI challenge (CAMI_high); real human gut metagenome |
| E02 | VirHunter | Viral RNA | Fragments of 500 bp and 1,000 bp; contigs ≥750 bp | NCBI Plant Viruses; 12 real plant RNA-seq datasets (peach, grapevine, beet) |
| E03 | PhaGCN2 | Viral DNA and RNA | Fragments from ≥1,700 bp to full genomes | ICTV (2020/2021); Global Ocean Virome (GOV2.0); Gut Phage Database (GPD) |
| E05 | Multi-biome benchmark | Viral and cellular DNA | Contigs ≥1,500 bp (physical fractionation, 0.22 µm) | 8 paired virome/microbiome datasets from 3 biomes (polar seawater, agricultural soil, human gut) |
| E06 | VirRep | Viral DNA | Fragments of 1.5 kb to complete genomes (>20 kb) | GGCM (~140k genomes: GVD, GPD, CHVD, MGV); IMG/VR-gut; DEVoC; GPIC; colorectal cancer cohort |
| E29 | VirSorter2 | Viral DNA and RNA | Fragments of 1 kb to complete genomes | NCBI Viral RefSeq; integrated proviruses; uncultivated marine and soil viromes; 51 curated bacterial genomes |
| E31 | NextVir | Viral DNA and host | Sequencing reads of 150 bp | Human genomes and 7 oncovirus classes (HBV, HPV, HCV, EBV, HTLV, HHV-8, MCV) |
| E38 | IPEV | Viral DNA/RNA (VLP viromes) | Reads and fragments of 1,200 to 1,800 bp | VLP viromes; NCBI RefSeq; marine and longitudinal gut viromes |
