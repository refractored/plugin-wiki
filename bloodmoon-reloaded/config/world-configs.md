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
Length: 360
# Players may be able to skip the night by sleeping in a bed, if this is not enabled.
BedDisabled: true
# If the weather should be set to thunder during a bloodmoon.
SetThunder: true
# Bossbar settings.
Bossbar:
  Title: "<red>Bloodmoon"
  Enabled: true
  Color: RED
  Style: PROGRESS
  Fog: true
  DarkenScreen: true
  # If true, the bossbar will increase with time
  # If false, the bossbar will decrease with time
  Increasing: true
# If bloodmoons should set do daylight cycle to false whenever a bloodmoon is active.
# If this is not enabled, the day may shift during the bloodmoon.
SetDaylightCycle: true
# Should the plugin play a victory chime when the bloodmoon ends?
VictoryChime: true
# Should the plugin have a chance to play a sound every 20 seconds during the bloodmoon?
PeriodicCaveSounds:
  Enabled: true
  # 0.005 = 0.5% Chance to play.
  Chance: 0.005
# If the bloodmoon shouldn't change the time of the world.
# This may break some BloodmoonActivate methods.
# This is useful if you have a plugin that changes the time of the world, or
# The bloodmoon is active in a dimension where time doesn't matter.
DisableChangeTime: false
PlayerDeath:
  ClearInventory: false
  ClearEXP: false
  CustomDeathMessage: false
Messages:
  # If the prefix should be added to the message.
  UsePrefix: false
  ActivationEnabled: true
  ActivationAnnounceGlobal: true
  # %world% = World name
  Activation: "<red>A bloodmoon is upon us."
  DeactivationEnabled: true
  DeactivationAnnounceGlobal: true
  # %world% = World name
  Deactivation: "<green>The Bloodmoon has ended."
  BedDenyMessageEnabled: true
  BedDenyMessage: "<red>You cannot sleep during a bloodmoon."
  # Death messages won't have a prefix added to them, even if UsePrefix is true.
  # %player% = Player's name
  # %player_displayname% = Player's display name
  DeathMessage: "%player% couldn't handle the wrath of the bloodmoon"
# Commands to run on activation or deactivation.
# Do not add a "/" in front of the command.
# %world% will be replaced with the world name.
commands:
  activation: [ ]
  expiry: [ ]

# The method of activating the bloodmoon.
# If "days" is selected, the bloodmoon will activate every x days at night.
# If "timed" is selected, the bloodmoon will activate after a specific time and when the world is night.
# If "chance" is selected, the bloodmoon will activate after a random chance every night.
# If "mirror" is selected, the bloodmoon will activate shortly after another world's bloodmoon activates.
# If "none", or anything else is selected, the bloodmoon will not activate on its own, and must be activated manually.
BloodmoonActivate: Days

#######################################################################################
#  These options only apply if BloodmoonActivate is set to their respective values.   #
#######################################################################################

# There is no built-in paper method to check if a day has passed.
# To get around this the plugin checks every 5 ticks if the time jumped from day to night, then it counts based off that.
# This may not work correctly if you have a plugin that alters the rate of time.
# If BloodmoonActivate isn't set to "Days", this will be ignored.
Days: 5

# The time in seconds until the bloodmoon activates.
# Once the plugin detects that it is night, and the time has passed, the bloodmoon will activate.
# This is especially useful (and recommended) for other dimensions where time does not matter.
# If BloodmoonActivate isn't set to "Timed", this will be ignored.
Timed: 7200
# If the bloodmoon should only activate at night if Timed is enabled.
# This should be disabled if this is in the end or nether.
# If BloodmoonActivate isn't set to "Timed", this will be ignored.
TimedNightOnly: true

# The max value is 1.0, which is 100%.
# The initial chance of the bloodmoon activating.
#   0.05 = 5%,   0.1 = 10%,   1.0 = 100%, etc.
# If BloodmoonActivate isn't set to "Chance", this will be ignored.
Chance: 0.05
# Set true to increment the chance every night the bloodmoon doesn't activate.
ChanceIncrementEnabled: true
# The max and min increment values. The plugin grabs a random value between these two numbers and adds it to the chance.
# If BloodmoonActivate isn't set to "Chance" and ChanceIncrementEnabled isn't true, this will be ignored.
ChanceIncrementMin: 0.05
ChanceIncrementMax: 0.1

# The world to mirror the bloodmoon from, meaning if the bloodmoon is active in this world, it will activate in the mirrored world.
# Reminder: THIS DOES NOT MIRROR THE CONFIG FILES OR THE LENGTH OF THE BLOODMOON.
# Just copy and paste the config above the BloodmoonActivate line to do that.
# If BloodmoonActivate isn't set to "mirror", this will be ignored.
MirrorWorld: "bloodmoonworld"

# Should the bloodmoon ALWAYS be active?
# If this is true the bloodmoon will always be active.
# If BloodmoonActivate isn't to "None", this will be ignored.
NoneStatus: false
```
