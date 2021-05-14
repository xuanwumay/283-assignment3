# 283-assignment3

## Contribution of Team Members
Jinxuan Hu:
Modified the code in vmx.c
ran testing
Updated the documentation.
Xuan Shi:
Modified the code in cpuid.c
Created the documentation.
run testing

## steps: 
We did this assignment based on the environment of assignment-2 and followed the same steps of environment setup.
https://github.com/xuanwumay/283-assignment2

## modification of kernel code
Updated vmx.c to keep track of exit counts by exit reason. Updated cpuid.c to support new CPUID leaf 0x4FFFFFFE

In the outer VM, do the following:

Remove the kvm and kvm_intel modules

Compile the updated kernel code

In inner VM, installed cpuid package
In the terminal run the commands to test each leaf
In the outer VM , run the command “dmesg” to view the print statements

## Questions
3. Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there more exits performed during certain VM operations? Approximately how many exits does a full VM boot entail?


4. Of the exit types defined in the SDM, which are the most frequent? Least?


