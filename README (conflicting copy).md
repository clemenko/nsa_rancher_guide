
https://www.armosec.io/blog/nsa-cisa-kubernetes-hardening-guide/


https://www.cisa.gov/uscert/ncas/current-activity/2022/03/15/updated-kubernetes-hardening-guide




---
title: Taking Advantage of Encryption at Rest with Longhorn
author: Andy Clemenko, @clemenko, andy.clemenko@rancherfederal.com
---

# Taking Advantage of Encryption at Rest with Longhorn

![logo](img/longhorn.jpg)

Data security is becoming an increasing importance with our customers. One of the great features of [Longhorn](https://longhorn.io) is the ability to encrypt the volumes at rest. Meaning the data on the nodes are encrypted. For added security we will want at least three nodes for high availability.

From the [docs](https://longhorn.io/docs/1.3.0/advanced-resources/security/volume-encryption/) : *An encrypted volume results in your data being encrypted while in transit as well as at rest, this also means that any backups taken from that volume are also encrypted.*

We will need a few tools for this guide. We will walk through how to install `helm` and `kubectl`.

Before getting started we should probably take a look at a post for setting up [RKE2, Rancher, and Longhorn](https://github.com/clemenko/rke_install_blog).

---

> **Table of Contents**:
>
> * [Whoami](#whoami)
> * [Prerequisites](#prerequisites)
> * [Linux Servers and Kubernetes](#linux-servers-and-kubernetes)
> * [Longhorn](#longhorn)
>   * [Longhorn Install](#longhorn-install)
>   * [Longhorn Gui](#longhorn-gui)
>   * [Enabling Encryption](#enabling-encryption)
>   * [Using Encryption](#using-encryption)
> * [Automation](#automation)
> * [Conclusion](#conclusion)

---

## Whoami

Just a geek - Andy Clemenko - @clemenko - andy.clemenko@rancherfederal.com

## Prerequisites

The prerequisites are fairly simple. We need a kubernetes cluster with access to the internet. They can be bare metal, or in the cloud provider of your choice. I prefer [Digital Ocean](https://digitalocean.com). We need an `ssh` client to connect to the servers. And finally DNS to make things simple. Ideally we need a URL for the Rancher interface. For the purpose of the this guide let's use `longhorn.rfed.io`. We will need to point that name to the first server of the cluster. While we are at it, a wildcard DNS for your domain will help as well.
