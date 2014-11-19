# chef-server

chef-server is running Chef server 11 on an Ubuntu Trusty 14.04 LTS

This is a fork of: [base/chef-server](https://registry.hub.docker.com/u/base/chef-server/).

## Environment
Chef is running over HTTPS/443 by default.

## Usage
*With log output:*

```
$ docker run --privileged --name chef-server -d -v ~/chef-logs:/var/log -v ~/install-chef-out:/root -p 443:443 kontinuity/chef-server
```

*Just the container:*

```
$ docker run --privileged --name chef-server -d -p 443:443 kontinuity/chef-server
```

Once the Chef server is configured, you download the Knife admin keys here:

```
$ curl -Ok https://IP:443/knife_admin_key.tar.gz
```

Then un-tar that archive and point your knife.rb to the `admin.pem` and `chef-validator.pem` files.
