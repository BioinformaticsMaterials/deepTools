Visualization
==============

The modules for visualizing scores contained in [bigWig][] files are separated into a tool that calculates the values
(_computeMatrix_) and two tools that contain many, many options to fine-tune the plot (_heatmapper_ and _profiler_).

![flowChartII](https://raw.github.com/fidelram/deepTools/manual/examples/flowChart_computeMatrixetc.png "Relationship between computeMatrix, heatmapper and profiler")

## Table of content

  * [computeMatrix](#computeMatrix)
  * [heatmapper](#heatmapper)
  * [profiler](#profiler)

<a name="computeMatrix"/>
## computeMatrix
This tool summarizes and prepares an intermediary file containing
scores associated with genomic regions that can be used afterwards to
plot a heatmap or a profile. Typically, these genomic regions are
genes, but any other regions defined in a BED or INTERVAL format can
be used. This tool can also be used to filter and sort regions
according to their score.

## Output files
obligatory: zipped matrix of values to be used with _heatmapper_ and/or _profiler_

optional output:
BED-file of the regions sorted according to the calculated values
list of average values per genomic bin
matrix of values per genomic bin per genomic interval


<a name="heatmapper"/>
## heatmapper
The heatmapper visualizes scores associated with genomic regions, for
example ChIP enrichment values around the TSS of genes. Those values
can be visualized individually along each of the regions provided by
the user in INTERVAL or BED format. In addition to the heatmap, an
average profile plot is plotted on top of the heatmap (can be turned
off by the user; it can also be generated separately by the tool
profiler). We implemented vast optional parameters and we encourage
you to play around with the min/max values displayed in the heatmap as
well as with the different coloring options. If you would like to plot
heatmaps for different groups of genomic regions individually,
e.g. one plot per chromosome, simply supply each group as an
individual BED file.


<a name="profiler"/>
## profiler
This tool creates a profile plot for a score associated to genomic regions.
Typically, these regions are genes, but any other regions defined in a BED or
INTERVAL format will work. A preprocessed matrix generated by the tool
computeMatrix is required.


-----------------------------------------------------------------------------------
[BAM]: https://docs.google.com/document/d/1Iv9QnuRYWCtV_UCi4xoXxEfmSZYQNyYJPNsFHnvv9C0/edit?usp=sharing "binary version of a SAM file; contains all information about aligned reads"
[SAM]: https://docs.google.com/document/d/1Iv9QnuRYWCtV_UCi4xoXxEfmSZYQNyYJPNsFHnvv9C0/edit?usp=sharing "text file containing all information about aligned reads"
[bigWig]: https://docs.google.com/document/d/1Iv9QnuRYWCtV_UCi4xoXxEfmSZYQNyYJPNsFHnvv9C0/edit?usp=sharing "binary version of a bedGraph file; contains genomic intervals and corresponding scores, e.g. average read numbers per 50 bp"
[bedGraph]: https://docs.google.com/document/d/1Iv9QnuRYWCtV_UCi4xoXxEfmSZYQNyYJPNsFHnvv9C0/edit?usp=sharing "text file that contains genomic intervals and corresponding scores, e.g. average read numbers per 50 bp"
[FASTQ]: https://docs.google.com/document/d/1Iv9QnuRYWCtV_UCi4xoXxEfmSZYQNyYJPNsFHnvv9C0/edit?usp=sharing "text file of raw reads (almost straight out of the sequencer)"
### References
[Benjamini and Speed]: http://nar.oxfordjournals.org/content/40/10/e72 "Nucleic Acids Research (2012)"
[Diaz et al.]: http://www.degruyter.com/view/j/sagmb.2012.11.issue-3/1544-6115.1750/1544-6115.1750.xml "Stat. Appl. Gen. Mol. Biol. (2012)"


This tool is developed by the [Bioinformatics Facility](http://www1.ie-freiburg.mpg.de/bioinformaticsfac) at the [Max Planck Institute for Immunobiology and Epigenetics, Freiburg](http://www1.ie-freiburg.mpg.de/).