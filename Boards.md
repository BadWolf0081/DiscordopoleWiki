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

### Limit
About 25 Raids. Enough for an area of around 150 Gyms.

### JSON
- **channel_id**: The ID of the channel the message is in
- **message_id**: The message's ID
- **title**: The embed's title. Defaults to the locale of "Raids"
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **timezone**: The timezone End times are converted into. Defaults to the one set in config
- **wait**: Seconds to wait after updating the Board. Defaults to 15
- **levels**: Raid Levels included in the Raid Board
- **ex**: Only show EX Gyms or not (True/False)