SUBDIRS = libdvs

noinst_LTLIBRARIES = libxcam_plugin_dvs.la

XCAM_PLUGIN_DVS_CXXFLAGS = $(XCAM_CXXFLAGS)    \
	-I$(top_builddir)/plugins/smart/dvs/libdvs \
	$(NULL)

if HAVE_LIBDRM
XCAM_PLUGIN_DVS_CXXFLAGS += $(LIBDRM_CFLAGS)
endif

XCAM_PLUGIN_DVS_LIBS =            \
	$(top_builddir)/plugins/smart/dvs/libdvs/libxcam_dvs.la \
	$(NULL)

if HAVE_LIBDRM
XCAM_PLUGIN_DVS_LIBS += $(LIBDRM_LIBS)
endif

plugindir="$(libdir)/xcam/plugins/smart"

libxcam_plugin_dvs_la_SOURCES =   \
	xcam_plugin_dvs.cpp           \
	$(NULL)

libxcam_plugin_dvs_la_CXXFLAGS =                \
	$(GST_CFLAGS) $(XCAM_PLUGIN_DVS_CXXFLAGS)   \
	-I$(top_builddir)/xcore                     \
	-I$(top_builddir)/modules/ocl               \
	$(NULL)

libxcam_plugin_dvs_la_LIBADD =                  \
    $(XCAM_PLUGIN_DVS_LIBS)                     \
    $(top_builddir)/xcore/libxcam_core.la       \
    $(top_builddir)/modules/ocl/libxcam_ocl.la  \
    $(NULL)

libxcam_plugin_dvs_la_LDFLAGS =            \
    -module -avoid-version                 \
    $(top_builddir)/xcore/libxcam_core.la  \
    $(PTHREAD_LDFLAGS)                     \
    $(NULL)

libxcam_plugin_dvs_la_LIBTOOLFLAGS = --tag=disable-static
