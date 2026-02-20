---
trigger: always_on
---

# Workflow and Environment

Always consider the following regarding the workflow:

- The root domain is `lundeberg.cc`.
- Work is performed on a MacBook Pro; the server is never run locally on the MacBook.
- The code runs on a personal server equipped with Ubuntu Server 24.04.3 LTS.
- Code is pushed to GitHub and pulled down from the server. **Do not put secrets on GitHub.**
- Docker Compose is used for running the homelab. Several services operate on `lundeberg.cc`, such as `https://home.lundeberg.cc`.
- The homelab functions as the home's hub and server, running services like Home Assistant and various hobby projects.
- Cloudflare Zero Trust is used for secure access.
- You may SSH into the Ubuntu Server using `ssh lundedev`. This configuration exists in `~/.ssh/config`:
  ```text
  Host lundedev
    HostName ssh.lundeberg.cc
    User vegard
    ProxyCommand /opt/homebrew/bin/cloudflared access ssh --hostname %h
  ```
- Feel free to use Git on the server to pull down changes.
