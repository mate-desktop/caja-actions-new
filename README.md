18.08.2013 update to 1.6.3

changelog:

- update to follow nautilus-action-3.2.3

- for details see git commits

18.08.2013 update to 1.6.2

changelog:

- fix Copying-DOCS issue,  wrong-file-end-of-line-encoding

2013-08-15 update to 1.6.1

changelog:

- improve debug usage

29.11.2012 update to 1.6.0

changelog:

- complete removal of mateconf usage, needed for distros with MATE 1.6

  without mateconf.
  
Mate Installation
==================
NOCONFIGURE=1 ./autogen.sh

./configure  \

    --with-gtk=2 \

    --disable-scrollkeeper \

    --enable-html-manuals=gdt

make

sudo make install


for Mate-1.4, you need 1.4.0 source

NOCONFIGURE=1 ./autogen.sh

./configure  \

	--disable-schemas-install \

	--with-gtk=2 \

    --enable-mateconf=yes \

    --disable-scrollkeeper \

    --enable-html-manuals=gdt \

    --with-default-io-provider=na-desktop

make

sudo make install
  

Description
==================  
Caja-Actions

  Caja-actions is an extension for Caja file manager which
  allows the user to add arbitrary program to be launched through the
  Caja file manager popup menu of selected files.

Caja-Actions components.

  Caja-Actions has three sort of components:

  - A user interface, caja-actions-config-tool (CACT), which let you
    manage your actions. With CACT, you are able to create, modify and
    delete actions, to define menus and submenus, to order and reorder
    items.
    Import/export functions are also managed via CACT.

  - Caja extensions as dynamically loadable plugins. These extensions
    are automatically loaded by Caja when it starts. For now, two
    extensions are provided:
    . libcaja-actions-menu.so is a plugin which takes care of displaying
      actions in Caja context menus;
    . libcaja-actions-tracker.so is a plugin which tracks the current
      Caja selection, and sends it in response to a DBus request. 

  - Command-line utilities:
    a) installed in PREFIX/bin:
       . caja-actions-new lets you create new actions from the command-line;
       . caja-actions-run lets you execute a predefined action, taking
         into account the current Caja selection via a DBus call to the
         libcaja-actions-tracker plugin;
    b) installed in PKGLIBEXECDIR:
       . na-print-schemas prints the full MateConf schemas on stdout;
       . na-delete-xmltree deletes a tree from a XML file;
       . na-mateconf2keys.sh migrates menus, actions and user preferences from
         MateConf to files.

Caja-Actions plugins.

  I/O Providers.

    Caja-Actions itself uses plugins to load menus and actions from
    the storage space. These plugins are installed in PKGLIBDIR, usually
    something as /usr/lib/caja-actions/.

    Starting with 1.5.0, the preferred default I/O provider is 'na-desktop',
    which means that newly created actions and menus will be stored on
    disk as .desktop files, in accordance with DES-EMA specification [1].

  Importers/Exporters.

    Caja-Actions also relies on plugins to import actions and menus,
    and to export them, in several formats.
    For now, Caja-Actions is able to import/export its items as:
    . MateConf schemas;
    . MateConf dump;
    . XML;
    . .desktop files.

Caja-Actions documentation.

  Documentation is provided in several formats:
  - developer documentation is provided as xml and html files, as generated
    by gtk-doc;
  - CACT user's manuals and general documentation is provided as xml, pdf
    and html files, as generated by mate-doc-utils, docbook-utils or dblatex
    tools.
