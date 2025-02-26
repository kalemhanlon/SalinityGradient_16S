# runnign fastQC and multiQC on the raw sequencing data

##load fastQC

# Full path: /programs/FastQC-0.12.1/fastqc 
export PATH=/programs/FastQC-0.12.1:$PATH

running fastQC
fastqc /workdir/kh832/SalinityGradient_16S/data/01_DADA2/01_raw_gzipped_fastqs/*.fastq.gz \
    --threads 5 \
    -o /workdir/kkh832/SalinityGradient_16S/analysis/00_FastQC/fastqc_reports/

#Loading multiQC

export PYTHONPATH=/programs/multiqc-1.15/lib64/python3.9/site-packages:/programs/multiqc-1.15/lib/python3.9/site-packages
export PATH=/programs/multiqc-1.15/bin:$PATH

running multiQC

multiqc fastqc_reports/ -o multiqc_results/


# Configuring git on the server: cbsulm35
git config --global core.editor "nano -w"
git config --global init.defaultBranch main 


