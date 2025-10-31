#
# Makefile for the Linux kernel device drivers.
#
# Sep 2018, Binse Park <h22yap@gmail.com>
# Rewritten to use lists instead of if-statements.
#

FLAG=1

ifneq ($(CONFIG_KPERFMON), y)
FLAG=0
endif

ifneq ($(shell [ -e $(srctree)/include/linux/olog.pb.h ] && echo exist), exist)
FLAG=0
endif

ifneq ($(shell [ -e $(srctree)/include/linux/perflog.h ] && echo exist), exist)
FLAG=0
endif

ifeq ($(FLAG), 1)
$(info kperfmon_DUMMY="$(shell cp -f $(srctree)/drivers/kperfmon/ologk.h $(srctree)/include/linux/)")
	obj-y		+= kperfmon.o
else
	obj-y		+= ologk.o
#$(info kperfmon_DUMMY="$(shell cp -f $(srctree)/drivers/kperfmon/ologk.h $(srctree)/include/linux/)")
endif
