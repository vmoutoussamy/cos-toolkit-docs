
---
title: "Download"
linkTitle: "Download"
weight: 1
date: 2017-01-05
description: >
  How to get cOS vanilla assets: ISOs, Cloud Images, Vagrant boxes, ....
---

cOS-toolkit releases consist on container images that can be used to build derived against and the cos source tree itself.

cOS supports different release channels, all the final and cache images used are tagged and pushed regularly [to Quay Container Registry](https://quay.io/repository/costoolkit/releases-green) and can be pulled for inspection from the registry as well.

Those are exactly the same images used during upgrades, and can also be used to build Linux derivatives from cOS.

For example, if you want to see locally what's in a openSUSE cOS version, you can:

```bash
$ docker run -ti --rm quay.io/costoolkit/releases-green:cos-system-$VERSION /bin/bash
```
 
## Download cOS

You can also try out cOS from the vanilla images and use it to experiment locally or either bootstrap a derivative: those are minimal system with a small package set in order to boot and deploy a container. 

Latest cOS-toolkit releases assets (ISOs, Raw disks, Cloud images) can be found on [Github](https://github.com/rancher-sandbox/cOS-toolkit/releases/), check [Booting](../getting-started/booting) for an explanation of each asset type and how to use it.

cOS can run in: VMs, baremetals and Cloud - the default login username/password is `root/cos`.

### Install

To install run `cos-installer <device>` to start the installation process. Remove the ISO/medium and reboot.

_Note_: `cos-installer` supports other options as well. Run `cos-installer --help` to see a complete help.

## Releases

cOS has 3 variants:

- [green](https://quay.io/repository/costoolkit/releases-green): openSUSE based one, shipping packages from OpenSUSE Leap 15.3 repositories.
- [blue](https://quay.io/repository/costoolkit/releases-blue): Fedora based one, shipping packages from Fedora 33 repositories
- [orange](https://quay.io/repository/costoolkit/releases-orange): Ubuntu based one, shipping packages form Ubuntu 20.10 repositories

We currently support and test only the **green** variant.

## Published AMI images

We publish AMI images for each release, you can find them into ec2 for example with:

```bash
aws ec2 describe-images --filters 'Name=description,Values=cOS*'
```

## What to do next?

Check out [the customization section](../../customizing) to customize `cOS` or [the tutorial section](../tutorials) for some already prepared recipe examples.
