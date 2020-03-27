## Contents
- Raid Boards
- Egg Boards
- Stat Boards
- Quest Boards
- Raid Channels

# Boards
Boards are a nice way to present information to your users, while staying compact and clear.

Every Board is stored in config/boards.json. To create or delete Boards, it's best to use [`!board`](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board). Every board is stored in config/boards.json, so you can use this file to refine and edit already existing Boards.

## Raid Boards
Raid Boards summarize active Raids to their most important information and display them in a single embed. This includes the Gym name, whether it's ex eligible or not, End time, the Pokemon's name, the beginning letter of its form (if needed) and its moveset. They're sorted by end time, so the longest lasting Raid is at the bottom.

![](https://media.discordapp.net/attachments/523253670700122144/693070348081561640/unknown.png)

### Limits
One Raid Board can show about 25 Raids at once. Under normal conditions, that's enough for an area with around 150 Gyms. Gym Names are shortened to 30 characters.

### JSON
- **channel_id**: The ID of the channel the message is in
- **message_id**: The message's ID
- **title**: The embed's title. Defaults to the locale of "Raids"
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **timezone**: The timezone End times are converted into. Defaults to the one set in config
- **wait**: Seconds to wait after updating the Board. Defaults to 15
- **levels**: Raid Levels included in the Raid Board
- **ex**: Only show EX Gyms or not (True/False)

## Egg Boards
![](https://media.discordapp.net/attachments/523253670700122144/693072640432144414/unknown.png)

## Stat Boards
![](https://media.discordapp.net/attachments/523253670700122144/693073222639288420/unknown.png)

## Quest Boards
![](https://media.discordapp.net/attachments/523253670700122144/693076005182636032/unknown.png?width=668&height=677)

## Raid Channels
![](https://cdn.discordapp.com/attachments/523253670700122144/693077323909431326/unknown.png)