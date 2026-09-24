# RNA-seq Analysis Pipeline
A reproducible RNA-seq data-processing workflow for transcriptomic analysis of *Vibrio cholerae*, starting from raw Illumina FASTQ files and proceeding through quality control, read trimming, genome alignment, gene-level read quantification and downstream expression analysis.

## Overview

This workflow was developed to analyze RNA-seq data comparing wild-type (WT) an CgtA knockdown (KD) samples of *Vibrio cholerae*.

The pipeline includes:

- Quality assessment of raw sequencing reads
- Adapter and quality trimming
- Post-trimming quality control
- Reference genome preparation
- Read alignment
- SAM/BAM processing
- Gene-level read quantification
- DESeq2-based normalization
- Log2 fold-change calculation

## Workflow

```text
Raw FASTQ files
       ↓
FastQC
       ↓
Adapter & Quality Trimming (fastp)
       ↓
FastQC + MultiQC
       ↓
Reference Genome Preparation
       ↓
HISAT2 Alignment
       ↓
SAM/BAM Processing
       ↓
featureCounts
       ↓
Gene Count Matrix
       ↓
DESeq2 Normalization
       ↓
Log2 Fold-Change Calculation
