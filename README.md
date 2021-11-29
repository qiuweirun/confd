# Update
* forked from kelseyhightower/confd
* 新增模板方法{{getServiceIp}}，获取服务器ip。
* 此方法并不完整，`只能`获取一个非环回地址ip。

# docker版build amd64-linux版
* docker pull golang:1.9-stretch
* docker run -it --name conf-build -v /你的项目目录/confd:/go/src/github.com/kelseyhightower/confd golang:1.9-stretch /bin/bash
* 容器内操作 -> cd /go/src/github.com/kelseyhightower/confd && make build && make install && cp /usr/local/bin/confd /go/src/github.com/kelseyhightower/confd/bin
* 你的“/你的项目目录/confd/bin”内的confd就是你要的文件

# confd

[![Build Status](https://travis-ci.org/kelseyhightower/confd.svg?branch=master)](https://travis-ci.org/kelseyhightower/confd)

`confd` is a lightweight configuration management tool focused on:

* keeping local configuration files up-to-date using data stored in [etcd](https://github.com/coreos/etcd),
  [consul](http://consul.io), [dynamodb](http://aws.amazon.com/dynamodb/), [redis](http://redis.io),
  [vault](https://vaultproject.io), [zookeeper](https://zookeeper.apache.org), [aws ssm parameter store](https://aws.amazon.com/ec2/systems-manager/) or env vars and processing [template resources](docs/template-resources.md).
* reloading applications to pick up new config file changes

## Community

* IRC: `#confd` on Freenode
* Mailing list: [Google Groups](https://groups.google.com/forum/#!forum/confd-users)
* Website: [www.confd.io](http://www.confd.io)

## Building

Go 1.10 is required to build confd, which uses the new vendor directory.

```
$ mkdir -p $GOPATH/src/github.com/kelseyhightower
$ git clone https://github.com/kelseyhightower/confd.git $GOPATH/src/github.com/kelseyhightower/confd
$ cd $GOPATH/src/github.com/kelseyhightower/confd
$ make
```

You should now have confd in your `bin/` directory:

```
$ ls bin/
confd
```

## Getting Started

Before we begin be sure to [download and install confd](docs/installation.md).

* [quick start guide](docs/quick-start-guide.md)

## Next steps

Check out the [docs directory](docs) for more docs.
