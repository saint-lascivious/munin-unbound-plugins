# munin-unbound-plugins

Munin plugins for monitoring [Unbound](https://github.com/NLnetLabs/unbound)

## Automated Installation
Automated installation script for Debian/Ubuntu derivatives

Note: Automated installation is in its infacy right now and not particularly well tested

* Download the munin-pihole-plugins script
```
wget https://raw.githubusercontent.com/saint-lascivious/unbound-pihole-plugins/master/script/unbound-pihole-plugins
```
* Ensure it is executable
```
chmod +x unbound-pihole-plugins
```
* Install unbound-pihole-plugins
```
./unbound-pihole-plugins --install
```
For detailed usage information use
```
./unbound-pihole-plugins --help
```

## Manual Installation
* Install Munin
See the instructions in my [lighttpd-external-munin-proxy](https://github.com/saint-lascivious/lighttpd-external-munin-proxy) repository

* Download the plugin
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/munin-unbound-plugins/master/usr/share/munin/plugins/unbound_munin_ -P /usr/share/munin/plugins
```

* Ensure it is executable
```
sudo chmod a+x /usr/share/munin/plugins/unbound_munin_*
```

* Create any/all desired symbolic links
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_class
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_flags
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_type
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_opcode
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_rcode
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_histogram
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_hits
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_memory
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_queue
```

* Restart Munin services
```
sudo systemctl restart munin munin-node
```

## Configuration

The default configuration should Just Work. If you have a non-standard configuration, you can do one of the following.

* Sample setup for `/etc/munin/plugin-conf.d/unbound`:
```
[unbound*]
    user root
    env.unbound_conf /etc/unbound/unbound.conf
    env.unbound_control /usr/sbin/unbound-control
    env.spoof_warn 100
    env.spoof_crit 1000
```

* Download and edit a sample `/etc/munin/plugin-conf.d/unbound` file from this repo:
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/munin-unbound-plugins/master/etc/munin/plugin-conf.d/unbound -P /etc/munin/plugin-conf.d
```

## Help! My graphs aren't showing up!

* Be patient

Graphs should be generated at five minute intervals. If you still do not see graphs after this time, try restarting the machine and waiting a further five minutes. If you still can not get any graphs to display, contact me for further support.

## Contact
* Discord
[SaintLascivious](https://discord.gg/NC7taVyn)

* Email
saint@sainternet.xyz

* IRC
[##saint-lascivious](https://webchat.freenode.net/##saint-lascivious)

* Reddit
[saint-lascivious](https://www.reddit.com/user/saint-lascivious)

![alt text][logo]

[logo]:https://vignette.wikia.nocookie.net/pokemon/images/7/76/265Wurmple.png "Using the spikes on its rear end, Wurmple peels the bark off trees and feeds on the sap that oozes out. This Pokémon's feet are tipped with suction pads that allow it to cling to glass without slipping."

## Related projects
* [lighttpd-external-munin-proxy](https://github.com/saint-lascivious/lighttpd-external-munin-proxy)

lighttpd external.conf for Munin webserver proxy

* [munin-pihole-plugins](https://github.com/saint-lascivious/munin-pihole-plugins)

Munin monitoring plugins for Pi-hole

* [Munin](https://github.com/munin-monitoring/munin)

Main repository for munin master / node / plugins

* [Pi-hole](https://github.com/pi-hole/pi-hole)

A black hole for Internet advertisements

* [Unbound](https://github.com/NLnetLabs/unbound)

Unbound is a validating, recursive, caching DNS resolver.
