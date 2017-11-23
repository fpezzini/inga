GENERAL
1 - Filtering the set of NGS reads to remove sources of error/bias
2 - Aligning the reads to a reference genome
3 - Using an algorithm, either based on a statistical model or some heuristics, to predict the likelihood of variation at each locus, based on the quality scores and allele counts of the aligned reads at that locus
4 - Filtering the predicted results, often based on metrics relevant to the application
5 - SNP annotation to predict the functional effect of each variation.
The usual output of these procedures is a VCF file.