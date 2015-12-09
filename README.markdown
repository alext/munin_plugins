MythTV
------

`mythtv_backend_stats`

multigraph plugin to generate graphs from the mythtv backend status page.  Generates 2 graphs: the number of active recordings and jobs, and the number of days of guide data.

Virgin Superhub
---------------

`http__superhub`

This parses the Upstream and Downstream Status pages
(`/VmRouterStatus_upstream.asp` and `VmRouterStatus_downstream.asp`) in the
Superhub web interface, and graphs number of locked channels, downstream SNR,
and power levels (both upstream and downstream).

This follows the convention of snmp plugins where the symlink is expected to include the host to monitor between the double underscore.

This has been built and tested for a Superhub version 1.  It may work with the Superhub 2 if the web interface is the same as the Superhub.

TP-Link Router
--------------

These are 2 munin plugins to monitor a TP-Link ADSL router.  They have been developed againse a TD-8840, but they may well work with other versions.

`snmp__tp_link`

This currently generates a traffic graph for the DSL interface.  The SNMP MIB layout is somewhat strange, so the standard `snmp__if_` plugin fails to graph this well (It can't cope with an interface with a speed of 0).

`http__tp_link`

This parses the ADSL stats page within the router's web interface, and graphs the line speed, and SNR (both upstream and downstream).  It reads the env variables `user` and `password` for the username and password to use when connecting to the web interface.  Defaults to 'user' and 'user' which is the default read-only user on the router.

This follows the convention of snmp plugins where the symlink is expected to include the host to monitor between the double underscore.
