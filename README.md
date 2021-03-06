# 283-assignment3
## Team members
Jinxuan Hu (013728936) Xuan Shi(013856401)
## Contribution of Team Members
* Jinxuan Hu ---  modify the file cpuid.c, create the test file, update the documentation, create a user-mode program that performs various CPUID instructions to test the assignment
* Xuan Shi ----  modify the file vmx.c, compile the test file and create the documentation, create a user-mode program that performs various CPUID instructions to test the assignment

## steps: 
We did this assignment based on the environment of assignment-2 and followed the same steps of environment setup.
https://github.com/xuanwumay/283-assignment2

## modification of kernel code
Updated vmx.c to increment the counters for specific exit reasons.
arch_atomic_inc(&exit_counters[exit_reason.basic])

Updated cpuid.c to create new CPUID leaf 0x4FFFFFFE
exit_counters: array to record the number of exits for specific reasons.

* In the outer VM:
Remove the kvm module by: $sudo rmmod kvm
remove the kvm_intel module by: $ sudo rmmod kvm_intel
Compile the modified kernel code

* In inner VM:

install cpuid package

create a test file and run test file to get the output:
https://github.com/xuanwumay/283-assignment3/blob/main/output-a3.txt


## Questions
3. Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there more exits performed during certain VM operations? Approximately how many exits does a full VM boot entail?

By observation, the number of exists is increasing, but it doesn't increase at a stable rate.

A full VM boot entail about 230000 exits. 

4. Of the exit types defined in the SDM, which are the most frequent? Least?

Most frequent exit:
* Exit number: 48 EPT violation
* Exit number: 32 WRMSR

Least frequent exit:
* Exit number: 29 MOV DR
* Exit number: 54 WBINVD
* Exit number: 55 XSEBV

