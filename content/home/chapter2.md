+++
weight = 40
+++
{{% section %}}

# Chapter 2

### Genome graph applications for *M. tuberculosis* and public health

Benchmark Nanopore versus Illumina SNP calling and show our algorithms meet the needs of clinical and public health users.

<progress class="chapter1-progress" max="100" value="10"></progress>
</br>10%

---

## Tuberculosis

-   \#1 cause of death by a single pathogen
-   Standard of care requires phenotypic testing (DST) of the infecting organism - *Mycobacterium tuberculosis* - against the four first-line drugs
-   *M. tuberculosis* is slow-growing - gold-standard DST takes ~2 months

---

## TB and Public Health

-   Public health requirements for TB diagnostics are resistance prediction, species identification, and clustering of genomes.
-   Requirements currently met with Illumina
-   Reasons to consider switching to Nanopore: cost, location of burden, speed
-   Patient to result in 12.5 hours (2017) with Nanopore - and yield has improved since then

---

## Genetic clustering

The first step towards clustering a set of genomes is determining a distance matrix.

-   ~~Feeding aligned genomes into a phylogenetic tree-building tool~~
-   Counting SNP differences and clustering based on these

---

## Genetic clustering

We define genetic distance to be the sum of genetic discordances, where missing data
and heterozygosity do not cause discordance (unless the zygosity does not include the
reference allele) and study the clustering this definition generates.

---

## Chapter Aims

*M. tuberculosis* public health applications

-   ~~Species identification~~
-   Prediction of drug resistance
-   Epidemiological clustering of sample

**How can `pandora` be used to improve these requirements?**

**Show that Nanopore sequencing is now capable of performing these tasks**

---

## Dataset

Same isolate DNA extraction sequenced on both Illumina and Nanopore

-   119 samples from Madagascar (35 PacBio)
-   83 samples from South Africa (evidence of transmission pairs)
-   20 samples from Birmingham

---

## What have I done?

-   Getting data from collaborators
-   Organising data
-   Repeat
-   Providing assistance to collaborators
-   Preliminary results of data quality and resistance-calling for collaborators

---

## What's left to do?

### Analysis

---

## Baseline variant analysis

#### Variant truth sets

-   Illumina - `clockwork`, combining best of `samtools` and `cortex`
-   Nanopore - `samtools` with some filtering and masking

Baseline Illumina/Nanopore concordance, using PacBio as a validation (where we have it)

---

### Variant Calling

**Using four PRGs of varying complexity:**

-   Call SNPs and indels with `pandora`
-   Compare to baseline calls
-   Report concordance rate
-   How does complexity of PRG affect concordance and computational cost

---

### Clustering

-   Calculate pairwise SNP distance from truth-set
-   Calculate pairwise SNP distance from `pandora` with "best" PRG
-   Main figure will be dot plot of the two distance matrices - hoping for linear relationship

---

{{% /section %}}
