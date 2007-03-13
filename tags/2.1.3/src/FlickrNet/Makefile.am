BINDIR=$(top_builddir)/build
ASSEMBLY_DLL=flickr-sharp.dll
ASSEMBLY=$(BINDIR)/$(ASSEMBLY_DLL)
ASSEMBLY_MDB=$(ASSEMBLY).mdb

KEYFILE = \
	FlickrNet.snk

FILES = \
	FlickrNet/ActivityEvent.cs \
	FlickrNet/ActivityItem.cs \
	FlickrNet/Auth.cs \
	FlickrNet/Blogs.cs \
	FlickrNet/BoundaryBox.cs \
	FlickrNet/Cache.cs \
	FlickrNet/Categories.cs \
	FlickrNet/Comments.cs \
	FlickrNet/Contacts.cs \
	FlickrNet/Context.cs \
	FlickrNet/DateGranularity.cs \
	FlickrNet/Enums.cs \
	FlickrNet/ExifPhoto.cs \
	FlickrNet/FlickrConfigurationManager.cs \
	FlickrNet/FlickrConfigurationSettings.cs \
	FlickrNet/Flickr.cs \
	FlickrNet/FlickrException.cs \
	FlickrNet/GeoAccuracy.cs \
	FlickrNet/GeoPermissions.cs \
	FlickrNet/Groups.cs \
	FlickrNet/GroupSearchResults.cs \
	FlickrNet/Licenses.cs \
	FlickrNet/LockFile.cs \
	FlickrNet/Methods.cs \
	FlickrNet/PartialSearchOptions.cs \
	FlickrNet/PersistentCache.cs \
	FlickrNet/Person.cs \
	FlickrNet/PhotoCounts.cs \
	FlickrNet/Photo.cs \
	FlickrNet/PhotoDates.cs \
	FlickrNet/PhotoInfo.cs \
	FlickrNet/PhotoLocation.cs \
	FlickrNet/PhotoPermissions.cs \
	FlickrNet/Photos.cs \
	FlickrNet/PhotoSearchExtras.cs \
	FlickrNet/PhotoSearchOptions.cs \
	FlickrNet/PhotoSearchOrder.cs \
	FlickrNet/PhotoSets.cs \
	FlickrNet/Response.cs \
	FlickrNet/SafeNativeMethods.cs \
	FlickrNet/Sizes.cs \
	FlickrNet/Tags.cs \
	FlickrNet/Uploader.cs \
	FlickrNet/UploadProgressEvent.cs \
	FlickrNet/User.cs \
	FlickrNet/Utils.cs \
	AssemblyInfo.cs
 
RESOURCES =

REFERENCES = \
	-r:System.dll \
	-r:System.Xml.dll \
	-r:System.Web.dll \
	-r:System.Data.dll \
	-r:System.Drawing.dll

BUILD_FILES=$(addprefix $(srcdir)/, $(FILES))
BUILD_RESOURCES=$(addprefix -resource:$(srcdir)/, $(RESOURCES))

all: $(ASSEMBLY)

$(ASSEMBLY): $(FILES) $(RESOURCES)
	mkdir -p $(BINDIR)
	$(MCS) $(CSC_FLAGS) -debug+ -target:library -out:$(ASSEMBLY) \
	$(BUILD_FILES) $(BUILD_RESOURCES) $(REFERENCES)

CLEANFILES=$(ASSEMBLY) $(ASSEMBLY_MDB)
EXTRA_DIST=$(FILES) $(RESOURCES) $(KEYFILE)

flickrsharpdir=$(FLICKRSHARPDIR)
flickrsharp_DATA=$(ASSEMBLY) $(ASSEMBLY_MDB)
