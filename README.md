# bibliolog

bibliolog is a tool for real-time viewing in the browser raw logs generated by your proxy (eg EZproxy) and usage events generated by [ezPAARSE](https://github.com/ezpaarse-project/ezpaarse).

It uses
  * [Log.io](http://logio.org/) for logs harvesting and for real-time viewing in the browser raw logs and usage events.
  * [ezpaarse2log.io](https://github.com/ezpaarse-project/ezpaarse2log.io) for real-time listening lines of log comming from log.io-harvester, creating ezPAARSE jobs to generate corresponding usage event and then sending all of this to log.oi-server

<p style="text-align:center">
  <img src="https://docs.google.com/drawings/d/1wx-IudPtbiFurr8FMr84JOEKgfoTSC7DffOu6Ev6RAk/pub?w=828&amp;h=350" />
</p>

## Prerequisites

  * Linux OS
  * apt-get install curl git
  * nodejs:
```shell
curl https://raw.githubusercontent.com/creationix/nvm/v0.5.1/install.sh | sh
nvm install 0.10
nvm use 0.10
nvm alias default 0.10
```

## Installation

Install Log.io as a global command:
```shell
  npm install -g log.io@0.3.2
```

Install ezpaarse2log.io :
TODO
