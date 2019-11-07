# tprFinder
tprFinder identifies transcription pause regions (TPRs) from PRO-Cap data.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
tprFinder runs on Python v2.7+. The features of this program work the same way as the tsrFinderv2, instead it evaluates every TPR window across the genome for the sum of 3' reads (transcription pause sites) and the average read length. The tprFinderI is an interface program that runs the actual tprFinder program. It checks for errors in a user's input. If errors are found the tprFinderI program displays the usage example and parameter description prior to exiting the run. 

Both tprFinder and tprFinderI are intended to be run via a Python v2.7+ interpreter installed on your desired operating system of choice such as Windows, Mac or Linux. The tprFinderI expects the following syntax on a linux command-line interface:

```
python tprFinderI <mapped-fragments.bed file> <TPR window size> <TPR read depth> <minimum average read length> <maximum fragment size> <chromosome sizes file>
```

### Parameter description:
```
mapped-fragments.bed file: A mapped fragment bed file can be generated from 
                           alignment files in sam format using samtools and bedtools.

TPR window size:           A desired size of the TPR window. We found TPRs are usually 
                           40bp in width and are often clustered. This parameter can be 
                           increased or decreased to find longer or shorter sized TPRs.

TPR read depth:            The minimum amount of reads per TPR. This determination of 
                           this parameter can vary depending on sequencing depth and the 
                           amount of background signal in your dataset.

minimum average read length: The desired minimum average read length allows 
                           elimination of TPRs formed exclusively by sequencing artifacts 
                           and hard to map fragments. We observed TPRs tend to have an 
                           avearage read length of atleast 30bp.

maximum fragment size:     This parameter allows exclusion of excessively long PRO-Seq reads. 

chromosome sizes file:     tprFinder requires a chromosome sizes file. This file can be obtained 
                           using [fetchChromSizes](http://hgdownload.soe.ucsc.edu/admin/exe/linux.x86_64/) 
                           utility.
```

Note: Download and put tprFinderI and tprFinder programs under one folder.

### Output:

