6 - BCFtools
BCFtools is a set of utilities that manipulate variant calls in the Variant Call Format (VCF) and its binary counterpart BCF. See bcftools call for variant calling from the output of the samtools mpileup command.
call: SNP/indel calling
-c, --consensus-caller the original samtools/bcftools calling method (conflicts with -m)
-g, --gvcf INT output also gVCF blocks of homozygous REF calls. The parameter INT is the minimum per-sample depth required to include a site in the non-variant block.