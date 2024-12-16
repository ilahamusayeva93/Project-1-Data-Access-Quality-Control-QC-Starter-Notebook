## Project 1: Data Access & Quality Control (QC) Starter Notebook

Overview

This repository contains the starter notebook for Project 1 focused on accessing and performing quality control (QC) on exome sequencing data from the 1000 Genomes Project. The project includes workflows for data access, population analysis, trimming, and post-QC assessments using industry-standard tools like fastp and FastQC.

Features

Assigned Individual Analysis:
Perform population and historical ancestry analysis for the individual HG00102 from the 1000 Genomes Project.
Exome Sequencing Insights:
Analyze exome sequencing data to determine read quality, variant counts, and more.
Data Processing Workflows:
Download paired-end exome sequencing FASTQ files.
Perform pre- and post-trimming QC.
Automated Trimming Pipeline:
Use fastp for efficient read trimming and generate high-quality, clean datasets.
Visualization & Insights:
Produce detailed reports and summaries using FastQC for trimmed and raw sequencing reads.
Getting Started

Prerequisites
Ensure the following tools and libraries are installed in your environment:

Python (>= 3.8)
wget (command-line utility for file downloads)
fastp (>= 0.23.4)
FastQC (>= 0.11.9)
Setup Instructions
Clone the Repository
git clone https://github.com/ilahamusayeva93/project1-data-access-qc.git
cd project1-data-access-qc
Install Dependencies
Download and install fastp:
wget http://opengene.org/fastp/fastp -O fastp
chmod +x fastp
Download and install FastQC:
wget https://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.9.zip
unzip fastqc_v0.11.9.zip
chmod +x FastQC/fastqc
Run the Notebook Open the Project1-DataAccessQC.ipynb file in Jupyter Notebook or Jupyter Lab to start working on the project.
Workflow Summary

1. Individual Analysis
Assigned Individual: HG00102
Population: British in England and Scotland (GBR).
Historical Insights: Genetic diversity influenced by migrations from Europe and global historical events.
2. Exome Sequencing Data
SRR ID: SRR081224
Download paired-end FASTQ files:
SRR081224_1.filt.fastq.gz (1.63 GB)
SRR081224_2.filt.fastq.gz (1.70 GB)
3. Pre-QC with FastQC
Generate initial quality metrics for raw sequencing reads.
Identify adapter contamination and low-quality regions.
4. Trimming with Fastp
Command:
./fastp -i SRR081224_1.filt.fastq.gz -I SRR081224_2.filt.fastq.gz -o SRR081224_1_trimmed.fastq.gz -O SRR081224_2_trimmed.fastq.gz --cut_front --cut_tail --cut_front_window_size 4 --cut_tail_window_size 4 --cut_front_mean_quality 20 --cut_tail_mean_quality 20 --trim_front1=15 --trim_front2=15
Remove adapters and low-quality bases.
Improve overall sequencing quality.
5. Post-QC with FastQC
Validate trimming results using FastQC reports.
Ensure no adapter contamination and improved sequence quality.
6. Summary of Results
Total Reads Before Trimming: 44,995,826
Total Reads After Trimming: 44,615,438
Reads Lost: ~0.85%

Results

Improved quality metrics after trimming.
Adapter contamination successfully removed.
High-quality paired-end exome sequencing reads for downstream analysis.
Contributing

Feel free to contribute to this project by submitting a pull request or reporting issues via GitHub.
