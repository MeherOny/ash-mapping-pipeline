# Ash Mapping Pipeline 🌳🧬

This repository contains the full pipeline used for **genotyping-by-sequencing (GBS)** and **QTL mapping** of *Fraxinus* (ash) trees for resistance to emerald ash borer (EAB). The workflow includes demultiplexing, QC, trimming, alignment, SNP calling, filtering, genetic map construction, and QTL analysis.

---

## 📁 Repository Structure

```bash
ash-mapping-pipeline/
├── scripts/         # SLURM shell scripts (.sh, .qsh) for each pipeline step
├── envs/            # Conda environments for all tools used
├── R/               # R scripts for downstream analysis and plotting
├── docs/            # Markdown summaries and documentation
├── .gitignore       # Files to ignore during version control
├── LICENSE          # MIT License
└── README.md        # This file
```

---

## 🚀 Pipeline Overview

| Step | Description                         | Script                     |
|------|-------------------------------------|----------------------------|
| 01   | Demultiplexing (Sabre)              | `scripts/01_demultiplex.qsh` |
| 02   | QC (FastQC + MultiQC)               | `scripts/02_fastqc.sh`       |
| 03   | Trimming (fastp)                    | `scripts/03_fastp.sh`        |
| 04   | Alignment (BWA)                     | `scripts/04_bwa.sh`          |
| 05   | Variant Calling (GATK)              | `scripts/05_gatk.sh`         |
| 06   | Filtering (VCFtools, PLINK)         | `scripts/06_filtering.sh`    |
| 07   | Genetic Map (Lep-MAP3)              | `scripts/07_lepmap3.qsh`     |
| 08   | QTL Mapping + Visualization (R)     | `R/qtl_summary_plots.R`      |

---

## 🧪 Environments

All tools are run in reproducible Conda environments. Activate one with:

```bash
conda env create -f envs/<tool>.yml
conda activate <tool>
```

List of environment files:

```bash
envs/
├── fastqc.yml
├── fastp.yml
├── bwa.yml
├── gatk.yml
├── vcftools.yml
├── plink.yml
├── samtools.yml
├── multiqc.yml
├── lepmap3.yml
└── qtl_R.yml
```

---

## 📊 Output & Summaries

Final results (genetic maps, QTL plots, etc.) and descriptions are located in:

```bash
docs/ash_resistant_geneticmap_QTL_summaries.md
```

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 👩‍💻 Contact

**Meher Afroze Ony**  
Graduate Student, Entomology and Plant Pathology  
University of Tennessee, Knoxville  
GitHub: [@MeherOny](https://github.com/MeherOny)
