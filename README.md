# My personal mac setup

As we have sometimes to format our computer, I decided to automated this process
and let my life less boring.

> That is my personal Mac set up and there are a lot of like this one outside
> there.

# Bootstrap

First of all the softwares have to me installed.  The `bootstrap` script aims to
ensure that gcc, xcode, homebrew, ansible and git will be installed. Then this
script will download this repository and execute the ansible playbooks:

```shell
$ curl -fsSL https://raw.githubusercontent.com/fefas/mac-setup/master/bootstrap | /bin/sh 
```
