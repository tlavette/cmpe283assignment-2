# cmpe283assignment-2

# Project Scope

Prerequisite:  Completion of Assignment #1
This assignment is designed to demonstrate modifying CPU Identification (CPUID) processor instruction behavior inside the KVM hypervisor.   This instruction used by system utilities and operating systems for capturing detailed information about the CPU.

# Team Members
Puja Kumari (017460157)

Tonja Jean

The following was the overall effort dynamic placed in the completion of this assignment.  We met and collaborated on the strategy and each one of us had point lead for the bulleted items, however, we spent much time collaborating via Zoom in peer configuration and code triage.  We also spent time engaging in knowledge transfer as each item had slightly different requirements and needs for ultimate completion.

**Tonja Jean**
* Confirmed the VM module and kernel were successfully running.  
* Performed a collaborative review of the requirements to determine the resources needed to complete for assignment-2.
* Installed build-essentials and cpuid package in nested VM.
* Performed code update of CPUID leaf node %eax=0x4FFFFFFF
* Performed final code refactoring and compilation.
* Test and debug Collaboration
* Collect and compile documentation.

**Puja Kumari**
* Confirmed the VM module and kernel were successfully running.  
* Performed a collaborative review of the requirements to determine the resources needed to complete for assignment-2.
*	Installed the nested Ubuntu VM inside the outer VM
* As part of nested VM installation, installed other packages like Virt-Manger, and downloaded OS iso
images.
* Performed code update of CPUID leaf node %eax=0x4FFFFFFE
* Created and compiled test program
* Collect and compile documentation.


# Test Working Kernel - Confirm Environment

lsmod | grep kvm

lsmod | grep kvm_intel

Remove KVM modules actively loaded.

rmmod kvm_intel and rmmod kvm

modprobe kvm

mod probe kvm_intel

![image](https://github.com/tlavette/cmpe283assignment-2/assets/33330609/0d2826ab-5c87-44fe-af36-f1000ffbb1ef)



# Update Kernel Code Files
Update kvm hypervisor files:  cupid.c and vmx.c files

Modified kvm_emulate_cpuid code for CPUID exit handling. 

![image](https://github.com/tlavette/cmpe283assignment-2/assets/33330609/9d56770f-4750-48f7-870f-e771c9c5b0cd)


Modified vmx.c code vmx_handle_exit to increment the total number of exits.

![image](https://github.com/tlavette/cmpe283assignment-2/assets/33330609/a4a9f4bb-cc2c-4ba8-8cd5-40fe4e1549a9)


# Build kernel modules

sudo make modules -j 8 modules

make INSTALL_MOD_STRIP=1 && make install

# Create L2 VM and Test CPUID Assignment

sudo apt-get install virt-manager 

sudo apt-get install libvirt-bin libvert-doc

sudo apt-get install gemu-system

sudo virt-manager

Reviewed GCP documentation for creating nested virtualization.

Downloaded GEMU-compatible OS image

Created and compiled code to test inside of the L2 VM



# Perform CPUID Confirmation and Test



**CPUID leaf node %eax=0x4FFFFFFF**

Results: 

Issues:

**CPUID leaf node %eax=0x4FFFFFFE**

Results:

Issues:

