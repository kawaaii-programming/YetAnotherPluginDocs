## Dependencies

## Configuration
This file might not be fully up to date, I'll try keep this up to date as much as possible.  
I also try to not change around the Config file too much, but if that happens keep in mind:  
**This plugin is still under development, so deal with it ♥**

### config.yml
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