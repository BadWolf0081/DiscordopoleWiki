## Contents
- [!board](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board)
  - [delete](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-delete)
  - [create](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create)
    - [raid](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create-raid)
    - [egg](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create-egg)
    - [raidchannel](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create-raidchannel)
    - [stats](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create-stats)
    - [quest](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board-create-quest)
- [!get](https://github.com/ccev/Discordopole/wiki/Admin-Commands#get)
  - [emotes](https://github.com/ccev/Discordopole/wiki/Admin-Commands#get-emotes)
  - [updates](https://github.com/ccev/Discordopole/wiki/Admin-Commands#get-updates)

# Admin Commands

## !board
The `!board` command allows you to quickly create or delete [Boards](TODO:LINK) without having to edit boards.json.

### !board delete
Delete a Board using its Message ID. This will delete both the message itself as well as the entry in boards.json.

    !board delete [Message ID]
    !board delete 676903136266289174

### !board create
Without further arguments, this command will create a message containing its Channel and Message ID, so you can then manually put the information in boards.json

    !board create

### !board create raid
Creates a Raid Board and puts the Channel ID, Message ID, Area name and tracked Levels in boards.json.

    !board create raid [Area Name] [Levels]
    !board create raid berlin 1,3,5

### !board create egg
Creates an Egg Board and puts the Channel ID, Message ID, Area name and tracked Levels in boards.json.

    !board create egg [Area Name] [Levels]
    !board create egg tokyo 1,2

### !board create raidchannel
Creates a new Channel and turns it into a Raid Channel. It puts the Channel ID, Area name and tracked Levels in boards.json.

    !board create raidchannel [Channel Name] [Area Name] [Levels]
    !board create raidchannel lvl5-raids denver 5

### !board create stats
Creates a Stat Board and puts the Channel ID, Message ID, Area name and wanted Stats in boards.json. When defining the Stats, spaces are allowed as long as every stat is seperated by a comma. It's also "smart", so it won't need the exact stat names.

    !board create stats [Area Name] [Stats]
    !board create stats rio mon active, mon today,active raids, egg ,gym amount

### !board create quest
Creates a Quest Board and puts the Channel ID, Message ID, Area name and wanted rewards in boards.json. It will also import one emote for each reward in your trash server.

Every reward needs to be seperated by a comma. Items need to 1:1 match the actual item names, Mon names are corrected.

When deleting a reward emote, make sure to also remove it from config/emotes.json to not cause any conflicts.

    !board create quest [Area Name] [Rewards]
    !board create quest helsinki sinnoh stone,mossy lure module,spnda, lavita, magikarp

## !get
The `!get` command is important For Discordopole Bot. It helps with importing needed emotes as well as keeping it updated.

### !get emotes
Downloads all needed emotes from the repo in your config.ini, uploads them to the Server you're currently in and also puts them in your emotes.json.

Bots can use custom emotes from all server they're in. So please create an extra Server to host emotes in and then invite your bot to it. This avoids possible conflicts with already existing custom emotes or limits.

Pro Tip: When using `!get emotes` you'll first need to confirm the Server Name. You can skip that dialog by saying `!get emotes [Server Name]` directly.

### !get updates
Sometimes, editing certain files in your configs are needed to ensure Discordopole is running correctly. This is what this command is used for.

Needing to use the command is rather uncommon, so it's usually being announced on the Discord Server, when it's time.