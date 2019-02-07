# ![nf-core/vipr](docs/images/vipr_logo.png)

[![Build Status](https://travis-ci.org/nf-core/vipr.svg?branch=master)](https://travis-ci.org/nf-core/vipr)
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A518.10.1-brightgreen.svg)](https://www.nextflow.io/)
[![Gitter](https://img.shields.io/badge/gitter-%20join%20chat%20%E2%86%92-4fb99a.svg)](https://gitter.im/nf-core/Lobby)

[![install with bioconda](https://img.shields.io/badge/install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/)
[![Docker Container available](https://img.shields.io/docker/automated/nfcore/vipr.svg)](https://hub.docker.com/r/nfcore/vipr/)
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/1405)

### Introduction

**nf-core/vipr** is a bioinformatics best-practice analysis pipeline
for assembly and intrahost / low-frequency variant calling for viral
samples.

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with docker / singularity containers making installation trivial and results highly reproducible.

### Pipeline Steps

| Step                                                | Main program/s                      |
|-----------------------------------------------------|-------------------------------------|
| Trimming, combining of read-pairs per sample and QC | Skewer, FastQC                      |
| Decontamination                                     | decont                              |
| Metagenomics classification / Sample purity         | Kraken                              |
| Assembly to contigs                                 | BBtools' Tadpole                    |
| Assembly polishing                                  | ViPR Tools                          |
| Mapping to assembly                                 | BWA, LoFreq                         |
| Low frequency variant calling                       | LoFreq                              |
| Coverage and variant AF plots                       | Bedtools, ViPR Tools                |

### Documentation

Documentation about the pipeline can be found in the `docs/` directory:

1. [Installation and configuration](docs/installation.md)
2. [Running the pipeline](docs/usage.md)
3. [Output and how to interpret the results](docs/output.md)

### Credits

This pipeline was originally developed at the
[Genome Institute of Singapore](http://a-star.edu.sg/gis) by
[Andreas Wilm](https://github.com/andreas-wilm/). It started out as an
ecosystem around LoFreq and went through a couple of iterations. The
current version had three predecessors
[ViPR 1](https://github.com/CSB5/vipr),
[ViPR 2](https://github.com/CSB5/vipr2) and
[ViPR 3](https://github.com/gis-rpd/pipelines/tree/master/germs/vipr).

An incomplete list of publications using (previous versions of) ViPR:

- [Sessions et. al., PLoS Negl Trop Dis., 2015](https://www.ncbi.nlm.nih.gov/pubmed/26327586)
- [Sim et al., PLoS Negl Trop Dis., 2015](https://www.ncbi.nlm.nih.gov/pubmed/26325059)

Plenty of people provided essential feedback, including:

- [October SESSIONS](https://www.duke-nus.edu.sg/content/sessions-october)
- [Paola Florez DE SESSIONS](https://www.a-star.edu.sg/gis/Our-People/Platform-Leaders)
- ZHU Yuan
- Shuzhen SIM
- CHU Wenhan Collins
