# tprFinder
tprFinder identifies transcription pause regions (TPRs) from PRO-Cap data.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

Please download and put TPR_F_V2 and TPR_F programs under one folder.
```
Please provide these details to run TSR finder properly:
a) input file to run such as /home/<user>/<folder name>/mapped-fragments.bed.
   Please provide the full path of the input file.
   <user> refers to username and <folder name> is where the file is.
b) TPR window size is an integer such as 20
c) TPR read depth is an integer such as 20
d) TPR average read length is an integer such as 30
e) Fragment size is an integer such as 600
f) chromosome size file path and name such as ###.chrom.sizes
```
Note: tprFinderv2 runs on Python 2.7+ version. Please refer to https://github.com/P-TEFb/tsrFinderv2 for description on the program features and details.The features of this program work the same way as the tsrFinderv2, instead it evaluates every TPR window across the genome for the sum of 3' reads (transcription pause sites) and the average read length.
```
Example run of TPR finder: python TPR_F_V2 mapped-fragments.bed 20 20 30 600 ###.chrom.sizes
```
