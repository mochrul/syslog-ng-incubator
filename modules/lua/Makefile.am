if ENABLE_LUA

module_LTLIBRARIES	  += modules/lua/liblua.la
noinst_LTLIBRARIES        = modules/lua/libluautil.la

modules_lua_liblua_la_CFLAGS		 = \
	$(LUA_CFLAGS)		   \
	$(INCUBATOR_CFLAGS)			   \
	-I$(top_srcdir)/modules/lua		   \
	-I$(top_builddir)/modules/lua

modules_lua_libluautil_la_CFLAGS = \
	$(LUA_CFLAGS) \
	$(INCUBATOR_CFLAGS)			   \
	-I$(top_srcdir)/modules/lua		   \
	-I$(top_builddir)/modules/lua

modules_lua_libluautil_la_SOURCES = \
	modules/lua/lua-msg.h	   	\
	modules/lua/lua-msg.c	   	\
	modules/lua/lua-utils.h	   	\
	modules/lua/lua-utils.c     \
	modules/lua/lua-template.h	   	\
	modules/lua/lua-template.c

modules_lua_libluautil_la_LIBADD		 = \
	$(LUA_LIBS)    \
	$(INCUBATOR_LIBS)

modules_lua_liblua_la_SOURCES		 = \
	modules/lua/lua-grammar.y	   \
	modules/lua/lua-dest.c		   \
	modules/lua/lua-dest.h		   \
	modules/lua/lua-parser.c	   \
	modules/lua/lua-parser.h	   \
	modules/lua/lua-plugin.c

modules_lua_liblua_la_LIBADD		 = \
	$(LUA_LIBS) 			   \
	$(INCUBATOR_LIBS) 
	modules/lua/libluautil.la

modules_lua_liblua_la_LDFLAGS		 = \
	-avoid-version -module -no-undefined

BUILT_SOURCES					+= \
	modules/lua/lua-grammar.y	   \
	modules/lua/lua-grammar.c	   \
	modules/lua/lua-grammar.h

modules/lua mod-lua: modules/lua/liblua.la
else
modules/lua mod-lua:
endif

EXTRA_DIST					+= \
	modules/lua/lua-grammar.ym		   \
	modules/lua/lua-example.conf		   \
	modules/lua/lua-example.lua		   \
	modules/lua/elasticsearch.conf		   \
	modules/lua/elasticsearch.lua

.PHONY: modules/lua mod-lua
