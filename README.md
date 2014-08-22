# BiblioLog

BiblioLog is a tool for real-time viewing in the browser raw logs generated by your proxy (eg EZproxy) and usage events generated by [ezPAARSE](https://github.com/ezpaarse-project/ezpaarse).

It uses
  * [Log.io](http://logio.org/) for logs harvesting and for real-time viewing in the browser raw logs and usage events.
  * [ezpaarse2log.io](https://github.com/ezpaarse-project/ezpaarse2log.io) for real-time listening lines of log comming from log.io-harvester, creating ezPAARSE jobs to generate corresponding usage event and then sending all of this to log.oi-server

<p align="center">
<img src="https://docs.google.com/drawings/d/1wx-IudPtbiFurr8FMr84JOEKgfoTSC7DffOu6Ev6RAk/pub?w=828&amp;h=350" />
</p>

## Prerequisites

  * Linux OS
  * apt-get install curl git
  * nodejs:
```bash
curl https://raw.githubusercontent.com/creationix/nvm/v0.5.1/install.sh | sh
nvm install 0.10
nvm use 0.10
nvm alias default 0.10
```
  * Install Log.io as a global command on the server where your logs are located and on the serveur where bibliolog is installed :
```bash
npm install -g log.io@0.3.2
```
  * Install ezpaarse and run it :
```bash
git clone https://github.com/ezpaarse-project/ezpaarse.git
cd ezpaarse/
git checkout `git describe --tags --abbrev=0`
make
echo "{ "EZPAARSE_NODEJS_PORT": 40010 }" > config.local.json
make start
```

## Installation

```bash
git clone git@github.com:ezpaarse-project/bibliolog.git
cd bibliolog/
npm install -g forever

git clone git@github.com:ezpaarse-project/ezpaarse2log.io.git
cd ezpaarse2log.io/
npm install
echo "module.exports = {
  ezpaarse: 'http://127.0.0.1:40010'
};" > ./config.local.js
```

## Running BiblioLog

### Start

```bash
./etc/init.d/bibliolog start
```

### Status

```bash
./etc/init.d/bibliolog status
```

### Stop

```bash
./etc/init.d/bibliolog stop
```

### Log files

```bash
tail -f ./logs/ezpaarse2log.io-stderr.log
tail -f ./logs/ezpaarse2log.io-stdout.log
tail -f ./logs/log.io-server-stderr.log
tail -f ./logs/llog.io-server-stdout.log
```
