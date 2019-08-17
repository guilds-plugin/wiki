# Developer API

## Hooking Into the API

Obtaining the instance of the API is pretty simple by using the singleton that provides static access to the class. You can obtain the instance of the API through the main `Guilds` class.

```java
GuildsAPI api = Guilds.getApi();
```

## Using the API

The API can be used for obtaining a bunch of information from the plugin. You can browse over the following section to see what all is provided.

### Getting a Guild object

We provide a few ways to obtain a Guild object, so feel free to use what is easiest for you.

#### Using OfflinePlayer

```java
    /**
     * Get the guild of a player
     * @param player the players you're getting the guild of
     * @return the guild that the player is in
     */
    public Guild getGuild(@NotNull OfflinePlayer player) {
        return guildHandler.getGuild(player);
    }
```

**Using Guild UUID**

```java
    /**
     * Get a guild by it's uuid
     * @param uuid uuid of the guild
     * @return the guild the uuid belong to
     */
    public Guild getGuild(@NotNull UUID uuid) {
        return guildHandler.getGuild(uuid);
    }
```

**Using Player name**

```java
    /**
     * Get a guild by it's name
     * @param name the name of the guild
     * @return the guild object
     */
    public Guild getGuild(@NotNull String name) {
        return guildHandler.getGuild(name);
    }
```

### Getting a Guild Vault

```java
    /**
     * Get a copy of one of a guild's vaults
     * @param guild the guild to get the vault of
     * @param vaultNumber which vault to get
     * @return guild vault
     */
    public Inventory getGuildVault(@NotNull Guild guild, int vaultNumber) {
        return guildHandler.getGuildVault(guild, vaultNumber);
    }
```

### Getting a GuildRole

```java
    /**
     * Get the role of a player
     * @param player role
     * @return the role of a player
     */
    public GuildRole getGuildRole(@NotNull Player player) {
        return getGuild(player).getMember(player.getUniqueId()).getRole();
    }
```

### Getting the GuildHandler

The GuildHandler will give you access to anything you might need in the plugin. Please use caution with this method as the content it lets you access to can break the plugin if you use it incorrectly.

```java
    /**
     * Get a copy of the guild handler
     * @return guild handler
     */
    public GuildHandler getGuildHandler() {
        return guildHandler;
    }
```

## Custom Events

In the plugin we offer a bunch of custom events that you can listen to and modify as you see fit.

### Base GuildEvent

```java
    /**
     * Base guild event
     * @param player player in event
     * @param guild guild in the event
     */
    public GuildEvent(Player player, Guild guild) {
        super(player);
        this.guild = guild;
    }
```

### GuildAddAllyEvent

```java
    /**
     * This event takes place when two guilds ally each other
     * @param player player who accepted
     * @param guild guild one
     * @param ally guild two
     */
    public GuildAddAllyEvent(Player player, Guild guild, Guild ally) {
        super(player, guild);
        this.ally = ally;
    }
```

### GuildCreateEvent

```java
    /**
     * Called when people create a guild
     * @param player player creating the guild
     * @param guild the guild being created
     */
    public GuildCreateEvent(Player player, Guild guild) {
        super(player, guild);
    }
```

### GuildDepositMoneyEvent

```java
    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param amount the amount to deposit
     */
    public GuildDepositMoneyEvent(Player player, Guild guild, double amount) {
        super(player, guild);
        this.amount = amount;
    }
```

### GuildInviteEvent

```java
    /**
     * Called when a player gets invited to a guild
     * @param player the player inviting other to guild
     * @param guild the guild player will be joining
     * @param invitedPlayer the player being invited
     */
    public GuildInviteEvent(Player player, Guild guild, Player invitedPlayer) {
        super(player, guild);
        this.invitedPlayer = invitedPlayer;
    }
```

### GuildJoinEvent

```java
    /**
     * Called when a player joins a guild
     * @param player the player joining a guild
     * @param guild the guild the player will be joining
     */
    public GuildJoinEvent(Player player, Guild guild) {
        super(player, guild);
    }
```

### GuildLeaveEvent

```java
    /**
     * Called a when a player leaves the guild
     * @param player the player leaving the guild
     * @param guild the guild the player was leaving
     * @param cause the reason the event was called
     */
    public GuildLeaveEvent(Player player, Guild guild, Cause cause) {
        super(player, guild);
        this.cause = cause;
    }

    public enum Cause {
        PLAYER_LEFT,
        PLAYER_KICKED,
        ADMIN_REMOVED
    }
```

### GuildPrefixEvent

```java
    private String prefix;

    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param prefix
     */
    public GuildPrefixEvent(Player player, Guild guild, String prefix) {
        super(player, guild);
        this.prefix = prefix;
    }

    public String getPrefix() {
        return prefix;
    }
```

### GuildRemoveAllyEvent

```java
    /**
     * Called when a guild removes an ally
     * @param player the player calling the removal
     * @param guild the guild calling the removal
     * @param ally the guild being removed
     */
    public GuildRemoveAllyEvent(Player player, Guild guild, Guild ally) {
        super(player, guild);
        this.ally = ally;
    }
```

### GuildRemoveEvent

```java
    private String name;
    
    /**
     * Called when a guild is removed
     * @param player the player removing the guild
     * @param guild the guild getting removed
     * @param cause the reason for the guild being removed
     */
    public GuildRemoveEvent(Player player, Guild guild, Cause cause) {
        super(player, guild);
        this.cause = cause;
    }

    public enum Cause {
        MASTER_LEFT,
        PLAYER_DELETED,
        ADMIN_DELETED
    }
```

### GuildRenameEvent

```java
    /**
     * @param player player in event
     * @param guild  guild in the event
     */
     public GuildRenameEvent(Player player, Guild guild, String newName) {
        super(player, guild);
        this.name = newName;
    }

    public String getName() {
        return name;
    }
```

### GuildTransferEvent

```java
private Player newMaster;

    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param newMaster
     */
    public GuildTransferEvent(Player player, Guild guild, Player newMaster) {
        super(player, guild);
        this.newMaster = newMaster;
    }

    public Player getNewMaster() {
        return newMaster;
    }
```

### GuildWithdrawMoneyEvent

```java
    /**
     * @param player player in event
     * @param guild  guild in the event
     * @param amount the amount to withdraw
     */
    public GuildWithdrawMoneyEvent(Player player, Guild guild, double amount) {
        super(player, guild);
        this.amount = amount;
    }
```

