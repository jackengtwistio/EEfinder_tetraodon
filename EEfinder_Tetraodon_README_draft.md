# EEfinder Testing Examples: _Tetraodon_ Genome

This document records the commands used in the _Tetraodon_ EEfinder tests.

## 1. Reference genome and input data

- Genome assembly accession: **NCBI GCA_051020865.1**.
- Genome inputs referenced in the runs: `genome/tetraodon_1Mb.fna` and `genome/tetraodon_1to11Mb.fna`.
- Viral protein reference: `db/viral_refseq.faa`.
- Viral metadata: `db/viral_refseq.csv`.
- Host proteins: `db/tetraodon_host.faa`.

### Genome download — exact executed command to recover

Download tetraodon genome

> datasets download genome accession GCA_051020865.1 --include genome --filename genome/tetraodon.zip

Descargar las proteínas virales
Desde NCBI Virus(https://www.ncbi.nlm.nih.gov/labs/virus/vssi/?utm_source=chatgpt.com):

1. Seleccionar RefSeq Proteins.
1. Pulsar Download → Protein → FASTA → Download all records.
1. Guardar el archivo como db/viral_refseq.faa.
1. Volver a Download, seleccionar CSV y las siete columnas Accession, Species, Genus, Family, Molecule type, Protein y Host.
1. Seleccionar with version para conservar identificadores como YP_009259320.1 y guardar como db/viral_refseq_raw.csv

Crear genome/tetraodon_1Mb.fna:

> python - <<'PY'
> from Bio import SeqIO
> genome = "genome/tetraodon_genome.fna"

> record = max(
> SeqIO.parse(genome, "fasta"),
> key=lambda rec: len(rec.seq)
> )

> fragment = record[:1_000_000]

> SeqIO.write(fragment, "genome/tetraodon_1Mb.fna", "fasta")
> PY

### Sequence extraction

### Viral metadata normalization — partial code recovered

**TODO:**

## 2. EEfinder runs

Run these commands from the _Tetraodon_ working directory, where `genome/`, `db/`, and `results/` exist.

### Test A — 1 Mb,

**Command previously pasted by the researcher:**

```bash
eefinder -in genome/tetraodon_1Mb.fna -od results/1genome -db db/viral_refseq.faa -mt db/viral_refseq.csv -bt db/tetraodon_host.faa -ln 1000 -id -p 4 -lm 100 -fl 1000
```

```bash
eefinder -in genome/tetraodon_1Mb.fna -od results/1Mb_fast -db db/viral_refseq.faa -mt db/viral_refseq.csv -bt db/tetraodon_host.faa -md fast -ln 1000 -id -p 4 -lm 100 -fl 1000
```

```bash
eefinder -in genome/tetraodon_1Mb.fna -od results/1Mb_blastx -db db/viral_refseq.faa -mt db/viral_refseq.csv -bt db/tetraodon_host.faa -md blastx -ln 1000 -id -p 4 -lm 100 -fl 1000
```

### Test B — 1–11 Mb

**Command previously pasted by the researcher:**

```bash
eefinder -in genome/tetraodon_1to11Mb.fna -od results/1to11Mb_fast -db db/viral_refseq.faa -mt db/viral_refseq.csv -bt db/tetraodon_host.faa -md fast -ln 1000 -id -p 4 -lm 100 -fl 1000
```

```bash
eefinder -in genome/tetraodon_1to11Mb.fna -od results/1to11Mb_blastx -db db/viral_refseq.faa -mt db/viral_refseq.csv -bt db/tetraodon_host.faa -md blastx -ln 1000 -id -p 4 -lm 100 -fl 1000
```

## 4. Outputs and interpretation

Inspect and summarize final EEfinder outputs, including those with suffixes:

- `.EEs.fa`: candidate endogenous-element sequences.
- `.EEs.tax.tsv`: associated taxonomic annotations.
- `.EEs.flanks.fa`: flanking sequences.
