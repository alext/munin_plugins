
These are 2 munin plugins to monitor a TP-Link ADSL router.  They have been developed againse a TD-8840, but they may well work with other versions.

`snmp__tp_link`

This currently generates a traffic graph for the DSL interface.  The SNMP MIB layout is somewhat strange, so the standard snmp__if_ plugin fails to graph this well (It can't cope with an interface with a speed of 0.

`http__tp_link`

This parses the ADSL stats page within the router's web interface, and graphs the line speed, and SNR (both upstream and downstream).  It reads the env variables `user` and `password` for the username and password to use when connecting to the web interface.  Defaults to 'user' and 'user' which is the default read-only user on the router.

This follows the convention of snmp plugins where the symlink is expected to include the host to monitor between the dboule underscore.
