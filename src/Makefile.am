AM_CFLAGS = -Wall -std=c99
AM_CPPFLAGS = -isystem $(SYSROOT)/usr/include/$(CRYPTOLIB) $(LIBUSB_CFLAGS)

bin_PROGRAMS = tegrarcm
tegrarcm_SOURCES = \
	main.c \
	usb.c \
	nv3p.c \
	debug.c \
	rcm.c \
	rsa-pss.cpp \
	rsa-pss.h \
	aes-cmac.cpp \
	aes-cmac.h \
	debug.h \
	nv3p.h \
	nv3p_status.h \
	rcm.h \
	miniloader/tegra20-miniloader.h \
	miniloader/tegra30-miniloader.h \
	miniloader/tegra114-miniloader.h \
	miniloader/tegra124-miniloader.h \
	usb.h

man_MANS = tegrarcm.1

EXTRA_DIST = tegrarcm.1.in
DISTCLEANFILES = tegrarcm.1

tegrarcm_LDADD = $(LIBUSB_LIBS) -l$(CRYPTOLIB) -lpthread

tegrarcm.1: $(srcdir)/tegrarcm.1.in
	sed 's|VERSION|$(VERSION)|g' $< >$@
