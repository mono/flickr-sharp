SUBDIRS = src po doc
bin_SCRIPTS = flickr-sharp

# for linking with pkg-config at some point
pkgconfig_in_files = flickr-sharp.pc.in

pkgconfigdir=$(prefix)/lib/pkgconfig
pkgconfig_DATA=$(pkgconfig_in_files:.pc.in=.pc)

REWRITE =                                   \
	sed -e "s|\@prefix\@|$(prefix)|g"       \
		-e "s|\@pkglibdir\@|$(pkglibdir)|g" \
		-e "s|\@bindir\@|$(bindir)|g"       \
		-e "s|\@MONO\@|$(MONO)|g"

$(bin_SCRIPTS): $(srcdir)/flickr-sharp.in Makefile
	$(REWRITE) $(srcdir)/flickr-sharp.in > $@.tmp
	mv $@.tmp $@

CLEANFILES = \
	intltool-merge   \
	intltool-extract \
	intltool-update  \
	flickr-sharp \
	flickr-sharp.pc

EXTRA_DIST = \
	flickr-sharp.in \
	flickr-sharp.pc.in  \
	intltool-extract.in \
	intltool-merge.in   \
	intltool-update.in

DISCLEANFILES =  \
	configure    \
	config.guess \
    config.sub   \
    Makefile.in  \
    install-sh   \
    aclocal.m4   \
    INSTALL      \
    COPYING      \
    missing
