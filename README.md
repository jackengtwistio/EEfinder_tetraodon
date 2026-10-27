
## Directory structure

```text
tetraodon/
├── genome/                       # Genome FASTA files
│   ├── tetraodon_genome.fna       # Complete genome
│   ├── tetraodon_1Mb.fna          # First 1 Mb
│   ├── tetraodon_1to11Mb.fna      # 1–11 Mb interval
│   └── downloaded/               # NCBI download
├── ncbi_dataset/                  # Additional NCBI extraction
├── db/                            # Viral and host databases
├── results/                       # EEfinder outputs
│   ├── 1Mb_fast/                  # DIAMOND, 1 Mb
│   ├── 1Mb_fast_retry/            # Retried run
│   ├── 1Mb_blastx/                # BLASTX, 1 Mb
│   │   └── tmp_files/            # Temporary files
│   ├── 1to11Mb_fast/              # DIAMOND, 10 Mb
│   │   └── tmp_files/
│   └── 1to11Mb_blastx/            # BLASTX, 10 Mb
├── .gitignore                     # Files excluded from Git
├── md5sum.txt                     # Checksums
└── README.md                      # Documentation
```

Complete tree

```text
examples/tetraodon/
├── db/                                      [ignored] Viral/host references and indexes
│   ├── viral_refseq.faa                     Viral proteins
│   ├── viral_refseq_raw.csv                 Original viral metadata
│   ├── viral_refseq.csv                     EEfinder-ready metadata
│   ├── tetraodon_host.faa                   Host proteins for filtering
│   └── *.dmnd, *.phr, *.pin, *.psq          [generated] DIAMOND/BLAST indexes
├── genome/                                  [ignored] Genome inputs
│   ├── tetraodon_genome.fna                 Full assembly FASTA
│   ├── tetraodon_1Mb.fna                    1 Mb test input
│   ├── tetraodon_1to11Mb.fna                1–11 Mb interval (10 Mb total)
│   └── downloaded/                          Additional NCBI extraction
│       └── ncbi_dataset/
│           └── data/
│               └── GCA_051020865.1/
├── ncbi_dataset/                            [ignored] Another NCBI extraction location
│   └── data/
│       └── GCA_051020865.1/
├── results/                                 Run-specific outputs (keep final results)
│   ├── 1Mb_fast/                            1 Mb, DIAMOND fast
│   ├── 1Mb_fast_retry/                      Retried run; exact command unverified
│   ├── 1Mb_blastx/                          1 Mb, BLASTX
│   │   └── tmp_files/                       [ignored] Intermediate files
│   ├── 1to11Mb_fast/                        1–11 Mb, DIAMOND fast
│   │   └── tmp_files/                       [ignored] Intermediate files
│   └── 1to11Mb_blastx/                      1–11 Mb, BLASTX
├── .git/                                    [generated] Git's internal repository data
│   ├── objects/
│   │   ├── pack/
│   │   ├── info/
│   │   ├── 2f/
│   │   ├── a6/
│   │   └── e0/
│   ├── info/
│   ├── logs/
│   │   └── refs/
│   │       ├── heads/
│   │       └── remotes/
│   │           └── origin/
│   ├── hooks/
│   └── refs/
│       ├── heads/
│       ├── tags/
│       └── remotes/
│           └── origin/
├── .gitignore                               Ignore rules
├── md5sum.txt                               File checksums
├── EEfinder_Tetraodon_README_draft.md       Earlier draft
└── README.md                                This document
```
