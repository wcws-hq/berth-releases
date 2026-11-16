# Berth

**Deploy apps to your own servers, without the usual pain.**

Berth is a self-hosted deployment platform. You point it at a Docker server or a Kubernetes cluster you own, connect an image or a git repository, and Berth builds, deploys and keeps your apps running with automatic HTTPS. Think of it as your own private cloud dashboard that you control completely.

Docs and guides: **https://berth.wcws.net**

## Install

On a fresh Linux server (Ubuntu or Debian, amd64) run:

```bash
curl -fsSL https://berth.wcws.net/install | sudo sh
```

The installer downloads the release, checks its signature and checksum, asks for your domain and email, and starts everything. At the end it prints a one-time link to create your owner account. Takes a few minutes.

You need a server with 2 GB of RAM or more, Docker, a domain name pointing at it, and ports 80, 443 and 4443 open.

## What you get

- **Docker and Kubernetes.** Run apps on plain Docker servers or on Kubernetes clusters, all from one dashboard.
- **Deploy from an image or git.** Push to deploy, roll back in one click.
- **Automatic HTTPS.** Domains and Let's Encrypt certificates are handled for you.
- **Safe releases.** Canary rollouts that watch your health targets and stop a bad release by themselves.
- **Autoscaling and scale to zero.** Add capacity under load and sleep idle apps.
- **Uptime checks and status pages.** Know when something breaks and show your customers a public page.
- **Databases and backups.** Create databases, schedule backups, restore when you need to.
- **Secrets stored encrypted.** Environment variables and keys are encrypted at rest.
- **Secure by design.** Servers connect to the control plane over mutual TLS, commands are signed, and every release is signed and verified before it installs.
- **Team access.** Roles, audit log, two factor sign in and single sign on.
- **Dark, fast interface.** Built to be used all day.

## Verified releases

Every release in this repository is signed. The installer refuses anything that does not match the key built into it, so a tampered download will not install. Updates work the same way, from the dashboard or with `sudo berth update`.

## Add more servers

After the control plane is running, open **Servers > Add server** in the dashboard and run the agent installer on the new machine:

```bash
curl -fsSL https://berth.wcws.net/agent | sudo sh
```

## What is in this repository

Only the signed release files: the installer scripts, the release manifest and the program package. The source code is private.

## Licence

Free to install and use on as many servers as you control, for personal, internal or commercial use, including client work. It is not open source. You may not sell, sublicense, host Berth itself as a service, modify it, reverse engineer it or redistribute the release files. The full terms are in the LICENSE file inside every release package, and the installer asks you to accept them.

## Help

Guides for every feature are at https://berth.wcws.net/docs/.
