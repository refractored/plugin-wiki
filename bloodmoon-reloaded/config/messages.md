---
description: Lang.yml
---

# Messages

```
messages:
  # Prefix for all messages
  prefix: "<#A50000>Bloodmoon<White> »<reset> "

  confirm-reload: "<yellow>Reloading the plugin will STOP all bloodmoons. To continue anyway, use /bloodmoon reload true."
  reloaded: "<green>Reloaded!"

  # Not all of these are actually used, but they are here incase they are ever needed.
  no-permission: "<red>You don't have permission to do this!"
  not-player: "<red>This command must be run by a player"
  invalid-command: "<red>Invalid command: %usage%"
  number-not-in-range: "<red>Number must be between %min% and %max%, but found: %input%"
  on-cooldown: "<red>You must wait %time% before using this command again."
  invalid-boolean: "<red>Expected true or false, but found: %input%"
  invalid-subcommand: "<red>Invalid subcommand: %input%"
  missing-argument: "<red>You must specify a value for the argument: %parameter%"
  too-many-arguments: "<red>Too many arguments! Correct usage: /%usage%"
  no-subcommand-specified: "<red>You must specify a subcommand."
  invalid-number: "<red>Expected a number, but found ''%input%''."
  invalid-enum: "<red>Invalid %parameter%: %input%"

  # Command messages
  not-a-bloodmoon-world: "<red>This world is not setup to have bloodmoons."
  cannot-stop-permanent: "<red>You cannot stop a permanent bloodmoon."
  bloodmoon-already-active: "<red>A bloodmoon is already active in this world."
  bloodmoon-activated: "<green>A bloodmoon has been activated in this world."
  bloodmoon-deactivated: "<green>A bloodmoon has been deactivated in this world."
  bloodmoon-not-active: "<red>A bloodmoon is not active in this world."
  bloodmoon-remaining: "<green>There are %time% remaining in the bloodmoon."
  bloodmoon-info-time: "<reset>The bloodmoon is currently inactive in %world%. It will start in <reset>%hours%:%minutes%:%seconds%."
  bloodmoon-info-days: "<reset>The bloodmoon is currently inactive in %world%. It will start in <reset>%days% days."
  bloodmoon-info-chance: "<reset>The bloodmoon is currently inactive in %world%. it has a <reset>%chance%% chance to start tonight."
  bloodmoon-info-mirror: "<reset>The bloodmoon is currently inactive in %world%. it will activate when %mirror_world% activates."
  bloodmoon-info-none: "<reset>The bloodmoon is currently inactive in %world%."
  bloodmoon-info-active: "<reset>The bloodmoon is currently active in %world%."
  bloodmoon-manage-days-set: "<green>%world% now has has %days% left until a bloodmoon."
  bloodmoon-manage-days-set-negative: "<red>%world% cannot have a negative number as the result."
  bloodmoon-not-active-world: "<red>A bloodmoon is not active in this world."
  not-a-days-bloodmoon: "<red>This world is not a incrementing days bloodmoon."
  days-bloodmoon-set: "<green>Set the days to %days%."
  bossbar-title: "<red>Bloodmoon"
  cant-modify-active: "<red>You cannot modify the bloodmoon while it is active."
bloodmoon-status:
  active: "<green>Active"
  inactive: "<gray>Inactive"
  activating: "<Blue>Activating"
  
```
