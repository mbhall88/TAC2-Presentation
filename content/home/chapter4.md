+++
weight = 60
+++
{{% section %}}

# Chapter 4

### Construction of a *M. tuberculosis* reference pan-genome

Curate a high-quality reference pan-genome for *M. tuberculosis* that includes a detailed map of the *pe/ppe* genes.

---

### Reasons for a *M. tuberculosis* pan-genome

-   Closed pan-genome
-   Some genes not present in H37Rv
-   ~10% of the genome consists of *pe/ppe* genes

<img src="images/pangenome.jpg"  height="300" width="400" style="border: none;">

---

### The enigmatic *pe/ppe* genes

-   Implicated in immune evasion and virulence
-   A disproportionately large amount of genetic diversity
-   Nucleotide diversity ~2-fold higher than rest of the genome
-   Sufficiently similar that short reads fail to map
-   Frequently masked out of analyses

---

## Chapter Aims

The ability to accurately map sequencing reads to these genes would likely improve our ability to perform variant calling in *M. tuberculosis* and therefore better determine how isolates relate to each other.

**Build a high-quality pan-genome for _M. tuberculosis_, to allow variant discovery in all genes - ideally including the _pe/ppe_ genes.**

---

## Data

-   Assemble highest quality genomes from Chapter 2 plus very high-quality data from outside this thesis
-   Assemblies will act as a "scaffold" for the pan-genome along with CRyPTIC variants
-   Divide the genome into discrete pieces

---

### Genome graph map of *pe/ppe* genes

-   If *pe/ppe* genes arose via gene conversion short reads likely multi-map
-   With high-quality short+long read assemblies, we hope to improve current resolution and allow more accurate mapping

**Produce a collection of high-quality _pe/ppe_ PRGs with information about what read length will provide reliable mapping, and whether Illumina data can be reliably mapped to them.**

---

## Analysis

Re-analyse data from Chapter 2 and see if we are better able to cluster samples with this new pan-genome with *pe/ppe* map 



Assess variation in *pe/ppe* genes across 10,000 samples from CRyPTIC

{{% /section %}}
