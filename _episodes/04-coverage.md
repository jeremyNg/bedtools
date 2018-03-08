---
title: "Coverage -- How many reads map to a given region?"
teaching: 5
exercises: 0
questions:
objectives:
keypoints:

---


## Using `genomecov`
Following alignment, we are faced with genomic coordinates. However, it is often of interest for us to find out how many reads are mapping to each feature of interest.  This is done using the `genomecov` command. By default, a histogram of coverage for the genome file is returned. This is extremely useful for visualization. For more information about the output of `genomecov`, please refer to (http://bedtools.readthedocs.io/en/latest/content/tools/genomecov.html). However, if we are interested in how many reads map to each base, we can use the `-d` option in `genomecov`. Note that this can take quite a long time for larger genomes. 

A useful option is the `-bg` option, which returns coverage in a *bedgraph* format. This differs from `-d` as it merges consecutive bases with the same coverage in a single line with the start and end of the region. The `-bga` option does the same thing, but unlike `-bg`, it also returns consecutive regions where there is zero coverage. The *bedgraph* format is often used for visualization of NGS data. 