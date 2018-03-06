---
title: "Introducing genome arithmetic"
teaching: 5
exercises: 0
questions:
- "What is a genome arithmetic?"
objectives:
keypoints:

---


## What is genome arithmetic?

Genome arithmetic is the application of *set theory* on the genome. Recall that given 2 sets (**A** and **B**), we can perform operations such as finding the *intersect* (found in both **A** and *B**), the *complement* (not found in the set), the *union* (found in **A OR B**), as well as count the number of elements. Similarly, these operations can be performed given 2 sets of genomic coordinates.

There are various tools that have been developed for genome arithmetic. One of the most commonly used tool is *bedtools*, which is a stand-alone command line interface set of programs. *Bedtools* has found widespread use due to the following reasons:

1. The ease of use,
2. Speed of operations,
3. Ability to deal with a wide range of genomic file types (including *BAM*, *BED* and *VCF*), and;
4. Suitability for use in complex pipelines by stringing together operations.

Today's class focuses on going through some of the most commonly used programs in *bedtools* encountered in the analysis of NGS data. 




