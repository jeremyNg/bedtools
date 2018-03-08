---
title: "Merging: Combining contiguous regions"
teaching: 10
exercises: 10
questions:
- "When do we use merge?"
objectives:
keypoints:


---


## Why do we need to merge? 
Sometimes, we obtain regions that show overlaps that can be collapsed
into a single contiguous interval. By merging these regions, we are
able to recover a single continuous region, which simplifies our
analysis. This is shown in the figure below. *Bedtools* enables this operation to be done using `merge`,
which we will discuss next. 

![Merging regions](../fig/merge.png)

## Using `merge`

> ## Requisite for merging
>
> Unlike `intersect` which does not strictly require the input to be
> sorted, `merge` requires that the input file provided is
> sorted. This can be done using a simple command `sort` that is
> provided in bash, as follows:  `sort -k1,1 -k2,2n foo.bed >
> foo.sort.bed` will sort the bed file and have it written to
> foo.sort.bed
{: .challenge}

As usual, one can find out the list of options using 

~~~
bedtools merge -h
~~~
{: .bash} 

> ## Try it
> 
> Using `merge`, combine the intervals found in the exons file to
> obtain contiguous regions. 
>
{: .bash}

If 2 features are some distance apart, `merge` will by default not
combine them together (since there is no overlap). However, we can use
the `-d` option to merge features that are less than `d` bases apart. 

## Advanced reporting options
`merge` provides a way to combine overlapping regions to obtain larger
contiguous regions. By default, we will obtain a new *bed* file
containing the new intervals. 

However, we might be interested in knowing how many intervals were
merged to give us a new interval. This can be done using `-c` and
`-o`. The `-c` indicates which column we will like to summarize, while
`-o` enables us to specify operations that we will like to perform on
the indicated column. For example

~~~
bedtools merge -i exons.bed -c 1 -o count
~~~
{: .bash}

will count how many features were merged into a new interval using
data from column 1 (the chromosome number). In theory, you can also
use any other columns as well for the same operation. 

> ## Try it
>
> Column 4 contains the names of exons. We can use the `collapse`
> operation to combine the names of different exons that were
> merged. How would you do this using `merge`? 
>
{: .bash}
