---
description: The main config of the plugin
icon: gear
---

# Config

{% hint style="info" %}
If you're looking for the world config or how to config each world then look [here](world-configs.md).
{% endhint %}

```
#
# Configuration file for the core plugin
#

# Each world has an individual configuration file.
# Check out the "worlds" folder in the plugin's data folder.

# Worlds that have bloodmoons enabled.
# Reload the plugin, and a config file should generate for said worlds.
# Worlds that are prefixed with a "_" are ignored.
worlds-list:
  - world
# If true, the WorldsList will be used as a whitelist.
# If false, the WorldsList will be used as a blacklist.
# If used as a blacklist, all other worlds will have a bloodmoon config created and read. (Including new ones)
whitelist: true
```

