# goaccess

[GoAccess](https://github.com/allinurl/goaccess) analyses access logs and reports some interesting insights. 
The Hosts panel which reports abusive bots/crawlers is of interest to me.


## Installing

Get the latest release zip/tar file from [https://github.com/allinurl/goaccess/releases](https://github.com/allinurl/goaccess/releases) and run:

```
tar -xzvf https://github.com/allinurl/goaccess/archive/v1.2.tar.gz
cd v1.2
apt-get install libncurses5-dev libncursesw5-dev
autoreconf -fiv
./configure --enable-utf8 --enable-geoip=legacy
make
make install
```


## Usage

Copy the [goaccess.conf](https://github.com/allinurl/goaccess/blob/master/config/goaccess.conf) file and update it based on the file you'd be analysing. 

* Choose a log format by uncommenting the appropriate `log-format` line. For nginx, default log format is combined.
* Specify the output file by uncommenting the `output` line.
* Ignore any of the panels you aren't interested in by uncommenting the `ignore-panel` lines.


And run:

`goaccess /var/log/nginx/access.log --config-file=/path/to/goaccess.conf`
