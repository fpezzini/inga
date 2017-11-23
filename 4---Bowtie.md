4 - Bowtie
C/C++

Bowtie 2 is an ultrafast and memory-efficient tool for aligning
sequencing reads to long reference sequences. It is particularly good at
aligning reads of about 50 up to 100s or 1,000s of characters to
relatively long (e.g. mammalian) genomes. Bowtie 2 indexes the genome
with an FM Index (based on the Burrows-Wheeler Transform or BWT) to keep
its memory footprint small: for the human genome, its memory footprint
is typically around 3.2 gigabytes of RAM. Bowtie 2 supports gapped,
local, and paired-end alignment modes. Multiple processors can be used
simultaneously to achieve greater alignment speed. Cufflinks: a tool for
transcriptome assembly and isoform quantitiation from Bowtie 2 outputs
alignments in SAM format, enabling interoperation with a large number of
other tools (e.g. SAMtools, GATK) that use SAM. Bowtie 2 is distributed
under the GPLv3 license, and it runs on the command line under Windows,
Mac OS X and Linux.

THE bowtie2 ALIGNER

bowtie2 takes a Bowtie 2 index and a set of sequencing read files and
outputs a set of alignments in SAM format.

"Alignment" is the process by which we discover how and where the read
sequences are similar to the reference sequence. An "alignment" is a
result from this process, specifically: an alignment is a way of "lining
up" some or all of the characters in the read with some characters from
the reference in a way that reveals how they're similar. For example:

      Read:      GACTGGGCGATCTCGACTTCG
                 |||||  |||||||||| |||
      Reference: GACTG--CGATCTCGACATCG

Where dash symbols represent gaps and vertical bars show where aligned
characters match.

End-to-end alignment versus local alignment

By default, Bowtie 2 performs end-to-end read alignment. That is, it
searches for alignments involving all of the read characters. This is
also called an "untrimmed" or "unclipped" alignment.

When the --local option is specified, Bowtie 2 performs local read
alignment. In this mode, Bowtie 2 might "trim" or "clip" some read
characters from one or both ends of the alignment if doing so maximizes
the alignment score.

Scores: higher = more similar

An alignment score quantifies how similar the read sequence is to the
reference sequence aligned to. The higher the score, the more similar
they are. A score is calculated by subtracting penalties for each
difference (mismatch, gap, etc.) and, in local alignment mode, adding
bonuses for each match.

--score-min <func>
Sets a function governing the minimum alignment score needed for an alignment to be considered "valid" (i.e. good enough to report). This is a function of read length. For instance, specifying L,0,-0.6 sets the minimum-score function f to f(x) = 0 + -0.6 * x, where x is the read length. See also: setting function options. The default in --end-to-end mode is L,-0.6,-0.6 and the default in --local mode is G,20,8.