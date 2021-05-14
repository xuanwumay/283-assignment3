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

create a test file

run test

* In the outer VM
run the “dmesg” command to show the output

CPUID(0x4FFFFFFE), exit number=0, number of exits=14116 
CPUID(0x4FFFFFFE), exit number=1, number of exits=293243
CPUID(0x4FFFFFFE), exit number=2, number of exits=0 
CPUID(0x4FFFFFFE), exit number=3, number of exits=0 
CPUID(0x4FFFFFFE), exit number=4, number of exits=0 
CPUID(0x4FFFFFFE), exit number=5, number of exits=0 
CPUID(0x4FFFFFFE), exit number=6, number of exits=0 
CPUID(0x4FFFFFFE), exit number=7, number of exits=244342
CPUID(0x4FFFFFFE), exit number=8, number of exits=0 
CPUID(0x4FFFFFFE), exit number=9, number of exits=0 
CPUID(0x4FFFFFFE), exit number=10, number of exits=34479
CPUID(0x4FFFFFFE), exit number=11, number of exits=0 
CPUID(0x4FFFFFFE), exit number=12, number of exits=101196
CPUID(0x4FFFFFFE), exit number=13, number of exits=0 
CPUID(0x4FFFFFFE), exit number=14, number of exits=0 
CPUID(0x4FFFFFFE), exit number=15, number of exits=0 
CPUID(0x4FFFFFFE), exit number=16, number of exits=0 
CPUID(0x4FFFFFFE), exit number=17, number of exits=0 
CPUID(0x4FFFFFFE), exit number=18, number of exits=0 
CPUID(0x4FFFFFFE), exit number=19, number of exits=0 
CPUID(0x4FFFFFFE), exit number=20, number of exits=0 
CPUID(0x4FFFFFFE), exit number=21, number of exits=0 
CPUID(0x4FFFFFFE), exit number=22, number of exits=0 
CPUID(0x4FFFFFFE), exit number=23, number of exits=0 
CPUID(0x4FFFFFFE), exit number=24, number of exits=0 
CPUID(0x4FFFFFFE), exit number=25, number of exits=0 
CPUID(0x4FFFFFFE), exit number=26, number of exits=0 
CPUID(0x4FFFFFFE), exit number=27, number of exits=0 
CPUID(0x4FFFFFFE), exit number=28, number of exits=98809
CPUID(0x4FFFFFFE), exit number=29, number of exits=4 
CPUID(0x4FFFFFFE), exit number=30, number of exits=18282 
CPUID(0x4FFFFFFE), exit number=31, number of exits=291
CPUID(0x4FFFFFFE), exit number=32, number of exits=57917
CPUID(0x4FFFFFFE), exit number=33, number of exits=0 
CPUID(0x4FFFFFFE), exit number=34, number of exits=0 
CPUID(0x4FFFFFFE), exit number=35, number of exits=0 
CPUID(0x4FFFFFFE), exit number=36, number of exits=0 
CPUID(0x4FFFFFFE), exit number=37, number of exits=0 
CPUID(0x4FFFFFFE), exit number=38, number of exits=0 
CPUID(0x4FFFFFFE), exit number=39, number of exits=0 
CPUID(0x4FFFFFFE), exit number=40, number of exits=38324 
CPUID(0x4FFFFFFE), exit number=41, number of exits=0 
CPUID(0x4FFFFFFE), exit number=42, number of exits=0 
CPUID(0x4FFFFFFE), exit number=43, number of exits=0 
CPUID(0x4FFFFFFE), exit number=44, number of exits=0 
CPUID(0x4FFFFFFE), exit number=45, number of exits=0 
CPUID(0x4FFFFFFE), exit number=46, number of exits=12 
CPUID(0x4FFFFFFE), exit number=47, number of exits=4 
CPUID(0x4FFFFFFE), exit number=48, number of exits=1258701 
CPUID(0x4FFFFFFE), exit number=49, number of exits=152047 
CPUID(0x4FFFFFFE), exit number=50, number of exits=0 
CPUID(0x4FFFFFFE), exit number=51, number of exits=0 
CPUID(0x4FFFFFFE), exit number=52, number of exits=0 
CPUID(0x4FFFFFFE), exit number=53, number of exits=0 
CPUID(0x4FFFFFFE), exit number=54, number of exits=6 
CPUID(0x4FFFFFFE), exit number=55, number of exits=6 
CPUID(0x4FFFFFFE), exit number=56, number of exits=0 
CPUID(0x4FFFFFFE), exit number=57, number of exits=0 
CPUID(0x4FFFFFFE), exit number=58, number of exits=0 
CPUID(0x4FFFFFFE), exit number=59, number of exits=0 
CPUID(0x4FFFFFFE), exit number=60, number of exits=0 
CPUID(0x4FFFFFFE), exit number=61, number of exits=0 
CPUID(0x4FFFFFFE), exit number=62, number of exits=0 
CPUID(0x4FFFFFFE), exit number=63, number of exits=0 
CPUID(0x4FFFFFFE), exit number=64, number of exits=0 
CPUID(0x4FFFFFFE), exit number=65, number of exits=0 
CPUID(0x4FFFFFFE), exit number=66, number of exits=0 
CPUID(0x4FFFFFFE), exit number=67, number of exits=0 
CPUID(0x4FFFFFFE), exit number=68, number of exits=0 

## Questions
3. Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there more exits performed during certain VM operations? Approximately how many exits does a full VM boot entail?
By observation, the number of exists didn't increase. 
A full VM boot entail about 18000 exits. 

4. Of the exit types defined in the SDM, which are the most frequent? Least?

Most frequent exit:

Least frequent exit:

