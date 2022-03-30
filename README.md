# pyShimi
Small and fast Sashimi plotter. I am my main target users, so I'll add functionality as needed

Example use:
```
pyshimi -B1 ../port/results/majiq/bams/RPE.mutant.1a3.1.bam 
        -B2 ../port/results/majiq/bams/RPE.mutant.1a3.2.bam,../port/results/majiq/bams/RPE.mutant.1a3.1.bam  
        -n1 RPE.Mutant.1a3.1 
        -n2 2,RPE.Mutant. 
        -l1 mutant 
        -l2 corrected
        -c chr15:42409094-42409380 
        -p 1 
        -a hg38.ncbiRefSeq.gtf 
```
will result in:
![chr1542409094-42409380](https://user-images.githubusercontent.com/5287805/160927118-8e4ef76f-e282-428c-966c-c4b0845c6097.png)

Requires:
1) pysam
2) pandas
3) numpy
4) scipy
5) matplotlib

to install just put the pyshimi file somwhere in yor $PATH or just call it directly `python [path to file]/pyshimi -B1 ...`

