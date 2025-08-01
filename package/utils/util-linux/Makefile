#
# Copyright (C) 2007-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=util-linux
PKG_VERSION:=2.41.1
PKG_RELEASE:=2

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@KERNEL/linux/utils/$(PKG_NAME)/v2.41
PKG_HASH:=be9ad9a276f4305ab7dd2f5225c8be1ff54352f565ff4dede9628c1aaa7dec57
PKG_CPE_ID:=cpe:/a:kernel:util-linux


PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

define Package/util-linux/Default
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:= +librt
  URL:=http://www.kernel.org/pub/linux/utils/util-linux/
endef

define Package/libblkid
$(call Package/util-linux/Default)
  DEPENDS:=+libuuid
  TITLE:=block device id library
  SECTION:=libs
  CATEGORY:=Libraries
  ABI_VERSION:=1
  LICENSE:=LGPL-2.1-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.LGPL-2.1-or-later
endef

define Package/libblkid/description
 The libblkid library is used to identify block devices (disks) as to their
 content (e.g. filesystem type, partitions) as well as extracting additional
 information such as filesystem labels/volume names, partitions, unique
 identifiers/serial numbers...
endef

define Package/libfdisk
$(call Package/util-linux/Default)
  DEPENDS:=+libuuid +libblkid
  TITLE:=partition manipulating library
  SECTION:=libs
  CATEGORY:=Libraries
  ABI_VERSION:=1
  LICENSE:=LGPL-2.1-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.LGPL-2.1-or-later
endef

define Package/libfdisk/description
  The libfdisk library is used for manipulating with partition tables.
endef

define Package/libmount
$(call Package/util-linux/Default)
  DEPENDS:=+libblkid
  TITLE:=mount library
  SECTION:=libs
  CATEGORY:=Libraries
  ABI_VERSION:=1
  LICENSE:=LGPL-2.1-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.LGPL-2.1-or-later
endef

define Package/libmount/description
 The libmount library is used to parse /etc/fstab, /etc/mtab and
 /proc/self/mountinfo files, manage the mtab file, evaluate mount options...
endef

define Package/libuuid
$(call Package/util-linux/Default)
  TITLE:=DCE compatible Universally Unique Identifier library
  SECTION:=libs
  CATEGORY:=Libraries
  ABI_VERSION:=1
  LICENSE:=BSD-3-Clause
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-3-Clause
endef

define Package/libuuid/description
 The UUID library is used to generate unique identifiers for objects
 that may be accessible beyond the local system. This library
 generates UUIDs compatible with those created by the Open Software
 Foundation (OSF) Distributed Computing Environment (DCE) utility.
endef

define Package/libsmartcols
$(call Package/util-linux/Default)
  TITLE:=table or tree library
  SECTION:=libs
  CATEGORY:=Libraries
  ABI_VERSION:=1
  LICENSE:=LGPL-2.1-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.LGPL-2.1-or-later
endef

define Package/libsmartcols/description
 The smartcols library is used to print tables and trees in a pretty way.
endef

define Package/agetty
$(call Package/util-linux/Default)
  TITLE:=alternative Linux getty
  SUBMENU=Terminal
  LICENSE:=Public-Domain
endef

define Package/agetty/description
 agetty opens a tty port, prompts for a login name and invokes the
 /bin/login command
endef

define Package/blkdiscard
$(call Package/util-linux/Default)
  TITLE:=discard sectors on a device
  SUBMENU=Disc
  DEPENDS:=libblkid
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/blkdiscard/description
 The blkdiscard is used to discard device sectors. This is useful for
 solid-state drivers (SSDs) and thinly-provisioned storage. Unlike fstrim,
 this command is used directly on the block device.
endef

define Package/blkid
$(call Package/util-linux/Default)
  TITLE:=locate and print block device attributes
  DEPENDS:= +libblkid +libuuid
  SUBMENU=Disc
  LICENSE:=LGPL-2.1-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.LGPL-2.1-or-later
endef

define Package/blkid/description
 The blkid program is the command-line interface to working with the libblkid
 library.
endef

define Package/blockdev
$(call Package/util-linux/Default)
  TITLE:=call block device ioctls from the command line
  SUBMENU=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/blockdev/description
 The blockdev program is the command-line interface to call block device ioctls.
endef

define Package/cal
$(call Package/util-linux/Default)
  TITLE:=display a calendar
  DEPENDS:= +libncurses
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/cal/description
 cal displays a simple calendar
endef

define Package/cfdisk
$(call Package/util-linux/Default)
  TITLE:=display or manipulate disk partition table
  DEPENDS:= +libblkid +libncurses +libsmartcols +libfdisk +libmount
  SUBMENU:=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/cfdisk/description
 cfdisk is a curses-based program for partitioning any hard disk drive
endef

define Package/colrm
$(call Package/util-linux/Default)
  TITLE:=colrm removes selected columns from a file
  DEPENDS:=
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/colrm/description
 colrm removes selected columns from a file. Input is taken from
 standard input. Output is sent to standard output.
endef

define Package/dmesg
$(call Package/util-linux/Default)
  TITLE:=print or control the kernel ring buffer
  DEPENDS:= +libncursesw
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/dmesg/description
 dmesg  is used to examine or control the kernel ring buffer
endef

define Package/eject
$(call Package/util-linux/Default)
  TITLE:=eject removable media
  DEPENDS:= +libblkid +libmount +libuuid
  SUBMENU=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/eject/description
  eject allows removable media (typically a CD-ROM, floppy disk, tape, or JAZ
  or ZIP disk) to be ejected under software control.
endef

define Package/fdisk
$(call Package/util-linux/Default)
  TITLE:=manipulate disk partition table
  DEPENDS:= +libblkid +libsmartcols +libfdisk +libncursesw
  SUBMENU=Disc
  LICENSE:=GPL-1.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-1.0-or-later
endef

define Package/fdisk/description
 a menu-driven program for creation and manipulation of partition tables
endef

define Package/findfs
$(call Package/util-linux/Default)
  TITLE:=find a filesystem by label or UUID
  DEPENDS:= +libblkid
  SUBMENU=Disc
  LICENSE:=GPL-1.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-1.0-or-later
endef

define Package/findfs/description
 findfs will search the disks in the system looking for a filesystem which has
 a label matching label or a UUID equal to uuid
endef

define Package/flock
$(call Package/util-linux/Default)
  TITLE:=manage locks from shell scripts
  ALTERNATIVES:=200:/usr/bin/flock:/usr/bin/util-linux-flock
  LICENSE:=MIT
  LICENSE_FILES:=Documentation/licenses/COPYING.MIT
endef

define Package/flock/description
  manages flock locks from within shell scripts or the command line
endef

define Package/fstrim
$(call Package/util-linux/Default)
  TITLE:=discard unused blocks on a mounted filesystem
  DEPENDS:= +libblkid +libuuid +libsmartcols +libmount
  SUBMENU=Filesystem
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/fstrim/description
  fstrim is used on a mounted filesystem to discard (or "trim") blocks
  which are not in use by the filesystem.  This is useful for solid-
  state drives (SSDs) and thinly-provisioned storage.
endef

define Package/getopt
$(call Package/util-linux/Default)
  TITLE:=parse command options (enhanced)
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/getopt/description
 getopt is used to break up (parse) options in command lines for easy parsing
 by shell procedures, and to check for legal options
endef

define Package/hwclock
$(call Package/util-linux/Default)
  TITLE:=query or set the hardware clock
  LICENSE:=GPL-3.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-3.0-or-later
endef

define Package/hwclock/description
 hwclock is a tool for accessing the Hardware Clock
endef

define Package/ipcs
$(call Package/util-linux/Default)
  TITLE:=show information on IPC facilities
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/ipcs/description
  ipcs shows information on the inter-process communication facilities for
  which the calling process has read access. By default it shows information
  about all three resources: shared memory segments, message queues, and
  semaphore arrays.
endef

define Package/last
$(call Package/util-linux/Default)
  TITLE:=display history of user logins and logout sessions
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/last/description
 last utility displays a history of user login and logout sessions, system reboots,
 and other events recorded in /var/log/wtmp (or a specified file)
endef

define Package/logger
$(call Package/util-linux/Default)
  TITLE:=a shell command interface to the syslog system log module
  ALTERNATIVES:=200:/usr/bin/logger:/usr/bin/util-linux-logger
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/logger/description
 logger makes entries in the system log, it provides a shell command interface
 to the syslog system log module
endef

define Package/look
$(call Package/util-linux/Default)
  TITLE:=display lines beginning with a given string
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/look/description
 look utility displays any lines in file which contain string
endef

define Package/losetup
$(call Package/util-linux/Default)
  TITLE:=set up and control loop devices
  DEPENDS:= +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/losetup/description
 losetup is used to associate loop devices with regular files or block devices,
 to detach loop devices and to query the status of a loop device
endef

define Package/lsblk
$(call Package/util-linux/Default)
  TITLE:=list block devices
  DEPENDS:= +libblkid +libmount +libsmartcols +libncurses
  SUBMENU=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/lsblk/description
 lsblk lists information about all or the specified block devices
endef

define Package/lscpu
$(call Package/util-linux/Default)
  TITLE:=display information about the CPU architecture
  DEPENDS:= +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/lscpu/description
 lscpu displays information about the CPU architecture
endef

define Package/lslocks
$(call Package/util-linux/Default)
  TITLE:=list local system locks
  DEPENDS:= +libmount +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/lslocks/description
 lslocks lists information about all the currently held file locks in a Linux system
endef

define Package/lsns
$(call Package/util-linux/Default)
  TITLE:=list system namespaces
  DEPENDS:= +libblkid +libmount +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/lsns/description
 lsns lists information about all namespaces and their processes
endef

define Package/more
$(call Package/util-linux/Default)
  TITLE:=filter for paging through text one screenful at a time
  DEPENDS:= +libncurses
  LICENSE:=BSD-4.3TAHOE
endef

define Package/more/description
 more is a filter for paging through text one screenful at a time
endef

define Package/mcookie
$(call Package/util-linux/Default)
  TITLE:=generate magic cookies for xauth
  LICENSE:=Public-Domain
endef

define Package/mcookie/description
 mcookie generates a 128-bit random hexadecimal number for use with the X
 authority system
endef

define Package/mount-utils
$(call Package/util-linux/Default)
  TITLE:=related (u)mount utilities
  DEPENDS+= +libmount +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/mount-utils/description
 contains: mount, umount, findmnt
endef

define Package/namei
$(call Package/util-linux/Default)
  TITLE:=follow a pathname until a terminal point is found
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/namei/description
 namei uses its arguments as pathnames to any type of Unix file (symlinks,
 files, directories, and so forth)
endef

define Package/nsenter
$(call Package/util-linux/Default)
  TITLE:=enter a namespace
  LICENSE:=GPL-2.0-only
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-only
endef

define Package/nsenter/description
  run program with namespaces of other processes
endef

define Package/prlimit
$(call Package/util-linux/Default)
  TITLE:=get and set process resource limits
  DEPENDS:= +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/prlimit/description
  Given a process id and one or more resources, prlimit tries to retrieve
  and/or modify the limits.
endef

define Package/rename
$(call Package/util-linux/Default)
  TITLE:=rename files
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/rename/description
 rename will rename the specified files by replacing the first occurrence of
 expression in their name by replacement
endef

define Package/rev
$(call Package/util-linux/Default)
  TITLE:=Reverse lines characterwise
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/rev/description
 rev utility copies the specified files to the standard output, reversing the
 order of characters in every line. If no files are specified, the standard
 input is read.
endef

define Package/partx-utils
$(call Package/util-linux/Default)
  TITLE:=inform kernel about the presence and numbering of on-disk partitions
  DEPENDS:= +libblkid +libsmartcols
  SUBMENU=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/partx-utils/description
 contains partx, addpart, delpart
endef

define Package/script-utils
$(call Package/util-linux/Default)
  TITLE:=make and replay typescript of terminal session
  SUBMENU=Terminal
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/script-utils/description
 contains: script, scriptreplay
endef

define Package/setterm
$(call Package/util-linux/Default)
  TITLE:=set terminal attributes
  DEPENDS:= +libncurses
  SUBMENU:=Terminal
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/setterm/description
 setterm writes to standard output a character string that will invoke the
 specified terminal capabilities
endef

define Package/sfdisk
$(call Package/util-linux/Default)
  TITLE:=partition table manipulator for Linux
  SUBMENU=Disc
  DEPENDS:= +libblkid +libfdisk +libsmartcols +libncursesw
  LICENSE:=GPL-1.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-1.0-or-later
endef

define Package/sfdisk/description
 list the size of a partition, list the partitions on a device, check the
 partitions on a device and repartition a device
endef

define Package/swap-utils
$(call Package/util-linux/Default)
  TITLE:=swap space management utilities
  DEPENDS+= +libblkid
  SUBMENU:=Filesystem
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/swap-utils/description
 contains: mkswap, swaplabel
endef

define Package/taskset
$(call Package/util-linux/Default)
  TITLE:=set or retrieve a process's CPU affinity
  ALTERNATIVES:=200:/usr/bin/taskset:/usr/bin/util-linux-taskset
  LICENSE:=GPL-2.0-only
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-only
endef

define Package/taskset/description
 contains: taskset
endef

define Package/unshare
$(call Package/util-linux/Default)
  TITLE:=unshare userspace tool
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/unshare/description
  run programs with some namespaces unshared from parent
endef

define Package/uuidd
$(call Package/util-linux/Default)
  TITLE:=UUID generation daemon
  DEPENDS:= +libuuid
  LICENSE:=GPL-1.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-1.0-or-later
endef

define Package/uuidd/description
 The uuidd daemon is used by the UUID library to generate universally unique
 identifiers (UUIDs), especially time-based UUIDs, in a secure and
 guaranteed-unique fashion, even in the face of large numbers of threads
 running on different CPUs trying to grab UUIDs.
endef

define Package/uuidgen
$(call Package/util-linux/Default)
  TITLE:=create a new UUID value
  DEPENDS:= +libuuid
  LICENSE:=GPL-1.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-1.0-or-later
endef

define Package/uuidgen/description
 The uuidgen program creates (and prints) a new universally unique identifier
 (UUID) using the libuuid library. The new UUID can reasonably be considered
 unique among all UUIDs created on the local system, and among UUIDs created on
 other systems in the past and in the future.
endef

define Package/wall
$(call Package/util-linux/Default)
  TITLE:=send a message to everybody's terminal
  SUBMENU=Terminal
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/wall/description
 wall sends a message to everybody logged in with their mesg permission
 set to yes
endef

define Package/wdctl
$(call Package/util-linux/Default)
  TITLE:=show hardware watchdog status
  DEPENDS:= +libsmartcols
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/wdctl/description
 Show hardware watchdog status. The default device is /dev/watchdog. If more
 than one device is specified then the output is separated by one blank line.
 If the device is already used or user has no permissions to read from the
 device, then wdctl reads data from sysfs. In this case information about
 supported features (flags) might be missing. Note that the number of supported
 watchdog features is hardware specific.
endef

define Package/whereis
$(call Package/util-linux/Default)
  TITLE:=locate the binary, source, and manual page files for a command
  LICENSE=BSD-4-Clause-UC
  LICENSE_FILES:=Documentation/licenses/COPYING.BSD-4-Clause-UC
endef

define Package/whereis/description
 whereis locates source/binary and manuals sections for specified files
endef

define Package/wipefs
$(call Package/util-linux/Default)
  TITLE:=wipe a signature from a device
  DEPENDS:= +libblkid +libsmartcols
  SUBMENU:=Disc
  LICENSE:=GPL-2.0-or-later
  LICENSE_FILES:=Documentation/licenses/COPYING.GPL-2.0-or-later
endef

define Package/wipefs/description
 wipefs can erase filesystem, raid or partition table signatures (magic
 strings) from the specified device to make the signature invisible for
 libblkid.
endef

MESON_ARGS += \
	-Dsystemd=disabled \
	-Dtinfo=disabled \
	-Dcryptsetup=disabled \
	-Dlibutil=disabled \
	-Dlibutempter=disabled \
	-Dlibpcre2-posix=disabled \
	-Dlibuser=disabled \
	-Duse-tty-group=false \
	-Duse-tls=false \
	-Dtranslate-docs=disabled \
	-Dbuild-python=disabled \
	-Dbuild-zramctl=disabled \
	-Dbuild-fsck=disabled \
	-Dbuild-wipefs=disabled \
	-Dbuild-fallocate=disabled \
	-Dbuild-setpriv=disabled \
	-Dbuild-hardlink=disabled \
	-Dbuild-cramfs=disabled \
	-Dbuild-bfs=disabled \
	-Dbuild-minix=disabled \
	-Dbuild-fdformat=disabled \
	-Dbuild-lslogins=disabled \
	-Dbuild-switch_root=disabled \
	-Dbuild-pivot_root=disabled \
	-Dbuild-lsmem=disabled \
	-Dbuild-lsirq=disabled \
	-Dbuild-irqtop=disabled \
	-Dbuild-chmem=disabled \
	-Dbuild-ipcrm=disabled \
	-Dbuild-rfkill=disabled \
	-Dbuild-tunelp=disabled \
	-Dbuild-kill=disabled \
	-Dbuild-utmpdump=disabled \
	-Dbuild-line=disabled \
	-Dbuild-mesg=disabled \
	-Dbuild-raw=disabled \
	-Dbuild-vipw=disabled \
	-Dbuild-newgrp=disabled \
	-Dbuild-chfn-chsh=disabled \
	-Dbuild-login=disabled \
	-Dbuild-nologin=disabled \
	-Dbuild-sulogin=disabled \
	-Dbuild-su=disabled \
	-Dbuild-runuser=disabled \
	-Dbuild-ul=disabled \
	-Dbuild-pg=disabled \
	-Dbuild-write=disabled \
	-Dbuild-bash-completion=disabled \
	-Dbuild-pylibmount=disabled \
	-Dbuild-liblastlog2=disabled \
	-Dreadline=disabled \
	-Dmagic=disabled \
	-Dncursesw=enabled

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/blkid.pc $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/fdisk.pc $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/mount.pc $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/smartcols.pc $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/uuid.pc $(1)/usr/lib/pkgconfig

	$(INSTALL_DIR) $(1)/usr/include/blkid
	$(CP) $(PKG_INSTALL_DIR)/usr/include/blkid/blkid.h $(1)/usr/include/blkid
	$(INSTALL_DIR) $(1)/usr/include/libfdisk
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libfdisk/libfdisk.h $(1)/usr/include/libfdisk
	$(INSTALL_DIR) $(1)/usr/include/libmount
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libmount/libmount.h $(1)/usr/include/libmount
	$(INSTALL_DIR) $(1)/usr/include/uuid
	$(CP) $(PKG_INSTALL_DIR)/usr/include/uuid/uuid.h $(1)/usr/include/uuid
	$(INSTALL_DIR) $(1)/usr/include/libsmartcols
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libsmartcols/libsmartcols.h $(1)/usr/include/libsmartcols

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libblkid.so* $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libfdisk.so* $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libmount.so* $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libuuid.so* $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsmartcols.so* $(1)/usr/lib
endef


define Package/libfdisk/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libfdisk.so.* $(1)/usr/lib/
endef

define Package/libblkid/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libblkid.so.* $(1)/usr/lib/
endef

define Package/libmount/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libmount.so.* $(1)/usr/lib/
endef

define Package/libsmartcols/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsmartcols.so.* $(1)/usr/lib/
endef

define Package/libuuid/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libuuid.so.* $(1)/usr/lib/
endef

define Package/agetty/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/agetty $(1)/usr/sbin/
endef

define Package/blkdiscard/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/blkdiscard $(1)/usr/sbin/
endef

define Package/blkid/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/blkid $(1)/usr/sbin/
endef

define Package/blockdev/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/blockdev $(1)/usr/sbin/
endef

define Package/cal/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/cal $(1)/usr/bin/
endef

define Package/cfdisk/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/cfdisk $(1)/usr/sbin/
endef

define Package/colrm/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/colrm $(1)/usr/bin/
endef

define Package/dmesg/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/dmesg $(1)/usr/bin/
endef

define Package/eject/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/eject $(1)/usr/bin/
endef

define Package/fdisk/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/fdisk $(1)/usr/sbin/
endef

define Package/findfs/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/findfs $(1)/usr/sbin/
endef

define Package/flock/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/flock $(1)/usr/bin/util-linux-flock
endef

define Package/fstrim/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/fstrim $(1)/usr/sbin/
endef

define Package/getopt/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/getopt $(1)/usr/bin/
endef

define Package/hwclock/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/hwclock $(1)/usr/sbin/
endef

define Package/ipcs/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/ipcs $(1)/usr/bin/
endef

define Package/last/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/last $(1)/usr/bin/
endef

define Package/logger/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/logger $(1)/usr/bin/util-linux-logger
endef

define Package/look/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/look $(1)/usr/bin/
endef

define Package/losetup/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/losetup $(1)/usr/sbin/
endef

define Package/lsblk/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/lsblk $(1)/usr/bin/
endef

define Package/lscpu/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/lscpu $(1)/usr/bin/
endef

define Package/lslocks/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/lslocks $(1)/usr/bin/
endef

define Package/lsns/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/lsns $(1)/usr/bin/
endef

define Package/more/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/more $(1)/usr/bin/
endef

define Package/mcookie/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/mcookie $(1)/usr/bin/
endef

define Package/mount-utils/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/{u,}mount $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/mountpoint $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/findmnt $(1)/usr/bin/
endef

define Package/namei/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/namei $(1)/usr/bin/
endef

define Package/nsenter/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/nsenter $(1)/usr/bin/
endef

define Package/prlimit/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/prlimit $(1)/usr/bin/
endef

define Package/rename/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/rename $(1)/usr/bin/
endef

define Package/rev/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/rev $(1)/usr/bin/
endef

define Package/partx-utils/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/partx $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/addpart $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/delpart $(1)/usr/sbin/
endef

define Package/script-utils/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/script $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/scriptreplay $(1)/usr/bin/
endef

define Package/setterm/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/setterm $(1)/usr/bin/
endef

define Package/sfdisk/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/sfdisk $(1)/usr/sbin/
endef

define Package/swap-utils/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/mkswap $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/swaplabel $(1)/usr/sbin/
endef

define Package/taskset/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/taskset $(1)/usr/bin/util-linux-taskset
endef

define Package/unshare/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/unshare $(1)/usr/bin/
endef

define Package/uuidd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/uuidd $(1)/usr/sbin/
endef

define Package/uuidgen/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/uuidgen $(1)/usr/bin/
endef

define Package/wall/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/wall $(1)/usr/bin/
endef

# Install to /bin instead of /usr/bin to not conflict wdctl from wifidog
define Package/wdctl/install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/wdctl $(1)/bin/
endef

define Package/whereis/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/whereis $(1)/usr/bin/
endef

define Package/wipefs/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/wipefs $(1)/usr/sbin/
endef

# these lines need to be ordered by dependency because of ABI versioning
$(eval $(call BuildPackage,libuuid))
$(eval $(call BuildPackage,libblkid))
$(eval $(call BuildPackage,libfdisk))

$(eval $(call BuildPackage,libmount))
$(eval $(call BuildPackage,libsmartcols))
$(eval $(call BuildPackage,agetty))
$(eval $(call BuildPackage,blkdiscard))
$(eval $(call BuildPackage,blkid))
$(eval $(call BuildPackage,blockdev))
$(eval $(call BuildPackage,cal))
$(eval $(call BuildPackage,cfdisk))
$(eval $(call BuildPackage,colrm))
$(eval $(call BuildPackage,dmesg))
$(eval $(call BuildPackage,eject))
$(eval $(call BuildPackage,fdisk))
$(eval $(call BuildPackage,findfs))
$(eval $(call BuildPackage,flock))
$(eval $(call BuildPackage,fstrim))
$(eval $(call BuildPackage,getopt))
$(eval $(call BuildPackage,hwclock))
$(eval $(call BuildPackage,ipcs))
$(eval $(call BuildPackage,last))
$(eval $(call BuildPackage,logger))
$(eval $(call BuildPackage,look))
$(eval $(call BuildPackage,losetup))
$(eval $(call BuildPackage,lsblk))
$(eval $(call BuildPackage,lscpu))
$(eval $(call BuildPackage,lslocks))
$(eval $(call BuildPackage,lsns))
$(eval $(call BuildPackage,more))
$(eval $(call BuildPackage,mcookie))
$(eval $(call BuildPackage,mount-utils))
$(eval $(call BuildPackage,namei))
$(eval $(call BuildPackage,nsenter))
$(eval $(call BuildPackage,prlimit))
$(eval $(call BuildPackage,rename))
$(eval $(call BuildPackage,rev))
$(eval $(call BuildPackage,partx-utils))
$(eval $(call BuildPackage,script-utils))
$(eval $(call BuildPackage,setterm))
$(eval $(call BuildPackage,sfdisk))
$(eval $(call BuildPackage,swap-utils))
$(eval $(call BuildPackage,taskset))
$(eval $(call BuildPackage,unshare))
$(eval $(call BuildPackage,uuidd))
$(eval $(call BuildPackage,uuidgen))
$(eval $(call BuildPackage,wall))
$(eval $(call BuildPackage,wdctl))
$(eval $(call BuildPackage,whereis))
$(eval $(call BuildPackage,wipefs))
