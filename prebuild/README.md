# Build your own YunoHost Vagrant box

## Get Debian base boxes

```bash
vagrant box add debian/stretch64
```

## Build YunoHost boxes

Download the vagrant file to build from debian boxes

```bash
wget https://raw.githubusercontent.com/YunoHost/Vagrantfile/stretch/prebuild/Vagrantfile
```

## Run your homemade boxes

Run the box you need by calling `vagrant up DEBIAN_CODENAME-YUNOHOST_VERSION`

```bash
vagrant up stretch-unstable
```

- `DEBIAN_CODENAME`: Only `jessie` for now.
- `DISTRIB`: `stable`, `testing` and `unstable`.

You can now log into your box with `vagrant ssh jessie-stable`

## Package your own boxes

You can package it to use it more quickly later:

```bash
vagrant up stretch-unstable
vagrant package stretch-unstable  --output ./my-yunohost-unstable.box
vagrant box add yunohost/stretch-unstable ./my-yunohost-unstable.box
```
