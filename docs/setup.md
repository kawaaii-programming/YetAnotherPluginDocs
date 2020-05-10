!!! danger
    This page might not be fully up to date, I'll try keep this up to date as much as possible.  
    I also try to not change around the Config file too much, but if that happens keep in mind:  
    **This plugin is still under development, so deal with it ♥**

## Dependencies

YAP (Yet Another Plugin) has a couple dependencies in order to work.  
If one of these plugins are not present or loaded YAP won't be able to be enabled.

#### Plugin Dependencies
- [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) ^2.10
- [mcMMO](https://www.spigotmc.org/resources/official-mcmmo-original-author-returns.64348/) ^2.1

#### Java Dependencies
*Java dependensies are only important for contributors*  

- [JavaCord](https://github.com/Javacord/Javacord) ^3.0.4

## Configration Breakdown
### config.discord
In this namespace you have to provide the important data such as the Discord Bot Token and other important information.
#### discord.token
`discord.token` only takes the Discord Bot Token, if you use something else YAP won't load and will cause errors.
#### discord.prefixes
`discord.prefixes` takes a list of Strings and those will be used as the prefixes for Discord commands. If none are given the default prefix will be `!`

### config.modules
In this namespace we change the configs of the modules within YAP. 
#### modules.advancements
#### modules.connections
#### modules.cross-chat

## Default Configuration

``` yaml  
config:

  # These settings are really important to make this plugin actually do something.
  # discord.token only takes the Discord Bot Token, if you use something else this plugin won't work!
  # discord.prefixes takes a list with Strings and those are the prefixes for the Discord Commands if none given default will be "!"
  discord:
    token: ''
    prefixes:
      - ''

  modules:

    # This module when enabled will sent advancements earned by players straight to the assigned Discord channels.
    # This module uses their own formats and for now these are not editable, maybe in the near feature!
    # They look like this: "**{username}** just obtained their first diamond and made the advancement [**{advancement}**]"
    advancements:
      enabled: false
      channels:
        - ''

    # This module when enabled will sent a message upon player join and player leave to the assigned Discord channels.
    # Formats are editable and since the plugin hooked is with PlaceholderAPI you can use those placeholders too.
    connections:
      enabled: false

      join:
        enabled: true
        format: '\🟢 | **{username}** entered the server, have fun!'
        channels:
          - ''

      quit:
        enabled: true
        format: '\🔴 | **%s** left the server, come again!'
        channels:
          - ''

    cross-chat:
      enabled: false

      to-minecraft:
        enabled: true
        format: ''
        channels:
          - ''

      to-discord:
        enabled: true

        # Methods are the way the Minecraft to Discord message will be delivered.
        # webhook: is the default method and to my opinion the better looking one.
        # bot: is the other method and is a bit more basic but has a format option.
        # More explanations are available on the plugin wiki on Github.
        # https://github.com/kawaaii-programming/YetAnotherPlugin/wiki/Modules#methods
        method: 'webhook'

        # This only works if method is set to 'bot'
        format: '**{username}**: {message}'
        channels:
          - ''

        # This works only if methid is set to 'webhook'
        webhooks:
          - ''
```