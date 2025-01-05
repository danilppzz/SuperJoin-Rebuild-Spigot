## SuperJoin Rebuild
This plugin allows you to customize join message with player head in it, also supports PlaceholderAPI.

### This plugin support this features
 - [x] Hex & Color codes support.
   - Format for hex `#6bcde3`
   - Format for minecraft color code `&3`
 - [x] Only display at join for premium users.
 - [x] [Discord hook integration.](#discord-hook-support)
 - [x] Custom join sound.
 - [x] Place margin top & bottom at messages.
 - [x] PlaceholderAPI 
   - Recommend installing `Servertime` & `Player` for use default hook message

## Default Configuration
This is the `config.yml` file where you can customize the plugin.
```yml
error_permission_message: "&fYou don't have enough permissions."

join:
  # Keep empty for all the worlds in the server (especial when using networks)
  world: ""

  # You can put a 8px by 8px image to render to users at join message.
  custom_image: false
  custom_image_url: "https://raw.githubusercontent.com/danilppzz/SuperJoin-Rebuild-Spigot/refs/heads/main/resources/5d28c579a4c0.png"

  # Display the player head
  player_head: true

  # If you want the head display you need to keep 8 rows at message.
  # DON'T REMOVE ANY ROW !
  message:
    - ""
    - "&fWelcome &c%player_name% &fto the server!"
    - ""
    - ""
    - ""
    - ""
    - ""
    - ""

  # Default message is use when player_head is disabled.
  default_message: "&8[&2+&8] &f%player_name%"

  # Set a margin at the top and bottom of the message.
  margin: true

  # For no sound just let it without text.
  # Also, the sound must be in UpperCase.
  # Default: ENTITY_EXPERIENCE_ORB_PICKUP
  sound: "ENTITY_EXPERIENCE_ORB_PICKUP"

# Discord hook also support PlaceholderAPI so you can use %player_name% or other.
discord:
  enable: false
  discord_hook_url: ""
```

## Discord Hook Support
To enable the hook for discord you need to change the following code at config.
```yml
discord:
  enable: true
  discord_hook_url: "discord_hook_url"
```

Also for the message of the discord you need to change the discord.json

use `%servertime_yyyy-MM-dd'T'HH:mm:ss.SSS'Z'%` at the timestamp for current date.

use `%player_name%` for the player name.

you can use all the PlaceholderAPI extension you want, for this two you need `Servertime` & `Player`

> [!IMPORTANT]
> To create custom messages for discord I recomend using this: [https://discohook.org/](https://discohook.org/)
> 
> and export it to json after you made it.
```json
{
  "content": null,
  "embeds": [
    {
      "title": "%player_name%",
      "description": "Has joined the server !",
      "color": 1973790,
      "footer": {
        "text": "minecraft.net"
      },
      "timestamp": "%servertime_yyyy-MM-dd'T'HH:mm:ss.SSS'Z'%"
    }
  ],
  "attachments": []
}
```
