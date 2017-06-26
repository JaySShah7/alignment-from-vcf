# alignment-from-vcf
Make fasta alignments from vcf files, written by Stephan Kamrad (stephan.kamrad@crick.ac.uk)

This script requires biopython (http://biopython.org/wiki/Biopython) and pysam (http://pysam.readthedocs.io/en/latest/) installed. I have only used and tested this in Linux environments.

The script will generate a sequence alignment for multiple individuals using the reference genome and a vcf file.
I personally work with S. pombe (which conveniently is haploid) but this script should work for higher ploidy as well. In that case, one sequence per individual and genome copy is generated. This obviously only makes sense if your variants are phased. The heavy lifting (parsing of the vcf) is done by pysam, so it all depends on whether or not pysam can handle your vcf correctly. 

I have written this script for my own use, but have not tested in systematically in a range of scenarios, so it comes with no warranty. Please validate if the output is as expected and raise any issues on github (https://github.com/Bahler-Lab/alignment-from-vcf/).

Usage:
The script requires the following 7 arguements (in the given order):
- path to the reference genome in fasta format
- path to the vcf
- name of the contig that contains the region of interest
- start of the region
- end of the region
- ploidy (This script obviously only makes sense if variants are phased. One sequence per genome copy will be generated)
- path to the output file. This will be in fasta format.

An 8th arguement can optionally be supplied and should specify the path to a file containing a list of individuals to be included (one per line). If not supplied, all individuals will be used.
