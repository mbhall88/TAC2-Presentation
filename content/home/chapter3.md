+++
weight = 50
+++
{{% section %}}

# Chapter 3

### Prediction of drug resistance in *M. tuberculosis* using genome graphs and Nanopore sequencing

Improve upon current whole-genome sequencing-based drug resistance prediction for *M. tuberculosis* using genome graphs.

---

## Tuberculosis

-   WGS-based diagnostics offer faster solution
-   Two-week "liquid culture" gives similar results
-   For the four first-line drugs, a study by the CRyPTIC consortium demonstrate that DST is not required if genotype predicts susceptibility

---

## CRyPTIC

##### Comprehensive Resistance Prediction for Tuberculosis: an International Consortium

-   Perform DST (14 drugs) and WGS on 40,000 global *M. tuberculosis* samples (many MDR)
-   Combine with WGS data from another 60,000 samples
-   The aim is to improve genotypic resistance prediction by expanding our catalogue of resistance mutations.

---

## `Mykrobe`

Uses a panel of resistance markers to predict drug resistance from WGS data for *M. tuberculosis*
and *Staphylococcus aureus*.

The predictive power of `Mykrobe` likely to expand during this PhD due to CRyPTIC consortium.

---

## Chapter Aims

**Nanopore concordance with Illumina for phenotype prediction in _M. tuberculosis_**

Given the collection of SNPs and indels identified as being necessary for resistance to the 14 major drugs tested, we want to show that we can detect them as well with Nanopore data as we can with Illumina.

---

### Limitations of existing methods

-   Only two support Nanopore - `Mykrobe` and `TBProfiler` - small sample sizes (n<6) used to validate
-   The same panel produces different results between tools
-   `TBProfiler` uses pileup approach - poor indel power. Indels are important for resistance to some drugs
-   `Mykrobe` uses k-mer mapping - requires high coverage. K-mers considered in isolation
-   Both only genotype wrt known variants
-   CRyPTIC have shown flagging unknown mutations can lead to specificity and sensitivity acceptable for clinical usage (used by PHE)

---

## Solution = `Pandora`

Can use smaller k-mer size than `Mykrobe` as it takes context into account. Therefore it theoretically requires less coverage.

Can call novel variants (Chapter 1)

---

### Drug susceptibility prediction for *M. tuberculosis* using `pandora`

-   Produce gene-succinct PRG of variants known to cause resistance/susceptibility
-   Write a software program that takes `pandora` output and produces resistance predictions or flag for phenotyping
-   Validate on data from Chapter 2 against `Mykrobe` for Illumina and Nanopore


{{% /section %}}
