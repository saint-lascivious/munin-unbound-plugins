# munin-unbound-plugins

Munin plugins for monitoring [Unbound](https://github.com/NLnetLabs/unbound)

## Install Munin
* See the instructions in my [lighttpd-external-munin-proxy](https://github.com/saint-lascivious/lighttpd-external-munin-proxy) repository

## Usage
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

* Restart Munin services
```
sudo systemctl restart munin munin-node
```

## Help! My graphs aren't showing up!

* Be patient

Graphs should be generated at five minute intervals. If you still do not see graphs after this time, try restarting the machine and waiting a further five minutes. If you still can not get any graphs to display, contact me for further support.

## Configuration

The default configuration should Just Work. If you have a non-standard configuration, you can do one of the following.

* Edit the existing `plugins.conf` file

* Sample setup for '/etc/munin/plugin-conf.d/plugins.conf':
```
[unbound*]
    user root
    env.unbound_conf /etc/unbound/unbound.conf
    env.unbound_control /usr/sbin/unbound-control
    env.spoof_warn 100
    env.spoof_crit 1000
```

* Download and edit a sample `plugins.conf` file from this repo:
```
wget https://raw.githubusercontent.com/saint-lascivious/munin-unbound-plugins/master/etc/munin/plugin-conf.d/plugins.conf -q -O - | sudo tee /etc/munin/plugin-conf.d/plugins.conf
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
