---
description: Lang.yml
---

# Messages

```
# This plugin uses Minimessage formatting.
# For more information on this, see:
# https://docs.advntr.dev/minimessage/format#standard-tags

# Some messages are used by the core plugin, and some are used by extensions.
# Extension messages are only used if the extension for them is installed & enabled.
messages:
  # Common messages
  prefix: "<#A50000>Bloodmoon</#A50000> <white>»</white><reset> "
  no-permission: "<red>You don't have permission to do this!"
  not-player: "<red>This command must be run by a player, or is missing player only arguments."
  not-console: "<red>This command must be run by the console."

  # General Error messages
  # Not all are currently in use, but are here for future use.
  general:
    no-entities-found: "<red>No entities were found."
    no-non-player-entities: "<red>No non-player entities were found."
    more-than-one-entity: "<red>Only one entity is allowed, but the provided selector allows more than one."
    unknown-command: "<red>Unknown command: <yellow>%command%</yellow>."
    missing-argument: "<red>Required argument is missing: <yellow>%argument%</yellow>. Usage: <yellow>%usage%</yellow>"
    number-too-small: "<red><yellow>%parameter%</yellow> too small <yellow>(%input%)</yellow>. Must be at least <yellow>%minimum%</yellow>."
    number-too-large: "<red><yellow>%parameter%</yellow> too small <yellow>(%input%)</yellow>. Must be at least <yellow>%minimum%</yellow>."
    string-too-small: "<red><yellow>%parameter%</yellow> must be at least <yellow>%minimum%</yellow> characters long."
    string-too-long: "<red><yellow>%parameter%</yellow> must be at most <yellow>%minimum%</yellow> characters long."
    list-too-small: "<red>You must input at least <yellow>%minimum%</yellow> entries for <yellow>%parameter%</yellow>."
    list-too-large: "<red>You must input at most <yellow>%maximum%</yellow> entries for <yellow>%parameter%</yellow>."
    expected-string-literal: "<red>Expected: <yellow>%literal%</yellow>, but found: <yellow>%input%</yellow>."
    unclosed-quote: "<red>Unclosed quote. Make sure to close all quotes."
    expected-whitespace: "<red>Expected whitespace to end one argument, but found trailing data."
    invalid-uuid: "<red>Invalid UUID: <yellow>%input%</yellow>."
    invalid-integer: "<red>Invalid integer: <yellow>%input%</yellow>."
    invalid-number: "<red>Invalid number: <yellow>%input%</yellow>."
    invalid-boolean: "<red>Expected <yellow>true</yellow> or <yellow>false</yellow>, but found: <yellow>%input%</yellow>."
    invalid-player: "<red>Invalid Player: <yellow>%input%</yellow>."
    invalid-world: "<red>Invalid World: <yellow>%input%</yellow>."
    invalid-location: "<red>Expected: <yellow>%argument%</yellow>."
    invalid-entity-selector: "<red>Malformed entity selector: <yellow>%input%</yellow>. Error: %error%"
    invalid-escape-character: "<red>Invalid input. Use <yellow>\\</yellow> &cto include a backslash."
    invalid-choice: "Invalid choice: <yellow>%input%</yellow>. Please enter a valid option from the available values."
    invalid-help-single: "<red>Invalid help page: <yellow>%input%</yellow>. Must be <yellow>1</yellow>."
    invalid-help: "<red>Invalid help page: <yellow>%input%</yellow>. Must be between <yellow>1</yellow> and <yellow>%pages%</yellow>."
    invalid-bloodmoon: "<red><yellow>%world%</yellow> is not configured for bloodmoons."
    # Used by the Hordes extension.
    invalid-horde: "<red><yellow>%world%</yellow> is not configured for hordes."

  # Command messages
  deactivate:
    inactive: "<red>A bloodmoon is not active in this world."
    permanent: "<red>You cannot deactivate a permanent bloodmoon."
    success: "<green>Bloodmoon deactivated in <yellow>%world%</yellow>."
  activate:
    already-active: "<red>A bloodmoon is already active in this world."
    success: "<green>Bloodmoon activated in <yellow>%world%</yellow>."
  reload:
    confirm: "<red>Reloading during a active bloodmoon is <dark_red>not recommended</dark_red>. To continue anyway, use <yellow><click:run_command:'/bloodmoon reload true'>/bloodmoon reload true</click></yellow>."
    success: "<green>Reloaded!"
  manage-days:
    active: "<red>You cannot modify the bloodmoon while it is active."
    not-days: "<red>This world is not a incrementing days bloodmoon."
    success: "<green><yellow>%world%</yellow> now has has %days% days left until a bloodmoon."
  remaining:
    success: "<green>There are <yellow>%time%</yellow> remaining in the bloodmoon."
  info:
    active: "<green>Bloodmoon is active in <yellow>%world%</yellow>."
    success:
      none: "<reset>The bloodmoon is currently inactive in <yellow>%world%</yellow>"
      active: "<reset>The bloodmoon is currently active in <yellow>%world%</yellow>."
      time: "<reset>The bloodmoon is currently inactive in <yellow>%world%</yellow>. It will start in <yellow>%hours%:%minutes%:%seconds%</yellow>."
      days: "<reset>The bloodmoon is currently inactive in <yellow>%world%</yellow>. It will start in <yellow>%days%</yellow> days."
      chance: "<reset>The bloodmoon is currently inactive in <yellow>%world%</yellow>. it has a <yellow>%chance%</yellow> chance to start tonight."
      mirror: "<reset>The bloodmoon is currently inactive in <yellow>%world%</yellow>. it will activate when %mirror_world% activates."
  version:
    success:
      version: "<green><yellow>Bloodmoon</yellow> version <yellow>%version%</yellow> by <yellow>%author%</yellow>."
      no-extensions: "<green> No extensions are loaded.<green>"
      extension: "<green><yellow>%name%</yellow> version <yellow>%version%</yellow> by <yellow>%author%</yellow>."
  # Used by extensions.
  spawn:
    # Used by the Hordes extension.
    horde:
      no-players: "<red>No eligible players found. Players in creative or vanish are ignored. Try specifying a player."
      success: "<green>Horde spawned on <yellow>%player%</yellow>."

bloodmoon-status:
  active: "<green>Active"
  inactive: "<gray>Inactive"
  activating: "<Blue>Activating"
```
