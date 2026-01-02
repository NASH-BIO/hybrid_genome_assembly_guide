# Whole Genome Sequence and Assembly 

## Overview
## Workflow
### 1. Raw Reads

We will use grabseqs for raw reads downloading. 
#### 1.1. Install grabseqs

```bash
# install grabseqs
conda create -n grabseqs -y 
conda activate grabseqs

#for downloading grabseqs i used this command:
conda install grabseqs -c louiejtaylor -c bioconda -c conda-forge -y


# but for some this would take a lot of time because its not an official channel
# so try the mamba command if conda takes too long: 
# mamba install grabseqs -c louiejtaylor -c bioconda -c conda-forge -y (remove the # when using)
# if it still gives you error try to can do it by python as well 
#conda istall python=3.9 -y
#pip install grabseqs (but you wont pigz support this way which is required for the tool to work properly)
# dependencies
#conda install conda-forge::pigz -y
#conda install conda-forge::sra-tools -y
```

#### 1.2. Download raw reads
```bash

# to download a sequence illumina run
grabseqs sra SRR35136585

We require the metadata:
# to download a sequence illumina run
grabseqs sra -t 4 -m metadata.csv SRR8893090

#first run for nanopore reads
grabseqs sra -t 4 -m metadata.csv SRR8893087
#Second run for nanopore reads
grabseqs sra -t 4 -m metadata.csv SRR8893086
#Pacbio Read
grabseqs sra -t 4 -m metadata.csv SRR8893091
```
--- 
# To download the whole project:
```bash

grabseqs sra SRP610834 

#to get help
grabseqs sra -h

# srr file with -t 
grabseqs sra -t 4 -m metadata.csv SRR8893090
```