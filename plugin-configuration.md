# Plugin Configuration

## Configuration

The `config.yml` will be created on the first server startup.

The config file _should_ automatically update with the new additions added in an update.

```yaml
# Guilds
# Creator: Glare
# Contributors: https://github.com/guilds-plugin/Guilds/graphs/contributors
# Issues: https://github.com/guilds-plugin/Guilds/issues
# Spigot: https://www.spigotmc.org/resources/guilds.48920/
# Wiki: https://wiki.glaremasters.me/
# Discord: https://glaremasters.me/discord
settings:
    announcements:
        # This is used for the Guild's Announcement System, which allow me (The Author) to communicate to you guys without updating.
        # The way this works is very simple. If you have "console" set to "true", you will see the announcement when the server starts.
        # If you have "in-game" set to "true", your OPed players will see it the first time they login to the server.
        console: true
        in-game: true
    # Choosing your language for the plugin couldn't be easier! The default language is english.
    # If you speak another language but don't see it here, feel free to submit it via one of the links above to have it added to the plugin.
    # If you try and use a different language than any in the list above, the plugin will not function in a normal manner.
    # As you can see this is currently en-US, and there is a en-US.yml file in the language folder.
    # If I wanted to switch to french, I would use fr-FR as the language instead.
    messagesLanguage: en-US
    # Would you like to allow admin players to update the languages via command?
    # If yes, set to true, and they will be able to run /guild admin update-languages
    # If no, set to false, and the command will only run via console.
    player-update-languages: false
    # How often (in minutes) do you want all Guild Data to save?
    save-interval: 1
    # Would you like to check for plugin updates on startup? It's highly suggested you keep this enabled!
    update-check: true
hooks:
    # Do we want to hook into Essentials-Chat format to handle guild placeholders?
    essentials-chat: false
    # Do we want to hook into WorldGuard to allow claiming land?
    worldguard-claims: false
guis:
    guild-list:
        # What should the name of the inventory be?
        gui-name: Guild List
        # What should the name of the all the items be in the inventory?
        # Currently supports {player} and {guild}.
        item-name: '&f{player}''s Guild'
        # How should the menu be sorted?
        # LOADED: In the order that the Guilds were loaded on startup
        # TIER: In order from highest tier to lowest tier
        # MEMBERS: In order from most members to least members
        sort: LOADED
        # What should be the default texture url for textures that fail to load in? Refer to the Guild Manage settings to see how to change the texture!
        head-default-url: 7a2df315b43583b1896231b77bae1a507dbd7e43ad86c1cfbe3b2b8ef3430e9e
        # You are free to design this to your liking
        # This is just an example of all the available placeholders that you can use for the lore!
        # Note: With v3.6.7 and on, you can now use {guild-tier-name} for the name of the tier.
        # Also, from v3.6.7 and on, {guild-status} will now apply from what you set for the guild-info GUI for the status being public or private.
        head-lore: 
        - '&cName&8: &a{guild-name}'
        - '&cPrefix&8: &a{guild-prefix}'
        - '&cMaster&8: &a{guild-master}'
        - '&cStatus&8: &a{guild-status}'
        - '&cTier&8: &a{guild-tier}'
        - '&cBalance&8: &a{guild-balance}'
        - '&cMember Count&8: &a{guild-member-count}'
    guild-buffs:
        # What should the name of the inventory be?
        gui-name: Guild Buffs
        # Do we want to allow users to have more than one buff at a time?
        buff-stacking: false
        buffs:
            haste:
                # What do you want to name the buff?
                name: '&a&lSubstance of the Redmod Graff'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: FEATHER
                # What type of potion is this?
                type: FAST_DIGGING
                # You can put as much as you want here
                description: 
                - '&aType » &7Haste'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 0
            speed:
                # What do you want to name the buff?
                name: '&a&lBlessing of the Cheetah'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: SUGAR
                # What type of potion is this?
                type: SPEED
                # You can put as much as you want here
                description: 
                - '&aType » &7Speed'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 1
            fire-resistance:
                # What do you want to name the buff?
                name: '&a&lScales of the Dragon'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: BLAZE_POWDER
                # What type of potion is this?
                type: FIRE_RESISTANCE
                # You can put as much as you want here
                description: 
                - '&aType » &7Fire-Resistance'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 2
            night-vision:
                # What do you want to name the buff?
                name: '&a&lEyes of the Lurking Demon'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: REDSTONE_TORCH_ON
                # What type of potion is this?
                type: NIGHT_VISION
                # You can put as much as you want here
                description: 
                - '&aType » &7Night-Vision'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 3
            invisibility:
                # What do you want to name the buff?
                name: '&a&lFeet of the Ghostly Walker'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: EYE_OF_ENDER
                # What type of potion is this?
                type: INVISIBILITY
                # You can put as much as you want here
                description: 
                - '&aType » &7Invisibility'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 4
            strength:
                # What do you want to name the buff?
                name: '&a&lMighty Strength of the Pouncing Lion'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: DIAMOND_SWORD
                # What type of potion is this?
                type: INCREASE_DAMAGE
                # You can put as much as you want here
                description: 
                - '&aType » &7Strength'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 5
            jump:
                # What do you want to name the buff?
                name: '&a&lBounce of the Quick Witted Rabbit'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: DIAMOND_BOOTS
                # What type of potion is this?
                type: JUMP
                # You can put as much as you want here
                description: 
                - '&aType » &7Jump'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 6
            water-breathing:
                # What do you want to name the buff?
                name: '&a&lLungs of the Albino Shark'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: BUCKET
                # What type of potion is this?
                type: WATER_BREATHING
                # You can put as much as you want here
                description: 
                - '&aType » &7Water-Breathing'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 7
            regeneration:
                # What do you want to name the buff?
                name: '&a&lIntegrity of the Mystic Witch'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: EMERALD
                # What type of potion is this?
                type: REGENERATION
                # You can put as much as you want here
                description: 
                - '&aType » &7Regeneration'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 8
    # Here you can control what the GUI looks like that allows players to choose which vault to open
    # You can do things like set the name of the gui, the material to use, material name, and lore!
    vault-picker:
        # What do you want the name of the gui to be?
        # Currently supports {name} for the name of the guild.
        name: '&8» &r{name}''s Vaults'
        # How many rows would you like to display?
        rows: 1
        # What do you want the material of the vaults to be?
        item-material: CHEST
        # WHat do you want the name of the vault to be?
        # I recommend keeping this blank so that we can put the vault number in the lore.
        item-name: ' '
        item-lore: 
        - '&8• &7Vault &9#{number}'
        - '&8• &7Status: {status}'
        - ''
        # What do you want to show when a vault is unlocked?
        unlocked: '&9Unlocked'
        # What do you want to show when a vault is locked?
        locked: '&c&mLocked&r'
    vault:
        # What do you want the name of the Vault to be?
        # Note: This requires a restart to change the inventory names.
        name: '&8» &rGuild Vault'
        blacklist:
            # What materials would you like to blacklist from being put into the vaults?
            materials: 
            - ''
            # What custom names of items would you like to blacklist from being put into the vaults?
            names: 
            - ''
            # What custom lore do you want to blacklist from being put into the vaults?
            # Please keep in mind this can be prove to false-positives so please let me know if you have issues.
            # This will currently loop through your lore to check for any strings you have in the list to check.
            # Improvements will be made over time. Thanks for your patience and suppport in advanced.
            lores: 
            - ''
    # Welcome to the Guild Info GUI section of the config.
    # Here you can modify the configuration of what the Guild Info GUI looks like.
    # This can be used by any member of a Guild and shows key information of the Guild.
    # You can see things like the members, the balance, tier, etc.
    guild-info:
        # What would you like the name of the GUI to be?
        # Currently supports {name} for the name of the guild and {prefix} for the prefix of the guild
        name: '&8» &r{name}''s Info'
        # What material do you want the tier button to be?
        tier-material: DIAMOND
        # What do you want the name of the tier button to be?
        tier-name: '&3Guild Tier'
        # What do you want the lore of the tier button to be?
        tier-lore: 
        - '&8• &7Level: &b{tier}'
        # Would you like to display this button?
        tier-display: true
        # What material do you want the bank button to be?
        bank-material: GOLD_INGOT
        # What do you want the name of the bank button to be?
        bank-name: '&6Guild Bank'
        # What do you want the lore of the bank button to be?
        bank-lore: 
        - '&8• &7Balance: &e{current} &7/ &e{max}'
        # Would you like to display this button?
        bank-display: true
        # What material do you want the members button to be?
        members-material: IRON_HELMET
        # What do you want the name of the members button to be?
        members-name: '&5Guild Members'
        # What do you want the lore of the members button to be?
        members-lore: 
        - '&8• &7Members: &d{current} &7/ &d{max}'
        - '&8• &7Online: &d{online} &7/ &d{current}'
        - ''
        - '&7Click to view members!'
        # Would you like to display this button?
        members-display: true
        status-material:
            # What material do you want the status button to be when a guild is public?
            public: EMERALD
            # What material do you want the status button to be when a guild is private?
            private: REDSTONE
        # What do you want the name of the status button to be?
        status-name-item: '&2Guild Status'
        status-name:
            # What do you want the status to say if it's public?
            public: '&aPublic'
            # What do you want the status to say if it's private?
            private: '&cPrivate'
        # What do you want the lore of the status button to be?
        status-lore: 
        - '&8• &7Status: &r{status}'
        # Would you like to display this button?
        status-display: true
        # What material do you want the home button to be?
        home-material: BED
        # What do you want the name of the home button to be?
        home-name: '&cGuild Home'
        # What do you want the lore of the home button to be?
        home-lore: 
        - '&8• &7Home: &f{coords}'
        # Would you like to display this button?
        home-display: true
        # What do you want it to say when a guild doesn't have a home set?
        home-empty: '&fNot Set'
        # Do you want players to be teleported to their guild home when they click this?
        home-teleport: false
        # What material do you want the vault button to be?
        vault-material: CHEST
        # What do you want the name of the home button to be?
        vault-name: '&9Guild Vaults'
        # What do you want the lore of the vault button to be?
        vault-lore: 
        - '&7Click here to open your guild vaults!'
        # Would you like to display this button?
        vault-display: true
        # What material do you want the motd button to be?
        motd-material: SIGN
        # What do you want the name of the motd button to be?
        motd-name: '&6Guild MOTD'
        # What do you want the lore of the motd button to be?
        motd-lore: 
        - '{motd}'
        # Would you like to display this button?
        motd-display: true
    # This part of the config controls what the members gui looks like.
    # You can get to this in game by clicking on the members icon via the guild info gui.
    guild-info-members:
        # What would you like the name of the GUI to be?
        name: '&8» &rMembers of {name}'
        item:
            # What material do you want to use to represent members?
            material: EMPTY_MAP
            # What do you want the name of the item to be?
            name: ' '
            # What do you want the lore of the item to be?
            lore: 
            - '&8• &7Name: &a{name}'
            - '&8• &7Role: &a{role}'
            - '&8• &7Status: {status}'
            - ''
            # What do you want to be what shows when a member is online?
            online: '&aOnline'
            # What do you want to be what shows when a member is offline?
            offline: '&cOffline'
guild:
    requirements:
        # With the default RegEx currently set, the minimum length of the prefix is 1 and the maximum is 64.
        # To change this, adjust the number and you can refer to the link below on how to modify RegEx.
        # RegEx (https://en.wikipedia.org/wiki/Regular_expression) used to only allow certain characters (default only allows alphanumeric characters).
        # To turn off the ability to use colors, remove the & from the RegEx.
        # Trying to use symbols such as Chinese ones? Try this Regex: [\u4E00-\u9FA5_a-zA-Z0-9&_\一-龥]{1,6}
        name: '[a-zA-Z0-9&]{1,64}'
        # Similar to the name, just refer above.
        prefix: '[a-zA-Z0-9&]{1,20}'
    # Would you like to allow players to make a guild without a prefix?
    disable-prefix: false
    blacklist:
        # Do we want to enable the blacklist?
        enabled: true
        # What words would you like to blacklist from being used?
        words: 
        - crap
        - ass
        - stupid
    format:
        # This is the style used when a message sent in guild chat.
        # As of 3.4.7, this now supports {display-name} to show the display name of a player.
        chat: '&7&l[Guild Chat]&r &b[{role}&b]&r &b {player}: {message}'
        # Similar to the one above, just for the admins spying.
        spy: '&7&l[Guild Spy]&r &b[{guild}&b]&r &b[{role}&b]&r &b {player}: {message}'
        # Used for {GUILD_FORMATTED} and %guilds_formatted%
        placeholder-design:
            # The left bracket in the placeholder
            left-bracket: '['
            # The content of the placeholder. Either will be {name} or {prefix}
            content: '{name}'
            # What to show instead of the placeholder if there's no guild
            no-guild: ''
            # The right bracket in the placeholder
            right-bracket: ']'
    damage:
        # Do we want people in the same guild to be able to damage each other?
        guild: false
        # Do we want allies to be able to damage each other?
        ally: false
        # Do we want to respect WorldGuard flags for PVP deny?
        # This will be checked first before checking same guild and ally.
        # This is ONLY needed if you have either of the above two options to set true.
        # ONLY PUT THIS ON TRUE IF YOU HAVE WORLDGUARD INSTALLED OR YOU WILL BREAK STUFF
        respect-wg-pvp-flag: false
    # Would you like to send players their guild's motd on login?
    motd-on-login: true
war:
    # How long does a defending guild have to accept a war challenge? (In seconds)
    accept-time: 120
    # What is the min number of players needed on each side for a war to start?
    min-players: 1
    # What is the max number of players allowed on each side for a war?
    max-players: 8
    # How long do players of both sides have to join the war? (In seconds)
    join-time: 20
    # How long should we wait to teleport the players and start the war after everyone joined?
    ready-time: 20
timers:
    cooldowns:
        # How often (in seconds) can a player set their guild home?
        sethome: 60
        # How often (in seconds) can a player go to their guild home?
        home: 60
        # How often (in seconds) can a player request to join a guild?
        request: 60
        # How often (in seconds) can a guild buy a buff?
        buff: 60
        # How long should a user have to wait before joining a new guild after leaving one?
        join: 120
    warmups:
        home:
            # Do you want to enable making players stand still before teleporting?
            enabled: false
            # How long should a user have to stand still before teleporting?
            time: 3
cost:
    # How much should it cost to create a guild?
    creation: 0.0
    # How much should it cost to set the cost of the guild home?
    sethome: 0.0
# This section of the config will allow you to handle guild land claiming.
# Remember that the enable / disable for this is the WorldGuard Hook at the TOP of the config.
# There are multiple options when it comes to guild claims. For the time being, all guilds will only get one claim.
claims:
    # This is the number of blocks around the player it will try to create the region.
    # Keep in mind this is the RADIUS, it will go this many blocks in both directions.
    # For example, if you take the default 15, it'll do 30 total as it will go 15 blocks in both directions.
    # This is a CUBOID region, not SPHERE.
    radius: 15
    # Customize the entrance and exit message of joining claims.
    # Supports {prefix} for guild prefix and {guild} for guild name.
    # Also supports color codes!
    enter-message: '&aNow entering &d{guild}''s &aclaim!'
    exit-message: '&aNow leaving &d{guild}''s &aclaim!'
    # Would you like to disable guild claiming in specific worlds?
    disabled-worlds: 
    - ''
    # Would you like to enable claim signs?
    # Format - 
    # First Line: [Guild Claim]
    # Second Line: WorldGuard Region Name
    # Third Line: Price
    claim-signs: false
    # Would you like to make it so that claims can only be aquired through the purchasing with signs?
    # This will disable the regular claim commands.
    force-claim-signs: false
tablist:
    # Should the plugin use the built-in tablist?
    enabled: false
    # Would you like to display a user's display name instead of their MC username?
    display-name: false
    # Change how the Prefixes in the TabList show!
    # Note: DO NOT REMOVE THE {guild}
    # You can use {prefix} to show the Guild Prefix instead if you would like.
    format: '&7[&b{guild}&7]&r'
tickets:
    # What do you want the name of the upgrade ticket to be?
    name: '&bGuild Upgrade Ticket'
    # What do you want the lore of the ticket to be?
    lore: 
    - '&dRight click this ticket to upgrade your guild tier!'
    # What do you want the material of the ticket to be?
    material: PAPER
codes:
    # How long do you want the default length of guild codes to be?
    length: 7
    # Do you want inactive codes (no uses left) to display on the /guild code list?
    list-inactive-codes: true
    # What is the max amount of active codes you would like to allow per guild?
    amount: 10
# This section of the config will talk about various parts of upgrading a guild and allow you to choose how it works.
# For "mob-xp-multiplier" the default is 1, meaning that it will drop the normal amount of XP for non-upgraded guilds.
# DO NOT set it to 0, that will either throw errors or cause mobs to not drop XP.
# Keep in mind for the damage-multiplier, it applies to players also, so by default it's set to normal for every tier.
tiers:
    # Should permissions carry over between tiers?
    carry-over: true
    list:
        1:
            # Which level tier is this? 1 is the default.
            level: 1
            # What is the name of this tier?
            name: Bronze
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 0.0
            # How many members can be in a guild of this tier?
            max-members: 15
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 1
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 1.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 10000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here
        2:
            # Which level tier is this? 1 is the default.
            level: 2
            # What is the name of this tier?
            name: Silver
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 200.0
            # How many members can be in a guild of this tier?
            max-members: 30
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 2
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 2.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 20000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here
        3:
            # Which level tier is this? 1 is the default.
            level: 3
            # What is the name of this tier?
            name: Gold
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 300.0
            # How many members can be in a guild of this tier?
            max-members: 50
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 3
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 3.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 30000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here
roles:
    0:
        name: GuildMaster
        permission-node: guilds.roles.master
        permissions:
            activate-buff: true
            add-ally: true
            ally-chat: true
            change-home: true
            change-prefix: true
            rename: true
            chat: true
            demote: true
            deposit-money: true
            invite: true
            kick: true
            open-vault: true
            promote: true
            remove-ally: true
            remove-guild: true
            toggle-guild: true
            transfer-guild: true
            upgrade-guild: true
            withdraw-money: true
            claim-land: true
            unclaim-land: true
            destroy: true
            place: true
            interact: true
            create-code: true
            delete-code: true
            see-code-redeemers: true
            modify-motd: true
            initiate-war: true
    1:
        name: Officer
        permission-node: guilds.roles.officer
        permissions:
            activate-buff: false
            add-ally: true
            ally-chat: true
            change-home: true
            change-prefix: false
            rename: false
            chat: true
            demote: true
            deposit-money: true
            invite: true
            kick: true
            open-vault: true
            promote: true
            remove-ally: true
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: true
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: true
            delete-code: true
            see-code-redeemers: true
            modify-motd: false
            initiate-war: true
    2:
        name: Veteran
        permission-node: guilds.roles.veteran
        permissions:
            activate-buff: false
            add-ally: false
            ally-chat: true
            change-home: false
            change-prefix: false
            rename: false
            chat: true
            demote: false
            deposit-money: true
            invite: true
            kick: false
            open-vault: true
            promote: false
            remove-ally: false
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: false
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: false
            delete-code: false
            see-code-redeemers: false
            modify-motd: false
            initiate-war: false
    3:
        name: Member
        permission-node: guilds.roles.member
        permissions:
            activate-buff: false
            add-ally: false
            ally-chat: true
            change-home: false
            change-prefix: false
            rename: false
            chat: true
            demote: false
            deposit-money: true
            invite: false
            kick: false
            open-vault: true
            promote: false
            remove-ally: false
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: false
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: false
            delete-code: false
            see-code-redeemers: false
            modify-motd: false
            initiate-war: false

```

