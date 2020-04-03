## Contents
- [Set up Discordopole]()
  - [Creating a Discord Bot]()
  - [Extra Server]()
- [Config Options]()

# Getting Started

## Set up Discordopole
Getting Discordopole on is a pretty easy task, especially if you've set up a Discord Bot before. Below is a step by step tutorial on how to get started.
- Clone the repo and copy the `config_example` folder to `config`
- Install the requirements.txt
- Fill out the `geofence.json` file in the config folder. (Tip: It's the same format as PoracleJS, so you can just copy it from there)
- Fill out the `config.ini` file in the config folder. Below is a table that explains most options
- Create a Discord Bot and invite it to your Servers (explained) below
- Set up an extra Server and use it to dump assets in. Also explained below

      git clone https://github.com/ccev/Discordopole.git && cd Discordopole
      cp -r config_example config
      pip3 install -r requirements.txt --upgrade
      cd .. && cp PoracleJS/config/geofence.json Discordopole/config/geofence.json
      nano Discordopole/config/config.ini
      python3 discordopole.py

### Creating a Discord Bot
- Go to the [Discord Developer Portal](https://discordapp.com/developers/applications/me)
- Create a New Application, give it a name and profile picture and confirm everything
- In the left menu, go to `Bot`, `Add Bot`, confirm and disable the `Public Bot` option (recommended)
- Copy the Bot Token and paste it into your Config
- Copy the Client ID in the `General Information` section
- Now replace `CLIENT_ID_HERE` in the below link with your Client ID, click the Link and invite the Bot to all Servers you need

      https://discordapp.com/oauth2/authorize?&client_id=CLIENT_ID_HERE&scope=bot&permissions=1074064496

### Extra Server
Discordopole sometimes uses custom emotes to make messages more beautiful. To use them, it needs to share a Server that has said Emotes, so it's best to just make an extra one for it to avoid possible emote limits or other conflictions. Additionally, Discordopole sometimes displays images in its messages. It does that by uploading them to a Channel and using the then generated Link. You could use any Channel for that, but why not use one on that extra Server when you have one anyway. So:
- Create a Discord Server
- Invite the Bot to it using the Link abover
- Mute it
- Copy the Channel ID of #general (right click - Copy ID) and paste it in the config's `trash_channel` option
- Copy the Server ID (found in Server Settings - Widget) and paste it in the config's `trash_server` option
- Say `!get emotes` once, then the Server's name to confirm and let the Bot import Emotes.

## Config Options

### Config
- **`bot_token`**: Your Discord Bot's Bot Token ([see here](TODO))
- **`language`**: The language your Bot's speaking. Can be `en/de/fr/es/pl` (Not in Admin Commands or Logs)
- **`timezone_offset`**: Your timezone offset (e.g. `-07:00`)
- **`prefix`**: The character that has to be written in front of commands
- **`admins`**: Discord User IDs allowed to use Admin Commands. Seperated by commas
- **`trash_channel`**: The Channel in which images are being uploaded in ([see here](TODO))
- **`trash_server`**: The Server Quest Emotes are being uploaded in ([see here](TODO))
- **`pokemon_icon_repo`**: The repo from which Discordopole gets its Pokemon Icons (PMSF format)
- **`emote_repo`**: The repo from which Discordopole gets its Emotes

### Maps
- **`use_static_maps`**: Whether to use Static Maps or not (`True/False`)
- **`provider`**: The Static Map Provider (`mapbox/tileserver`)
- **`key`**: Either your Mapbox Key or Tileserver URL
- **`use_map_frontend`**: Whether to use Custom Map Links or not (`True/False`)
- **`frontend`**: Your kind of Map frontend (`pmsf/rdm/rmad`)
- **`map_url`**: The URL to your Map

### Commands
- **`required_roles` `channels`**: Role and/or channel requirements for all commands
- **`pokemon_aliases` `gyms_aliases` `quest_aliases`** Aliases for all commands

### DB
- **`scanner_db_schema`**: MAD or RDM (`mad/rdm`)
- **`host` `port` `user` `password`**: DB credentials
- **`scanner_db_name`**: The name of your MAD/RDM database