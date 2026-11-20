# Kombucha Microbiome Amplicon Analysis

## Project Overview
An end-to-end bioinformatics pipeline profiling the bacterial communities of kombucha using public amplicon sequencing data (16S rRNA) from the NCBI Sequence Read Archive (SRA). This project adapts a reproducible Bash/QIIME 2 workflow and incorporates custom Python scripts for sequence composition and quality-control metrics, culminating in a scientific research poster.

## Project Goals
- Process raw paired-end amplicon reads from NCBI SRA through quality control, denoising, and taxonomic classification.
- Compare microbial community structure across fermentation conditions (e.g., time points, tea substrates)
- Develop beginner-friendly Python scripts to compute ASV GC-content distributions and summarize DADA2 read-retention statistics.
- Synthesize taxonomic and QC findings into a visual research poster.

## Planned Workflow
1. **Data Acquisition:** Download raw FASTQ reads and sample metadata from NCBI SRA.
2. **Quality Control:** Assess read quality via `FastQC` and `MultiQC`.
3. **Denoising & ASV Inference:** Filter, merge, and remove chimeras using `DADA2` in `QIIME 2`.
4. **Taxonomic Classification:** Assign taxonomy via `VSEARCH` against SILVA (16S)
5. **Python Post-Processing:** Run custom scripts (`gc_content.py`, `read_retention.py`) on exported sequences and stats tables.
6. **Visualization & Poster:** Generate relative abundance barplots and compile results into a research poster.

## Repository Structure
- `data/` — Raw sequencing reads (`fastq/`), reference databases, and intermediate QIIME 2 artifacts (`qiime2/`).
- `metadata/` — Sample manifest and experimental metadata tables (`metadata.tsv`).
- `scripts/` — Modular Bash pipeline scripts (`.sh`) and Python analysis utilities (`.py`).
- `results/` — Tabular outputs, taxonomic summaries, and Python-generated QC/GC metrics.
- `figures/` — High-resolution plots exported for documentation and poster layout.
- `poster/` — Scientific poster drafts, layout assets, and final PDF export.

---

## Lab Notes & Progress Log

### Session 1: Project Initialization
- Set up repository directory skeleton (`data/`, `metadata/`, `scripts/`, `results/`, `figures/`, `poster/`).
- Defined project scope: adapt 18S eDNA Bash pipeline for kombucha 16S/ITS profiling, add Python scripts for GC% and read retention, and design a results poster.
- **Next Step:** Search NCBI SRA for a suitable paired-end kombucha BioProject (target: 6–12 samples with clear fermentation metadata).
