ASSEMBLIES = \
	flickr-sharp.dll

UPDATE_ASSEMBLIES = $(addprefix -assembly:lib/, $(ASSEMBLIES))

if ENABLE_MONODOC
SOURCESDIR=$(prefix)/lib/monodoc/sources
TARGETS=flickr-sharp-docs.zip flickr-sharp-docs.tree flickr-sharp-docs.source
UPDATER = $(MONODOCER) -path:en $(UPDATE_ASSEMBLIES)
else
SOURCESDIR=$(datadir)
TARGETS=
UPDATER = echo "All optional assemblies must be built to use the updater." && exit 1
endif

monodocdir=$(SOURCESDIR)
monodoc_DATA=$(TARGETS)

edit:
	monodoc --edit ./en/

assemble: flickr-sharp-docs.zip flickr-sharp-docs.tree

flickr-sharp-docs.zip flickr-sharp-docs.tree: $(srcdir)/en/*.xml $(srcdir)/en/*.xml
	$(MDASSEMBLER) --ecma $(srcdir)/en -o flickr-sharp-docs

get-assemblies:
	mkdir -p lib
	cp $(top_builddir)/build/flickr-sharp.dll lib

update: get-assemblies
	$(UPDATER) --delete

CLEANFILES=flickr-sharp-docs.zip flickr-sharp-docs.tree
EXTRA_DIST=flickr-sharp-docs.source

NAMESPACES = \
	FlickrNet

dist-hook:
	mkdir -p $(distdir)/en
	cp $(srcdir)/en/*.xml $(distdir)/en/
	for i in $(NAMESPACES); do                            \
		mkdir -p $(distdir)/en/$$i;                       \
		cp $(srcdir)/en/$$i/*.xml $(distdir)/en/$$i;      \
	done

clean-local:
	rm -rf lib

