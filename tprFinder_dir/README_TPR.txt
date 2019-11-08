tprFinder identifies transcription pause regions (TPRs) from PRO-Cap and similar nascent transcript sequencing datasets.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

Usage:
tprFinder runs on Python .7+. The tprFinder evaluates every TPR window across the genome for the
sum of 3' reads (transcription pause sites) and the average read length. tprFinder checks for errors
in a user's input. If errors are found the tprFinder program displays the usage example and parameter
description prior to exiting the run. 

tprFinder syntax:

tprFinder <mapped-fragments.bed file> <TPR window size> <TPR read depth> <minimum average read length> <maximum fragment size> <chromosome sizes file>

Maintain the program files under the tprFinder_dir folder.

Parameter description:

mapped-fragments.bed file: A mapped fragment bed file can be generated from alignment files in sam
                           format using samtools and bedtools.

TPR window size:           A desired size of the TPR window (an integer). We found TPRs are usually
                           20bp in width and are often clustered. This parameter can be increased or
			   decreased to find longer or shorter sized TPRs.

TPR read depth:            The minimum amount of reads per TPR (an integer). This determination of
                           this parameter can vary depending on sequencing depth and the amount of
			   background signal in your dataset.

minimum average read length: The desired minimum average read length (an integer) allows elimination
                             of TPRs formed exclusively by sequencing artifacts and hard to map
			     fragments. We observed TPRs tend to have an avearage read length of
			     atleast 30nt.

maximum fragment size:     This parameter (an integer) allows exclusion of excessively long PRO-Seq
                           reads. 

chromosome sizes file:     tprFinder requires a chromosome sizes file. This file can be obtained
                           using [fetchChromSizes](http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/)
			   utility.

Output:

                           The final output is a comprehensive tab-delimited text file which contains
			   information about both FW and RV strand TPR boundaries, sum of TPR read lengths,
			   # of TPR reads, strand, the MaxTPS position, # of MaxTPS reads, the average TPS
			   position, MaxTPS-averageTPS, and the standard deviation of the average TPS position.
			   