1 - Folder with 4 files

170615_M01270_0325_000000000-B5K92_1_TP-D7-007_TP-D5-006_1.fastq.gz
170615_M01270_0325_000000000-B5K92_1_TP-D7-007_TP-D5-006_1.fastq.gz.md5
170615_M01270_0325_000000000-B5K92_1_TP-D7-007_TP-D5-006_2.fastq.gz
170615_M01270_0325_000000000-B5K92_1_TP-D7-007_TP-D5-006_2.fastq.gz.md5

##count the word in 2nd line
head -n 2 KB4_1.sanfastq | tail -n 1 | wc
printf "%s" `head -n 2 KB4_1.sanfastq | tail -n 1` | wc

## count the number of reads
grep -w "@HWI" FP100_1.sanfastq | wc -l

#make a list os accessions:

ls -d */ | sed 's/\///g' > accessions

use script renaming.sh to extract files:

while read f; do ./renaming.sh "$f" ; done < accessions