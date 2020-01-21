#Run the following command in the terminal to run the toy example
python ../alignment-from-vcf.py toy_reference.fa toy.vcf.gz chr1 1 10 2 toy_out.fasta

#You can modify the vcf, but you then have to run the following commands for the changes to have an effect
bgzip -c toy.vcf > toy.vcf.gz
tabix -p vcf toy.vcf.gz

