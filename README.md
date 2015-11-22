# nagios-plugin-check_btc_miner
Nagios plugin to monitor Bitcoin Miner performance


Dependencies
- Getopt::Long Perl module
- Nagios::Plugin Perl Module
- DateTime Perl Module


# Installation
- Copy the check_btc_miner to your nagios plugin folder and set executable
- Add a line to your nrpe.cfg file
```
command[check_btc_miner]=sudo /usr/lib/nagios/plugins/check_btc_miner --hash_rate_current=300Mh/s,200Mh/s
```
- If the syslog file that your miner outputs to can only be read by root, Add a line to your sudoers config to allow nagios to read your syslog
```
nagios    ALL=(ALL) NOPASSWD:/usr/lib/nagios/plugins/check_btc_miner
```

# Supported configurations
At present only bfgminer/cgminer is supported

Some checks aren't available on all miners, run with the --help switch to see more information

# Examples

- Run with the --help argument to see all options
```
check_btc_miner --help
```

- Basic example
```
check_btc_miner --hash_rate_current=300Mh/s,200Mh/s
```
- Different syslog file
```
check_btc_miner --hash_rate_current=300Mh/s,200Mh/s --log=/var/log/otherlogfile
```

# Future Work
- Support for other miners such as cpuminer
- Create check for average hash rates

# Site
- https://github.com/alasdairkeyes/nagios-plugin-check_btc_miner

# Author
- Alasdair Keyes - https://akeyes.co.uk/


License
- Released under GPL V3 
  See included LICENSE file

