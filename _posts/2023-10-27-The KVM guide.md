---
layout: post
title: "The kVM Guide"
date: 2023-10-27
---

### **About & Why ?**

> KVM [Kernel-based Virtual Machine] is the best technology used these days for virtualization. Most of the 
Server managers use KVM in their virtualization. pretty much the world runs on Virtualization.

> KVM hypervisor enables full virtualization capabilities. It gives each VM a standard service of 
the physical system, including the Virtual Basic Input Output System (Bios) and virtual hardware 
like network cards, processors, memory, and much more. As a result, every VM completely mimics a 
physical machine also, As part of the Linux kernel source code, KVM benefits from rigorous 
development and testing processes, as well as continuous security patching. 

### **Configuring KVM for Linux**

>**Checking Virtualization Support for your hardware**


``` term
egrep -c '(vmx|svm)' /proc/cpuinfo
```
If the above command returns a value of 0 in your machine, your processor cannot run KVM.

**Note** : If the output is zero then go to bios settings and enable VT-x (Virtualization Technology Extension) for Intel processor and AMD-V for AMD processor.

``` term
grep -E --color '(vmx|svm)' /proc/cpuinfo
```
Using this command you will get information about your CPU [Intel or AMD] If the red color output text is VMX then it 
is Intel whereas SVM means AMD.


### **Install QEMU / KVM & Libvirt packages `Debian`**

```term
sudo apt install qemu-kvm qemu-utils python3 python3-pip libvirt-clients libvirt-daemon-system bridge-utils virtinst libvirt-daemon virt-manager spice-vdagent


```
**Start & Enable KVM service**
``` term
sudo systemctl enable --now libvirtd
```

**Check Libvirtd service is started**

``` term
sudo systemctl status libvirtd.service
```
>**Reboot !**

**If you want you can configure [VIRSH](https://wiki.debian.org/KVM) [VIRSH is a command to directly interact with our VMs from terminal].**

### **Install QEMU / KVM & Libvirt packages `Arch`**

```term
sudo pacman -S qemu-system-x86 qemu-system-x86-firmware libvirt bridge-utils virt-manager

```

`Refer wiki` : 
[Whonix](https://www.whonix.org/wiki/KVM#Debian)
| [QEMU](https://wiki.archlinux.org/index.php/QEMU)
| [libvirt](https://wiki.archlinux.org/index.php/Libvirt)
| [libvirt clients](https://wiki.archlinux.org/index.php/Libvirt#Client)


### **Set user Group** (Arch/Debian)

Add user to `libvirt` Group:

```term
sudo adduser $USER libvirt 
```

Add user to `libvirt-qemu`

```
sudo adduser $USER libvirt-qemu

```

### **Systemctl Service libvirtd (Arch)**

Start the `libvirtd.service` service:

```term
sudo systemctl start libvirtd.service
```

Enable `libvirt.service` service at boot:

```term
sudo systemctl enable libvirtd.service
```

Start `virt-manager`:

```term
virt-manager
```

>**Reboot** !

[checkout win 10 install in KVM](https://asteroidex.com/Win-10-vm-in-linux)


[manipulating qcow2](https://www.whonix.org/wiki/KVM#Manipulating_QCOW2_Images)

**quick note** :
operating system may end up writing sensitive information in RAM to swap space on your disk, so using a virtual 
machine for anonymity is not always the best idea!
