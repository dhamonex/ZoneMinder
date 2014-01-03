AUTOMAKE_OPTIONS = gnu

# This should be set to your web directory
webdir = @WEB_PREFIX@
# And these to the user and group of your webserver
webuser = @WEB_USER@
webgroup = @WEB_GROUP@

SUBDIRS = \
	ajax \
	css \
	graphics \
	includes \
	js \
	lang \
	skins \
	tools \
	views

dist_web_DATA = \
	index.php

# Yes, you are correct. This is a HACK!
install-data-hook:
	@-( cd $(DESTDIR)$(webdir); if ! test -e events; then mkdir events; fi; chmod u+w events )
	@-( cd $(DESTDIR)$(webdir); if ! test -e images; then mkdir images; fi; chmod u+w images )
	@-( cd $(DESTDIR)$(webdir); if ! test -e sounds; then mkdir sounds; fi; chmod u+w sounds )
	@-( cd $(DESTDIR)$(webdir); if ! test -e tools; then mkdir tools; fi; chmod u+w tools )
	@-( cd $(DESTDIR)$(webdir); if ! test -e temp; then mkdir temp; fi; chmod u+w temp )

uninstall-hook:
	@-( cd $(DESTDIR)$(webdir); rm -rf $(SUBDIRS) )
	@-( cd $(DESTDIR)$(webdir); rm -rf events images sounds tools temp )
