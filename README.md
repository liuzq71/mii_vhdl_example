# mii_vhdl_example

VHDL implementation of MII transceiver.  This is in the form of a Xilinx Vivado Project.  The target for this project is the Lattice iCE5LP4K FPGA.  I'm using Vivado for design and testing as I prefer it to the Lattice toolchain.

## Description

This is an implementation of a simple MII transceiver.  Currently this only includes the transmitter and receiver.
To use this, connect the data input and output to FIFOs.  This is a work in progress and I'll probably add FIFO's later.  For those
unfamiliar with MII, there is a short tutorial on the [Wiki](https://github.com/myersw12/mii_vhdl_example/wiki).

## Inspiration

I'm currently looking at MII to SPI conversion and decided to look into doing the conversion on an FPGA.  There are not many commercially available ICs that do this.
I started with this [page](http://www.ece.ualberta.ca/~elliott/ee552/studentAppNotes/2001_w/interfacing/ethernet_mii/eth_mii.html) and its accompanying examples.

## Simulation

The transceiver is simulated in /vhdl_mii.srcs/sim_1/imports/new/mii_testbench.vhd.  The testbench simulates transmission and reception of an ethernet frame.  Helpful resources for understanding the
simulation are in /extras.  The following are included:
* send_ethernet.py - Sends the packet used in the simulation over eth0.  This is useful if you want to see the packet in real life.  You'll need a Oscilloscope to see it.
* ethernet_crc.py - Generates the ethernet frame CRC for the packet in the simulation.  Unless you view this packet on the MII interface using and Oscilloscope, you won't see this CRC.

If you are not familiar with the Vivado project structure, here are links to the [top level component](/vhdl_mii.srcs/sources_1/imports/mii_vhdl_example/ethernet.vhd)
and [testbench](/vhdl_mii.srcs/sim_1/imports/new/mii_testbench.vhd) source.
