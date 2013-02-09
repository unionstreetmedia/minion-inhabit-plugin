Inhabit
=======

A plugin for [Minion](http://github.com/rfreebern/minion). Tell your bot to
inhabit (a.k.a. auto-join on connect, rejoin on kick) specific channels.

Depends on the (built in) DB plugin, connected to a MySQL or SQLite database.

Installation
------------

Place `Inhabit.php` in `plugins/Inhabit/` in your Minion install. If your Minion
install is a git repository, you can

    git submodule add https://github.com/rfreebern/minion-inhabit-plugin.git plugins/Inhabit

from the Minion base directory.

Configuration
-------------

Requires no configuration parameters. To make Minion load the plugin, add

    $this->PluginConfig['Inhabit'] = array();

to your `config.php`.

When first loaded, this plugin will create a table named `Inhabit` in your
database, which it will use to store the list of channels your Minion has
been told to inhabit.

Usage
-----

Assuming your Minion's nickname is `Azazel`:

    Azazel: !inhabit #limbo

makes Azazel immediately join `#limbo` and auto-join it in the future, and

    Azazel: !evict #limbo

makes Azazel immediately leave `#limbo` and stop auto-joining it in the future.

With no channel name, the commands operate on the current channel, e.g.

    Azazel: !inhabit

makes Azazel inhabit the channel in which the command was said, and

    Azazel: !evict

evicts Azazel from the channel in which the command was said.

Issuing these commands in a non-channel context (e.g. a private query) has no
effect.
