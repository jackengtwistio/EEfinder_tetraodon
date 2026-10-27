Directory structure

examples/tetraodon/
├── genome/ # Genome FASTAs and extracted test intervals
│ ├── tetraodon_genome.fna # Full genome
│ ├── tetraodon_1Mb.fna # First 1 Mb test input
│ ├── tetraodon_1to11Mb.fna # 1–11 Mb interval (10 Mb total)
│ └── downloaded/ncbi_dataset/data/GCA_051020865.1/
│ # NCBI assembly download/extraction
├── ncbi_dataset/data/GCA_051020865.1/
│ # Second NCBI extraction location; check for duplicates
├── db/ # Viral FASTA, metadata, host baits and search indexes
│ ├── viral_refseq.faa # Viral reference proteins
│ ├── viral_refseq_raw.csv # Original downloaded metadata
│ ├── viral_refseq.csv # EEfinder-formatted metadata
│ └── viral_refseq.faa.\* # Generated BLAST/DIAMOND indexes
├── results/ # Separate output per run
│ ├── 1Mb_fast/ # 1 Mb, DIAMOND fast
│ ├── 1Mb_fast_retry/ # Retried fast run; command not recovered
│ ├── 1Mb_blastx/ # 1 Mb, BLASTX
│ │ └── tmp_files/ # Intermediate files (not final results)
│ ├── 1to11Mb_fast/ # 1–11 Mb, DIAMOND fast
│ │ └── tmp_files/ # Intermediate files
│ └── 1to11Mb_blastx/ # 1–11 Mb, BLASTX
├── .git/ # Git commits, refs and internal metadata; do not edit
├── .gitignore # Excludes large data and temporary files
├── md5sum.txt # Checksums, where recorded
└── README.md # This guide
