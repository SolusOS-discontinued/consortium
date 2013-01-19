lib_LTLIBRARIES = libconsortium-private.la

SUBDIRS=wm-tester tools themes

INCLUDES=-I$(srcdir)/include -DCONSORTIUM_LIBEXECDIR=\"$(libexecdir)\" -DHOST_ALIAS=\"@HOST_ALIAS@\" -DCONSORTIUM_LOCALEDIR=\"$(prefix)/@DATADIRNAME@/locale\" -DCONSORTIUM_PKGDATADIR=\"$(pkgdatadir)\" -DCONSORTIUM_DATADIR=\"$(datadir)\" -DG_LOG_DOMAIN=\"consortium\" -DSN_API_NOT_YET_FROZEN=1 @CONSORTIUM_CFLAGS@

consortium_SOURCES= 				\
	core/async-getprop.c			\
	core/async-getprop.h			\
	core/atomnames.h                        \
	core/bell.c				\
	core/bell.h				\
	core/boxes.c				\
	include/boxes.h				\
	compositor/compositor.c			\
	compositor/compositor-private.h		\
	compositor/compositor-xrender.c		\
	compositor/compositor-xrender.h		\
	include/compositor.h			\
	core/above-tab-keycode.c		\
	core/constraints.c			\
	core/constraints.h			\
	core/core.c				\
	core/delete.c				\
	core/display.c				\
	core/display-private.h			\
	include/display.h			\
	ui/draw-workspace.c			\
	ui/draw-workspace.h			\
	core/edge-resistance.c			\
	core/edge-resistance.h			\
	core/effects.c				\
	core/effects.h				\
	core/errors.c				\
	include/errors.h			\
	core/eventqueue.c			\
	core/eventqueue.h			\
	core/frame.c				\
	core/frame-private.h			\
	include/frame.h				\
	ui/gradient.c				\
	ui/gradient.h				\
	core/group-private.h			\
	core/group-props.c			\
	core/group-props.h			\
	core/group.c				\
	core/group.h				\
	core/iconcache.c			\
	core/iconcache.h			\
	core/keybindings.c			\
	core/keybindings.h			\
	core/main.c				\
	include/main.h				\
	core/consortium-Xatomtype.h		\
	core/place.c				\
	core/place.h				\
	core/prefs.c				\
	include/prefs.h				\
	core/screen.c				\
	core/screen-private.h			\
	include/screen.h			\
	include/types.h                         \
	core/session.c				\
	core/session.h				\
	core/stack.c				\
	core/stack.h				\
	core/util.c				\
	include/util.h				\
	core/window-props.c			\
	core/window-props.h			\
	core/window.c				\
	core/window-private.h			\
	include/window.h			\
	core/workspace.c			\
	core/workspace.h			\
	core/xprops.c				\
	include/xprops.h			\
	include/common.h			\
	include/core.h				\
	include/ui.h				\
	inlinepixbufs.h				\
	ui/fixedtip.c				\
	ui/fixedtip.h				\
	ui/frames.c				\
	ui/frames.h				\
	ui/menu.c				\
	ui/menu.h				\
	ui/metaaccellabel.c			\
	ui/metaaccellabel.h			\
	ui/resizepopup.c			\
	include/resizepopup.h			\
	ui/tabpopup.c				\
	include/tabpopup.h				\
	ui/tile-preview.c			\
	include/tile-preview.h			\
	ui/theme-parser.c			\
	ui/theme-parser.h			\
	ui/theme.c				\
	ui/theme.h				\
	ui/themewidget.c			\
	ui/themewidget.h			\
	ui/ui.c					\
	include/all-keybindings.h

# by setting libconsortium_private_la_CFLAGS, the files shared with
# consortium proper will be compiled with different names.
libconsortium_private_la_CFLAGS =
libconsortium_private_la_SOURCES=			\
	core/boxes.c				\
	include/boxes.h				\
	ui/gradient.c				\
	ui/gradient.h				\
	core/util.c				\
	include/util.h				\
	include/common.h			\
	ui/preview-widget.c			\
	ui/preview-widget.h			\
	ui/theme-parser.c			\
	ui/theme-parser.h			\
	ui/theme.c				\
	ui/theme.h

libconsortium_private_la_LDFLAGS = -no-undefined
libconsortium_private_la_LIBADD  = @CONSORTIUM_LIBS@

libconsortiumincludedir = $(includedir)/consortium-1/consortium-private

libconsortiuminclude_HEADERS =			\
	include/boxes.h				\
	ui/gradient.h				\
	include/util.h				\
	include/common.h			\
	ui/preview-widget.h			\
	ui/theme-parser.h			\
	ui/theme.h

consortium_theme_viewer_SOURCES=  \
	ui/theme-viewer.c

gsettings_SCHEMAS = org.consort.consortium.gschema.xml
@INTLTOOL_XML_NOMERGE_RULE@
@GSETTINGS_RULES@

convertdir = $(datadir)/GConf/gsettings/
convert_DATA = consortium-schemas.convert

bin_PROGRAMS=consortium consortium-theme-viewer

EFENCE=
consortium_LDADD=@CONSORTIUM_LIBS@ $(EFENCE)
consortium_theme_viewer_LDADD= @CONSORTIUM_LIBS@ libconsortium-private.la

testboxes_SOURCES=include/util.h core/util.c include/boxes.h core/boxes.c core/testboxes.c
testgradient_SOURCES=ui/gradient.h ui/gradient.c ui/testgradient.c
testasyncgetprop_SOURCES=core/async-getprop.h core/async-getprop.c core/testasyncgetprop.c

noinst_PROGRAMS=testboxes testgradient testasyncgetprop

testboxes_LDADD= @CONSORTIUM_LIBS@
testgradient_LDADD= @CONSORTIUM_LIBS@
testasyncgetprop_LDADD= @CONSORTIUM_LIBS@

@INTLTOOL_DESKTOP_RULE@

desktopfilesdir=$(datadir)/applications
desktopfiles_in_files=consortium.desktop.in
desktopfiles_files=$(desktopfiles_in_files:.desktop.in=.desktop)
desktopfiles_DATA = $(desktopfiles_files)

wmpropertiesdir=$(datadir)/gnome/wm-properties
wmproperties_in_files=consortium-wm.desktop.in
wmproperties_files=$(wmproperties_in_files:.desktop.in=.desktop)
wmproperties_DATA = $(wmproperties_files)

xmldir       = @GNOME_KEYBINDINGS_KEYSDIR@
xml_in_files = \
	50-consortium-navigation.xml.in	\
	50-consortium-system.xml.in	\
	50-consortium-windows.xml.in

xml_DATA     = $(xml_in_files:.xml.in=.xml)

@INTLTOOL_SCHEMAS_RULE@

IMAGES=stock_maximize.png stock_minimize.png stock_delete.png window.png mini-window.png
VARIABLES=stock_maximize_data $(srcdir)/stock_maximize.png \
          stock_minimize_data $(srcdir)/stock_minimize.png \
          stock_delete_data $(srcdir)/stock_delete.png \
          mini_window_data $(srcdir)/mini-window.png \
          window_data $(srcdir)/window.png

BUILT_SOURCES = inlinepixbufs.h
CLEANFILES = inlinepixbufs.h consortium.desktop consortium-wm.desktop org.consort.consortium.gschema.xml 50-consortium-launchers.xml 50-consortium-navigation.xml 50-consortium-screenshot.xml 50-consortium-system.xml 50-consortium-windows.xml

inlinepixbufs.h: $(IMAGES)
	$(AM_V_GEN)$(GDK_PIXBUF_CSOURCE) --raw --build-list $(VARIABLES) >$(srcdir)/inlinepixbufs.h

pkgconfigdir = $(libdir)/pkgconfig

pkgconfig_DATA = libconsortium-private.pc

EXTRA_DIST=$(desktopfiles_files)	 	\
	$(wmproperties_files)			\
	$(IMAGES)		 		\
	$(desktopfiles_in_files)		\
	$(wmproperties_in_files)		\
	consortium-schemas.convert		\
	org.consort.consortium.gschema.xml.in	\
	$(xml_in_files)				\
	libconsortium-private.pc.in

