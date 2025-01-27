---
icon: question
---

# Q & A

**Does this plugin support SQLITE?**

Yes.  Replace url with "file" in the config if you want to use sqlite.

Your end result should look like this:

```
Database:
  # For the url, you should only need to replace DATABASE_IP , PORT, and DATABASE_NAME.
  # jdbc:mysql://DATABASE_IP:PORT/DATABASE_NAME
  # replace url with "file" if you want to use sqlite.
  url: "file"
  user: "USERNAME"
  password: "PASSWORD"
```

**Does this plugin support Spigot?**

No. Please use [PaperMC](https://papermc.io/) (or its [forks](https://luminescent.dev/forks/))...&#x20;

**How to bypass the paper warning?**

The paper warning was added in 2.1, it can be bypassed by adding a entry to your config.

Please note, if this warning was shown, things will likely break if bypassed!

No support will be given!

```
BypassPaperWarning: true
```

