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
     * @param uuid uuid of the player
     * @return the guild they are in
     */
    public Guild getGuild(@NotNull UUID uuid) {
        return guildHandler.getGuild(uuid);
    }
```

**Using Player name**

```java
    /**
     * Get the guild of a player by their name
     * @param name the name of the player
     * @return the guild they are in
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

