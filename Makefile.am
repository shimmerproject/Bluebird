EXTRA_DIST = \
	LICENSE.CC \
	LICENSE.GPL \
	README.md

MOSTLYCLEANFILES = \
	gtk-3.0/gtk.gresource \
	gtk-3.0/gtk-contained.css \
	gtk-3.0/gtk-contained-dark.css

themedir = $(datadir)/themes/Bluebird

all: clean compile

clean-local:
	rm -rf $(srcdir)/gtk-3.0/.sass-cache

compile:
	$(srcdir)/parse-sass.sh
	glib-compile-resources --sourcedir=$(srcdir)/gtk-3.0 $(srcdir)/gtk-3.0/gtk.gresource.xml

install-data-hook:
	$(MKDIR_P)				$(DESTDIR)$(themedir)
	$(MKDIR_P)				$(DESTDIR)$(themedir)/gtk-3.0

	cp -r $(srcdir)/gtk-2.0			$(DESTDIR)$(themedir)
	cp -r $(srcdir)/gtk-3.0			$(DESTDIR)$(themedir)
#	cp    $(srcdir)/gtk-3.0/gtk.css		$(DESTDIR)$(themedir)/gtk-3.0
#	cp    $(srcdir)/gtk-3.0/gtk.gresource	$(DESTDIR)$(themedir)/gtk-3.0
#	cp    $(srcdir)/gtk-3.0/settings.ini	$(DESTDIR)$(themedir)/gtk-3.0
	cp -r $(srcdir)/metacity-1		$(DESTDIR)$(themedir)
	cp -r $(srcdir)/xfwm4			$(DESTDIR)$(themedir)
	cp    $(srcdir)/index.theme		$(DESTDIR)$(themedir)

uninstall-hook:
	test -e $(DESTDIR)$(themedir) && rm -rfv $(DESTDIR)$(themedir)
