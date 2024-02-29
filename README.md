# meta-m840-imx8mp-kirkstone
This chapter describes how to build an Yocto BSP for a PSMC-M840 i.MX8 module(carrier) by using a Yocto Project build environment. It describes the i.MX release layer and M840-specific usage. The Yocto Project is an open-source collaboration focused on embedded Linux® OS development.

This README file contains information on the contents of the meta-m840-imx8mp-kirkstone layer.

Please see the corresponding sections below for details.

BSP Version
imx-5.10.72-2.2.0 with Yocto Kirkstone

Dependencies
This layer depends on:

URI: git://git.yoctoproject.org/poky branch: master revision: HEAD

URI: git://git.openembedded.org/meta-openembedded layers: meta-oe, meta-multimedia, meta-networking, meta-python branch: master revision: HEAD

URI: git://git.openembedded.org/meta-openembedded/meta-oe branch: master revision: HEAD prio: default

URI: git://git.openembedded.org/meta-openembedded/meta-perl branch: master revision: HEAD prio: default

URI: git://git.openembedded.org/meta-openembedded/meta-networking branch: master revision: HEAD prio: default

Quick Start
$ source setup-environment build/
Add this layer to bblayers.conf and the dependencies above
Set MACHINE in local.conf to one of the supported boards
$ bitbake m840-image
dd to a SD card the generated wic file
Boot Yocto through SD card
Boot the PSMC-M840
Table of Contents
I. Adding the M840 layer to your build II. Build the Layer III. License

I. Adding the M840 layer to your build
Assuming this layer exists at the top-level of your yocto build tree, you can add it to the build system by adding the location of the M840 layer to bblayers.conf, along with any other layers needed. e.g.:

BBLAYERS ?= "
/path/to/meta
/path/to/meta-poky
/path/to/meta-yocto-bsp
/path/to/meta-m840-imx8mp-kirkstone \

or you can run 'bitbake-layers add-layer meta-m840-imx8mp-kirkstone' command.

II. Build the Layer
Run $ bitbake m840-bsp-layer
