Installation
============

## Installing Prerequisite

### TeX Live

Installing the full version of TeX Live is recommended. If you'll be running InTeXration on Ubuntu, [this repository](https://github.com/scottkosty/install-tl-ubuntu) might come in handy.

### Node.JS

Install NodeJS and the node package manager.

```bash
$ sudo apt-get install nodejs
$ sudo apt-get install npm
$ sudo apt-get install nodejs-legacy
```

### MongoDB

Please refer to the MongoDB [documentation](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/).

### Forever

> A simple CLI tool for ensuring that a given node script runs continuously

```bash
$ npm install forever -g
```

## Installing InTeXration Stack

Create a new user called *InTeXration* without shell access and change the current directory to its home folder.

```bash
$ sudo adduser --disabled-login --gecos 'InTeXration' intexration
$ cd /home/intexration
```

### InTeXration-Proxy

Clone the InTeXration-Proxy Repository.

```bash
$ git clone https://github.com/InTeXration/InTeXration-Proxy /home/intexration/InTeXration-Proxy
```

Install the required node packages.

```bash
$ npm install
```

Run the proxy server detached with forever.

```bash
$ forever app.js &
```

### InTeXration-Server

Clone the InTeXration-Server Repository.

```bash
$ git clone https://github.com/InTeXration/InTeXration-Server.git /home/intexration/InTeXration-Server
```

Install the required node packages.

```bash
$ npm install
```

Run the InTeXration server detached with forever.

```bash
$ forever bin/www &
```

### InTeXration-App

Clone the InTeXration-App Repository.

```bash
$ git clone https://github.com/InTeXration/InTeXration-App.git /home/intexration/InTeXration-App
```