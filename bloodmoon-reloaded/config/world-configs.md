---
description: Each world has its own config.
---

# World Configs

```
# The effects that will be active when the bloodmoon is active.
# https://plugins.auxilor.io/effects/configuring-an-effect
effects:
  # Outgoing Damage (Player -> Entity)
  - triggers:
      - melee_attack
      - bow_attack
    filters:
      entities:
        - PLAYER
    mutators:
      - id: dispatcher_as_victim
    effects:
      - id: damage_multiplier
        args:
          multiplier: "0.2"
  # Incoming damage (Entity -> Player)
  - triggers:
      - melee_attack
      - bow_attack
    filters:
      entities:
        - ZOMBIE
        - SKELETON
        - PHANTOM
        - ZOMBIE
    mutators:
      - id: dispatcher_as_victim
    effects:
      - id: damage_multiplier
        args:
          multiplier: "2.0"
  - triggers:
      - entity_death
    effects:
      - id: smite
        args:
          damage: 1
conditions: [ ]

# Length of the bloodmoon in seconds.
length: 360

# The method of activating the bloodmoon.
# If "days" is selected, the bloodmoon will activate every x days at night.
# If "timed" is selected, the bloodmoon will activate after a specific time and when the world is night.
# If "chance" is selected, the bloodmoon will activate after a random chance every night.
# If "mirror" is selected, the bloodmoon will activate shortly after another world's bloodmoon activates.
# If "none" is selected, the bloodmoon will not activate on its own, and must be activated manually.
# The configuration for each method is at the bottom of this file.
activation-method: Days

# If the bloodmoon can only activate when players are in that world.
require-players-world: false

# If the bloodmoon can only activate when players are in the server.
require-players-online: false

on-activation:
  sound:
    enabled: true
    # The sound to play when the bloodmoon activates.
    # https://www.digminecraft.com/lists/sound_list_pc.php
    name: "block.bell.resonate"
    # The volume of the sound.
    volume: 1.0
    # The pitch of the sound.
    pitch: 1.0
  run-commands:
    enabled: false
    # The command to run when the bloodmoon activates.
    # %world% will be replaced with the world name.
    commands:
      - "say Bloodmoon activated in %world%"
  announce:
    enabled: true
    # If the message should be sent to all players on the server.
    # If false, the message will only be sent to players in this world.
    global: false
    # Commands to run on activation or deactivation.
    # Do not add a "/" in front of the command.
    # %world% will be replaced with the world name.
    message: "<red>A bloodmoon is upon us."
  spawn-rate:
    monster:
      # This enables the change of the spawn rate of monsters.
      # If false, the spawn rate will not be changed, and left as is.
      enabled: true
      rate: 25

on-deactivation:
  sound:
    enabled: true
    # The sound to play when the bloodmoon activates.
    # https://www.digminecraft.com/lists/sound_list_pc.php
    name: "ui.toast.challenge_complete"
    # The volume of the sound.
    volume: 1.0
    # The pitch of the sound.
    pitch: 1.0
  run-commands:
    enabled: false
    # Commands to run on activation or deactivation.
    # Do not add a "/" in front of the command.
    # %world% will be replaced with the world name.
    commands:
      - "say Bloodmoon activated in %world%"
  announce:
    enabled: false
    # If the message should be sent to all players on the server.
    # If false, the message will only be sent to players in this world.
    global: false
    # The message to send when the bloodmoon activates.
    # %world% will be replaced with the world name.
    message: "<green>The Bloodmoon has ended."
  weather:
    # If true, the weather will be set.
    # If false, the weather will not be set, and left as is.
    enabled: true
    rain: false
    # If rain is false, this won't do anything.
    thunder: false

while-active:
  beds:
    # Players can still set their spawn point in a bed, but they cannot sleep in it.
    deny-sleep: true
    message: "<red>You cannot sleep during a bloodmoon."
  weather:
    # If true, the weather will be set.
    # If false, the weather will not be set, and left as is.
    enabled: true
    rain: true
    # If rain is false, this won't do anything.
    thunder: true
  on-player-death:
    clear-inventory: false
    clear-exp: false
    custom-death-message: false
  periodic-sounds:
    enabled: true
    # Selects a random sound from the list of sounds.
    # https://www.digminecraft.com/lists/sound_list_pc.php
    sounds:
      - "ambient.cave"
    # 0.005 = 0.5% Chance to play every second.
    chance: 0.005
  bossbar:
    enabled: true
    title: "<red>Bloodmoon"
    # Available colors:
    # BLUE, GREEN, PINK, PURPLE, RED, WHITE and YELLOW
    color: RED
    # For more styles look here:
    # https://jd.advntr.dev/api/4.7.0/net/kyori/adventure/bossbar/BossBar.Overlay.html
    style: PROGRESS
    # Flags for the bossbar.
    # https://jd.advntr.dev/api/4.7.0/net/kyori/adventure/bossbar/BossBar.Flag.html
    flags:
      - DARKEN_SCREEN
      - CREATE_WORLD_FOG
    # If true, the bossbar will increase with time
    # If false, the bossbar will decrease with time
    increasing: true
  # If bloodmoons should set do daylight cycle to false whenever a bloodmoon is active.
  # If this is not enabled, the day may shift during the bloodmoon.
  stop-daylight-cycle: true
  # If the bloodmoon shouldn't change the time of the world.
  # This may break some BloodmoonActivate methods.
  # This is useful if you have a plugin that changes the time of the world, or
  # The bloodmoon is active in a dimension where time doesn't matter.
  disable-time-change: false

#######################################################################################
#  These options only apply if activation-method is set to their respective values.   #
#######################################################################################

# If activation-method isn't set to "days", this section will be ignored.
days:
  # There is no built-in paper method to check if a day has passed.
  # To get around this the plugin checks every 5 ticks if the time jumped from day to night, then it counts based off that.
  # This may not work correctly if you have a plugin that alters the rate of time.
  count: 5


# If activation-method isn't set to "timed", this section will be ignored.
timed:
  # The time in seconds until the bloodmoon activates.
  duration: 7200
  # If the bloodmoon should only activate at night if Timed is enabled.
  # This should be disabled if this is in the end or nether.
  night-only: true


# If activation-method isn't set to "chance", this section will be ignored.
chance:
  # The max value is 1.0, which is 100%.
  # The initial chance of the bloodmoon activating.
  #   0.05 = 5%,   0.1 = 10%,   1.0 = 100%, etc.
  initial-percentage: 0.05
  increment:
    # Set true to increment the chance every night the bloodmoon doesn't activate.
    enabled: true
    # The max and min increment values. The plugin grabs a random value between these two numbers and adds it to the chance.
    min: 0.05
    max: 0.1


# If activation-method isn't set to "mirror", this section will be ignored.
mirror:
  # The world to mirror the bloodmoon from, meaning if the bloodmoon is active in this world, it will activate in the mirrored world.
  # Reminder: THIS DOES NOT MIRROR THE CONFIG FILES OR THE LENGTH OF THE BLOODMOON.
  # Just copy and paste the config above the activation-method line to do that.
  world: "world"


# If activation-method isn't to "none", this section will be ignored.
none:
  # If the bloodmoon should be active when the server starts.
  always-active: false

```
