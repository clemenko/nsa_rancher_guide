---
title: How the NSA Kubernetes Hardening guide applies to Rancher and RKE2
author: Andy Clemenko, @clemenko, andy.clemenko@rancherfederal.com
---

# How the NSA Kubernetes Hardening guide applies to Rancher and RKE2

![logo](img/nsa_banner.jpg)

At a high level, [NSA](https://www.nsa.gov/) and [CISA](https://www.cisa.gov) developed a Kubernetes hardening [guide](https://www.cisa.gov/uscert/ncas/current-activity/2022/03/15/updated-kubernetes-hardening-guide
).

> NSA and CISA developed this document in furtherance of their respective cybersecurity missions, including their responsibilities to develop and issue cybersecurity specifications and mitigations. This information may be shared broadly to reach all appropriate stakeholders.

This article will help apply the recommendations to Rancher and RKE2 (Ranchers Government focused Kubernetes.)

---

> **Table of Contents**:
>
> * [What is the NSA Kubernetes Hardening Guide](#What-is-the-NSA-Kubernetes-Hardening-Guide)
>   * [Why is it important](#Why-is-it-important)
>   * [What’s in it](#What’s-in-it)
> * [How are all K8s not equal](#How-are-all-K8s-not-equal)
> * [Rancher - Secure by default](#Rancher---Secure-by-default)  

---

## What is the NSA Kubernetes Hardening Guide

In March of 2022 the [NSA](https://www.nsa.gov/) released an updated version of the hardening the [Kubernetes Hardening guide](https://www.cisa.gov/uscert/ncas/current-activity/2022/03/15/updated-kubernetes-hardening-guide). We should probably level set a little on what Kubernetes is. From the guide itself.

> Kubernetes® is an open-source system that automates the deployment, scaling, and management of applications run in containers, and is often hosted in a cloud environment.

The guide is designed as minimum standard for hardening Kubernetes against some common attack vectors. Namely supply chain, malicious threat actors and insider threats. The guide covers the best practices for prevent such attacks. The executive summary from the [guide](https://www.cisa.gov/uscert/ncas/current-activity/2022/03/15/updated-kubernetes-hardening-guide) does a good job explaining it.

> This guide describes the security challenges associated with setting up and securing a Kubernetes cluster. It includes strategies for system administrators and developers of National Security Systems, helping them avoid common misconfigurations and implement recommended hardening measures and mitigations when deploying Kubernetes.

### Why is it important

Throughout my career there has always been a disconnect between the documentation and the practical implementation. The Kubernetes ecosystem is no stranger to this problem. Since Kubernetes is open-source there are about a dozen different distributions. Each distribution makes strategic decisions on the deployment details. Some vendors make good choices. Some vendors make bad choices. [Kubernetes Hardening guide](https://www.cisa.gov/uscert/ncas/current-activity/2022/03/15/updated-kubernetes-hardening-guide) is intended to bridge the gap from the initial install to a hardened, secure Kubernetes cluster. It is important to have a guide like this when the advisory never quits.

### What’s in it

The guide covers the topics from a couple of major catagories.

* Kubernetes Pod Policy
* Network Separation and Hardening
* Authentication and Authorization
* Audit Logging and Threat Detection
* Upgrading and Application Security Practices

![rke2 logo](img/examples.jpg)

The guide does a great job showing technical examples for a lot of the topics. Again providing a strong, secure technical foundation.

## How are all K8s not equal

[Kubernetes](https://kubernetes.io/) is open source and free to use by anyone. This is good and bad. Take a look at the [vendor list](https://kubernetes.io/partners/#conformance). However Kubernetes has a slight complexity problem. When vendors take the underlying code and package it they make trade offs. Some vendors lean towards having a complete experience at the cost of security. Some lean towards lock-in of an entire ecosystem. One vendor builds additional object types on top of Kubernetes. Meaning it is very difficult to change distributions. Rancher, and RKE2, lean towards security.

## Rancher - Secure by default

![rke2 logo](img/rke2.png)

What makes Rancher and RKE2 different is the approach towards security. RKE2 was specifically designed around the needs for the federal government. Check out Rancher Government's [Security page](https://ranchergovernment.com/security). We list the current and upcoming STIGs for the Rancher and RKE2.

### Key points from the Guide

