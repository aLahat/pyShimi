# pyShimi
Small and fast Sashimi plotter. I am my main target users, so I'll add functionality as needed

Example use:
```
pyshimi -B1 [bams separated by comma]
        -B2 [bams separated by comma]
        -n1 [sample names separated by comma] 
        -n2 [sample names separated by comma] 
        -l1 mutant 
        -l2 corrected
        -c chr15:42409094-42409380 
        -p 1 
        -a hg38.ncbiRefSeq.gtf 
```
will result in:

![chr1542409094-42409380](https://user-images.githubusercontent.com/5287805/161256045-21d618ba-5d7b-4917-95b9-fbfb7f06de46.png)


You dont need to run two samples with multiple files, just one bam file (or multiple ones in one group) is enought:

```
pyshimi -B1 [bams separated by comma]
        -n1 [sample names separated by comma] 
        -l1 mutant 
        -c chr15:42409094-42409380 
        -p 1 
        -a hg38.ncbiRefSeq.gtf 
```
![chr1542409094-42409380](https://user-images.githubusercontent.com/5287805/161255783-bd46531c-cf4a-4189-a0b9-727bdabadc66.png)


## install 
Requires:
1) pysam
2) pandas
3) numpy
4) scipy
5) matplotlib

to install just put the pyshimi file somwhere in yor $PATH or just call it directly `python [path to file]/pyshimi -B1 ...`

## arguments

required:

**-B1 -B2 --bams1 --bams2**: Comma separated list of bam files (index files needed in the same directory) for the top plot (-B1/--bams1) or bottom plot (-B2/--bams2).

**-c --coords**: genomic coordinates in the `chr:start-end` format.

optional:

-n1 -n2 --names1 --names2: Comma separated list of names for the samples, one for each bam file. If none given will use bam file names instead. But the names might be too long for an elegant plot.

-l1 -l2 --label1 --label2: names for the group labels.

-a --annotations: path to gtf file to draw genes and exonic regions below the sashimi plot

-g --gene: gene name to use when plotting the bottom gene plot. will ignore other genes.

-m --minJunctCount: minimum number of junction counts to write the number for (they will still get lines), useful if too many junctions have a low number of counts and it makes it too hard to read the larger numbers.

-p --padding: left and right padding, multiplies by window size.

