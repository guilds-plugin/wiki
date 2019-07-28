# The Arena System

Hey there,

Guilds is proud to present to you the new War Arena System that will be coming in v3.5.2.

This update is **SO MASSIVE** that I've decided to put the update logs in a single place so that we can avoid any confusion.

In order to help you guys learn about what all has changed, each new major part of the update will have a video and a text-version to tell you about everything!

**Note:** It is super **important** that you read through all these changes so you understand what is changing. There are deep logistical changes happening throughout various parts of the plugin, especially with the GUIs, so you need to read through everything so your GUIs don't break.

Side-Note: A good way to determine who is on each team in the arena would be a plugin such as NameTagEdit.

## New Wiki

Before I get into that, you might also notice we use a new software for the wiki! Thank you so much GitBook for assisting me in moving over from my old software and graciously providing this for us to use.

Now, let's get into the fun stuff of this update.

## New Materials

As of this update, Guilds is now compiled under `1.14.4` in order to allow support for `1.13` and `1.14` materials. When you run the updated jar, there will be a link at the top of the GUI part of the config that shares a link that you can go to in order to see all the materials your can use.

The plugin is designed the have these work on all versions, but if they don't exist, for example, using a `1.14` item on `1.8`, it will just not show up.

**Note:** Most likely there will be a few default items that you will need to update. If you get any console errors saying something like `enum value MATERIAL.BED` doesn't exist, just follow the link in the config to see what material to use instead.

## Language Updates

* Added in a new Czech translation
* German translation updated
* Russian translation updated

## **API Changes**

* Fixed not being able to get the Guild from custom events
* Updated some clarification on some methods
* Implemented GuildRenameEvent
* Implemented GuildBankWithdrawEvent
* Implemented GuildBankDepositEvent
* GuildLeaveEvent now has causes for the reason it happened

## **Arenas**

The arenas by themselves are a massive implementation into the plugin. As a server owner, you will be able to create your own arenas, along with setting the spawn points for each team! Watch the video below to get a better idea of how to manage your arenas.

#### New Commands

* /guild arena set challenger &lt;arena&gt;
* /guild arena create &lt;name&gt;
* /guild arena set defender &lt;arena&gt;
* /guild arena delete &lt;arena&gt;
* /guild arena list
* /guild arena tp &lt;arena&gt; &lt;challenger/defender&gt;

#### Understanding

The new arena system is fairly easy to understand. As an admin of the server, you can create new arenas, set the spawn points for them, teleport to them, list the arenas, and delete the arenas as you see fit.

You have full control of what the arena is and where the team spawn.

**Note:** When I say you have full control, I mean **FULL**, as in, you need to implement your own protection on the arena itself such as a WorldGuard region and allowing PVP, etc.

{% embed url="https://glaremasters.me/tutorials/arenas.mp4" %}

## New Config Additions

In the following video, I will discuss the new config additions that will be coming for the first update of the war arenas. These changes will allow be seen in your config once you launch the update! Keep in mind these are just a few of them and more are to come soon!

#### Understanding

The new updates to the config are fairly easy to understand.

```yaml
war:
    # How often (in minutes) can a guild be the defender in a war?
    # This is to help prevent abuse from guilds fighting each other to farm rewards.
    # This is defaulted to 1 day.
    defend-cooldown: 1440
    # Would you like to block commands while a player is in the war?
    disable-commands: false
    # How long does a defending guild have to accept a war challenge? (In seconds)
    accept-time: 120
    # What is the min number of players needed on each side for a war to start?
    min-players: 3
    # What is the max number of players allowed on each side for a war?
    max-players: 8
    # How long do players of both sides have to join the war? (In seconds)
    join-time: 60
    # How long should we wait to teleport the players and start the war after everyone joined?
    ready-time: 60
    rewards:
        # Would you like to give rewards to the winning guild?
        enabled: false
        # What rewards (commands) would you like to run for the winning Guild?
        # Current supports {player}.
        rewards: 
        - ''
```

{% embed url="https://glaremasters.me/tutorials/config.mp4" %}

## The Challenge

Guild Masters \(and/or Officers\) can challenge other guilds to controlled combat in an arena. The challenge will go through several steps. A\) the challenge, B\) the accept, C\) joining the guild war, and D\) gearing up.

#### New Commands

* /guild war accept
* /guild war challenge &lt;guild&gt;
* /guild war deny
* /guild war join

#### Understanding

There will be three checks before the challenge is created:

1. If the guild has already accepted a defense in the last 24h.
2. If there is an open arena.
3. If there are any members of the defending guild online to accept the challenge.

When a challenge is accepted, an ActionBar will show up to all players in the guild telling them to join the war.

 If there are an uneven number of players _Example: 5 v 3, last two members to have joined on the larger team get kicked from the guild war in order for the team to be 3 v 3_

After the countdown players have another countdown \(_defaulted to one minute_\) in order to equip themselves.

**Note**: Some of the default messages have been updated in order to make it easier to see important details.

## The War

Members of each guild will fight until there is only one guild standing! 

* Each guild will be warped to their respective warps \(challenger for the challengers, and defender for the defenders\) and then the fight will begin.
* Each guild fights to kill members of the other guild to win.
* Each time a guild member is killed they will be warped back to where they originally were.
* Once all the members of one guild are defeated, the opposite guild is declared the winner.
* Rewards will be executed for all players on the winning team if enabled.

## Other Changes / Bug Fixes

* Removed a checksum verification for a certain library throwing errors from time to time
* Fixed a long-term bug that was not handling the damage and mob XP from tiers properly
* Implemented Lazy Loading for the plugin so future guilds won't take up as much disk space
* Fixed an issue that would occur when fighting mobs in certain instances
* Fixed some language typos
* Added in admin command to claim land for guilds.
* Implemented new placeholders for Guild Score!

