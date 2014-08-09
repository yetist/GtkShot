AM_CPPFLAGS = \
		$(all_includes) \
		-DGTK_DISABLE_DEPRECATED=1	\
		-DGDK_DISABLE_DEPRECATED=1	\
		-DGDK_PIXBUF_DISABLE_DEPRECATED=1	\
		-DG_DISABLE_DEPRECATED=1	\
		$(X11_CFLAGS) \
		$(GTK_CFLAGS) \
		-I$(top_srcdir) \
		-I$(top_srcdir)/include \
		-I$(top_srcdir)/resource \
		-DPACKAGE_DATA_DIR=\""$(datadir)"\" \
		-DPACKAGE_LOCALE_DIR=\""$(prefix)/$(DATADIRNAME)/locale"\"

bin_PROGRAMS = gtkshot
gtkshot_SOURCES = \
		main.c \
		shot.c \
		toolbar.c \
		pen.c \
		pen-editor.c \
		input.c \
		utils.c
gtkshot_LDADD = $(X11_LIBS) $(GTK_LIBS) -lm
