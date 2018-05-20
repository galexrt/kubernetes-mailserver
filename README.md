# kubernetes-mailserver
Work in progress! Mail server in Kubernetes.

## Goal
The goal is to build images and manifests to be able to run scalable Mailserver in Kubernetes (e.g. scale as you need).
The main focus is to be able to run and scale this project in Kubernetes.

What is not the goal is to provide an interface to manage users, domains, etc for the actual mailserver.

For my personal use of this, I'm especially looking into using OAuth2 for the authentication in the end for the mailserver (and other components).

## Tasks
- [ ] Write first Postfix and Dovecot config (first prototype will just use a static user file instead of a database)
- [ ] Add rspamd as Spam scanner
- [ ] Add ClamAV for virus scanner

## Requirements
* Either PersistentVolume `ReadWriteMany` or a shared FS, like CephFS.
* Either Service's with `LoadBalancer` or an Ingress controller that also allows TCP port expose (e.g. nginx-ingress).
* Domain (Provider must allow more than one MX record to be set for high availability).

## Limitations
Looking at scaling, you will probably be hit by the shared FS being the bottleneck.
I suggest to look at [@dalgaaf](https://github.com/dalgaaf) presentation about using Ceph as an email storage: https://www.slideshare.net/dalgaaf/email-storage-with-ceph.
