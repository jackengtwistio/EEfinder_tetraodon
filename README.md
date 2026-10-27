
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
