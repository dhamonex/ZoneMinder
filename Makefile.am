AUTOMAKE_OPTIONS = foreign

# And these to the user and group of your webserver
webuser = @WEB_USER@
webgroup = @WEB_GROUP@

sysconf_DATA = \
	zm.conf

SUBDIRS = \
	src \
	web \
	scripts \
	db \
	misc

EXTRA_DIST = \
	zm.conf.in \
	zmconfgen.pl.in

# Yes, you are correct. This is a HACK!
uninstall-hook:
	@-( cd $(DESTDIR)$(webdir); rm -rf events graphics images sounds temp )
	@-( if test "$(DESTDIR)$(ZM_RUNDIR)" != "/var/run"; then rm -rf $(DESTDIR)$(ZM_RUNDIR); fi )
	@-( if test "$(DESTDIR)$(ZM_TMPDIR)" != "/tmp"; then rm -rf $(DESTDIR)$(ZM_TMPDIR); fi )
	@-( if test "$(DESTDIR)$(ZM_LOGDIR)" != "/var/log"; then rm -rf $(DESTDIR)$(ZM_LOGDIR); fi )
