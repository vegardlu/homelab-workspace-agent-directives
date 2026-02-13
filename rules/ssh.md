---
trigger: always_on
---

* you may ssh into my Ubuntu Server using 'ssh lundedev', I have this config in .ssh/config:

```
Host lundedev
  HostName ssh.lundeberg.cc
  User vegard
  ProxyCommand /opt/homebrew/bin/cloudflared access ssh --hostname %h
```

* Feel free to use git on my server to pull changes