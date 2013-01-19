@INTLTOOL_DESKTOP_RULE@

icondir=$(pkgdatadir)/icons
icon_DATA=consortium-window-demo.png

INCLUDES=@CONSORTIUM_WINDOW_DEMO_CFLAGS@ @CONSORTIUM_MESSAGE_CFLAGS@ \
	-DCONSORTIUM_ICON_DIR=\"$(pkgdatadir)/icons\" \
	-DCONSORTIUM_LOCALEDIR=\"$(prefix)/@DATADIRNAME@/locale\"

consortium_message_SOURCES= 				\
	consortium-message.c

consortium_window_demo_SOURCES=				\
	consortium-window-demo.c

consortium_mag_SOURCES=					\
	consortium-mag.c

consortium_grayscale_SOURCES=				\
	consortium-grayscale.c

bin_PROGRAMS=consortium-message consortium-window-demo

## cheesy hacks I use, don't really have any business existing. ;-)
noinst_PROGRAMS=consortium-mag consortium-grayscale

consortium_message_LDADD= @CONSORTIUM_MESSAGE_LIBS@
consortium_window_demo_LDADD= @CONSORTIUM_WINDOW_DEMO_LIBS@
consortium_mag_LDADD= @CONSORTIUM_WINDOW_DEMO_LIBS@ -lm
consortium_grayscale_LDADD = @CONSORTIUM_WINDOW_DEMO_LIBS@

EXTRA_DIST=$(icon_DATA)

