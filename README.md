# munin-unbound-plugins

Munin plugins for monitoring [Unbound](https://github.com/NLnetLabs/unbound)

# Usage
* Switch to the munin plugin directory
```
cd /usr/share/munin/plugins
```

* Download the plugin
```
sudo wget https://raw.githubusercontent.com/saint-lascivious/munin-unbound-plugins/master/usr/share/munin/plugins/unbound_munin_
```

* Create the symbolic links
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_hits
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_queue
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_memory
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_type
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_class
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_opcode
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_rcode
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_by_flags
```
```
sudo ln -s /usr/share/munin/plugins/unbound_munin_ /etc/munin/plugins/unbound_munin_histogram
```

Or let "munin-node-configure --shell | bash" do it for you.

# Configuration
* Sample setup for '/etc/munin/plugin-conf.d/plugins.conf':
```
[unbound*]
user root
env.statefile /usr/local/var/munin/plugin-state/unbound-state
env.unbound_conf /usr/local/etc/unbound/unbound.conf
env.unbound_control /usr/local/sbin/unbound-control
env.spoof_warn 1000
env.spoof_crit 100000
```

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
