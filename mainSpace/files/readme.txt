=========
ATTENTION
=========
All files in this folder are open source and are released to the public.
No private or commercial code is allowed in this folder.

--------
Building
--------
Run "./build full" at the prompt.  This will build the boot loader and
OS images from source, placing them in the ../bin folder.

The ./build script is designed to run under Ubuntu Linux 10.10 for x86.

--------------------------------
Setting up the build environment
--------------------------------
If you develop on Windows, use VMWare Player to host Ubuntu 10.10.
At Neato, see \\bender\neato\Setups\Apps\VMWare\readme.txt for details.

If you are using your own Ubuntu system, apt-get install these packages:
build-essential lzop

Open up a terminal window (Application/Accessories/Terminal) and type:
cd /mnt/hgfs/linux/src     # or the src/ directory of this package
./build full

-----------------------
Contents of this folder
-----------------------
armtools/
	Code Sourcery G++ Lite Edition ARM cross-compiler
boot/
	U-Boot, along with Neato patches for our hardware
busybox/
	BusyBox, along with Neato configuration file
kernel/
	Linux Kernel, along with Neato config and patches
rootfs/
	Neato root file system, including startup scripts
build
	Script to build and package all components for deployment

--------------
Making changes
--------------
The bulk of the source code is stored unchanged in release archives,
with the extension .tar.gz or .tar.bz2.

Neato additions are stored as separate files, outside the archive.

If you need to change a file, you should first copy it out of the
staging area, /tmp/neato/xxx/, into the matching src/xxx/ folder.

Do not modify files in /tmp/neato, or your changes will be lost.

Use "./build delta" to do partial rebuilds for quicker testing.

If you want to use a new version of a release archive, you will need
to patch the Neato additions to match, or else the build will fail.
