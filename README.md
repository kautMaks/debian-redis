# debian-redis

This repository provides redis debianized source package for Debian Stretch.

Source repository - https://salsa.debian.org/lamby/pkg-redis

## Install build requirements:

```
apt-get -qq update && apt-get -y install build-essential debhelper devscripts dpkg-dev fakeroot git libjemalloc-dev procps tcl
```

## Clone this branch to your build server:

```
cd /root
git clone https://github.com/kautMaks/debian-redis.git
```

## Get redis sources:

```
wget http://download.redis.io/releases/redis-4.0.14.tar.gz
tar -xvf redis-4.0.14.tar.gz && mv redis-4.0.14/* debian-redis/
cd  debian-redis/
```

## Build redis with enabled tests:

```
debuild -us -uc -b
```

## Build redis with disabled tests:

```
DEB_BUILD_OPTIONS=nocheck debuild -us -uc -b
```
