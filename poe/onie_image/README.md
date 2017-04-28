Following the instruction to update ONIE to the AG6248C:

Installing the ONIE binaries

============================

Step 1 -- Put the ONIE files on a TFTP server

---------------------------------------------

The following directions assume the files are on the root of the TFTP

server. (TFTP server ip address is 192.168.1.5)

Step 2 -- Install ONIE kernel (20170416-onie-delta_ag6248c-poe-r0.bin)

-----------------------------------------------

Copying the image down using TFTP and flash to the NAND flash::

  

  Get into loader cli, run the following commands.

  => setenv ipaddr 192.168.1.1

  => setenv serverip 192.168.1.5

  => tftp 20170416-onie-delta_ag6248c-poe-r0.bin && nand erase 0 0xa00000 && nand write $loadaddr 0 $filesize

  => nand read $loadaddr onie && nand write $loadaddr onie2

------------------

