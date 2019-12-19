# trace32-dbsc4-rcar3-init
trace32 scripts to generate and initialize the rcar3 dbsc4 ddr4 controller

# dram_init_generate.cmm
You need to have a working Arm Trusted Firmware bl2 elf/binary etc. for the Rcar3 Board. Run this script. The script will run and track all mmio accesses through conditional breakpoins. After the DDR4 is initialized the script will generate two files mem_access_gen.c and mem_access_gen.cmm. The first one is for future uses in a fast DDR initialization through a bare metal app. The second is used for as an input file to the **table_based_ddr_init.cmm** script, and contains the Debugger commands to do the initialisation


# table_based_ddr_init.cmm

Run this script after generating the **mem_access_gen.cmm** with **dram_init_generate.cmm** to setup the DDR4 via Debugger
