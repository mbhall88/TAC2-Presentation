+++
weight = 30
+++
{{% section %}}

# Presentation Overview

1.  What have I been doing for the last 12 months?
2.  Executive Summary
3.  **Thesis Plan**
4.  Publication Strategy

---

# Chapter 1

### Variant discovery in genome graphs

Develop algorithms and software for variant discovery using bacterial genome graphs, building on work of a previous student in the lab.

<progress class="chapter1-progress" max="100" value="80"></progress>
</br>80%

---

# Pan-genome

Bacterial genomes are incredibly diverse.

<img src="images/pangenome.jpg"  height="350" width="500" style="border: none;">

In an "open" pan-genome, such as *Salmonella enterica*, two individuals could share as little as 16% of their genes

---

## The single-reference problem

<img src="images/single-ref.png"  height="550" width="550" style="border: none;">

---

## Genome graphs

-   Uses a population reference graph (PRG) instead of a single, linear reference
-   PRG represents variation seen within a population
-   Two forms - local and pan-PRG

<img src="images/build-prg.png"  height="300" width="700" style="border: none;">

---

## Nanopore sequencing

<img src="images/nanopore.png"  height="400" width="600" style="border: none;">

Variant calling in its infancy (`medaka` and `nanopolish`), but no extensive benchmark has been completed

---

### Genome Graphs + Nanopore

`Pandora` - pan-genome inference and **genotyping** with long-noisy or short-accurate reads from Rachel Colquhoun.

<img src="images/pandora.png"  height="400" width="700" style="border: none;">

---

## `Pandora map`

Infer consensus sequence for a *single* sample and genotype with respect to this consensus sequence

<img src="images/pandora-no-denovo.png"  height="400" width="1000" style="border: none;">

---

## `Pandora compare`

Infer consensus sequence for a *collection* of samples and genotype with respect to this consensus sequence

<img src="images/pandora-compare.png"  height="200" width="1000" style="border: none;">

---

## Limitation

`Pandora` can only genotype based on variation within the graph

---

## Solution

The work in my first chapter outlines a method for removing this limitation and provides
an analysis of the gain in recall and precision by incorporating *de novo* variant discovery
into the `pandora` workflow.

---

## What have I done?

-   {{% fragment %}}Implement *de novo* variant discovery module within `pandora` (~850/~3200 lines of source/test code){{% /fragment %}}
-   {{% fragment %}}Built evaluation framework (~1250/~3500 lines of source/test code){{% /fragment %}}
-   {{% fragment %}}Built a `snakemake` pipeline of ~3500 lines of codes to orchestrate the entire evaluation and simulations.{{% /fragment %}}

---

# Variant discovery in a genome graph

---

### Step 1: Finding candidate regions

<img src="images/find-candidate.png"  height="500" width="1000" style="border: none;">

---

### Step 2: Enumerating paths through candidate regions

<img src="images/pandora-denovo.png"  height="520" width="1000" style="border: none;">

---

# Evaluation

---

## Simulated data

Aim to show that the addition of *de novo* discovery allows `pandora` to improve its
ability to discover and call variants correctly (precision/recall).

---

## Simulated data

-   100 local PRGs (genes)
-   Random path from each joined together into a genome
-   Introduce variants at a given rate
-   Simulate Nanopore reads from mutated genome
-   Run `pandora` with reads from mutated genome
-   Assess how many introduced variants were found

---

### Assessing variants

<img src="images/evaluation.png"  height="520" width="1000" style="border: none;">

---

## Simulation results

<img src="images/simulations.png"  height="550" width="1000" style="border: none;">

---

## Empirical data

-   The main focus of both `pandora` and *de novo* evaluation
-   Use `compare` routine to show the power of the reference-graph approach
-   4 *E. coli* samples from different phylogroups
-   Compare to other variant callers - `snippy`, `medaka`, `nanopolish` - using a variety of references

---

## Empirical data

Difficulty in evaluating four-way is "truth"

-   Align each pair of genomes with `nucmer` to get differences
-   Construct truth panel from these differences
-   Map truth panel to a panel of probes from `pandora` VCF
-   Calculate recall and precision for all pairs

---

## Preliminary Results

<img src="images/prelim-results.png"  height="550" width="1100" style="border: none;">

---

## Outstanding work

-   Completion of the four-way analysis
-   Direct integration of *de novo* variants back into PRG
-   100-way analysis to validate the limit in variant detection using single-reference approaches



{{% /section %}}
