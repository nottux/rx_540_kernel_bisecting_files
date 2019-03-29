# rx_540_kernel_bisecting_files
These files are used to bisecting RX 540 gpu kernel bug, also can be used or kernels older than 4.16 or so:
casper-rw.xz in this repository has all packages necessary to build kernels, you will still need to configure them on your host machine.

ubuntu 16.04.6 iso file with md5sum of `5416371cc0e990871746ddaac89f1a5e`, you can download it from: http://releases.ubuntu.com/16.04/ubuntu-16.04.6-desktop-amd64.iso

yumi: i have used yumi 2.0.6.0

First extract casper-rw.xz, a 4gb casper-rw file will be created (this is persistent storage that includes all necessary packages, but its only compatible with ubuntu 16.04.6)

Then install iso file using yumi in a windows environment (i have used virtualbox for that), create 4gb persistent storage and replace extracted casper-rw file with that

Boot into usb and build kernels without any problem :) !

For benchmarking, i am using Xonotic and The Talos Principle

P.S: please see actual issue page: https://bugzilla.kernel.org/show_bug.cgi?id=201077
