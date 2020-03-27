## Contents
- [Raid Boards](https://github.com/ccev/Discordopole/wiki/Boards#raid-boards)
  - [Limits](https://github.com/ccev/Discordopole/wiki/Boards#limits)
  - [JSON](https://github.com/ccev/Discordopole/wiki/Boards#json)
- [Egg Boards](https://github.com/ccev/Discordopole/wiki/Boards#egg-boards)
  - [Limits](https://github.com/ccev/Discordopole/wiki/Boards#limits-1)
  - [JSON](https://github.com/ccev/Discordopole/wiki/Boards#json-1)
- [Stat Boards](https://github.com/ccev/Discordopole/wiki/Boards#stat-boards)
  - [JSON](https://github.com/ccev/Discordopole/wiki/Boards#json-2)
  - [Possible Stats](https://github.com/ccev/Discordopole/wiki/Boards#possible-stats)
- [Quest Boards](https://github.com/ccev/Discordopole/wiki/Boards#quest-boards)
  - [Limits](https://github.com/ccev/Discordopole/wiki/Boards#limits-2)
  - [JSON](https://github.com/ccev/Discordopole/wiki/Boards#json-3)
- [Raid Channels](https://github.com/ccev/Discordopole/wiki/Boards#raid-channels)
  - [Limits](https://github.com/ccev/Discordopole/wiki/Boards#limits-3)
  - [JSON](https://github.com/ccev/Discordopole/wiki/Boards#json-4)

# Boards
Boards are a nice way to present information to your users, while staying compact and clear.

Every Board is stored in config/boards.json. To create or delete Boards, it's best to use [`!board`](https://github.com/ccev/Discordopole/wiki/Admin-Commands#board). Every board is stored in config/boards.json, so you can use this file to refine and edit already existing Boards.

Since Discord has a 2048 character limit for messages, most Boards can only show so many things at once. Depending on how large your area is, you might have to split it up. This page gives an overview for how much each Board can cover. Personally, I scan a town with a size of 50km², ~100 Gyms and ~600 Stops with 10 MAD Workers and one Board each is enough.

## Raid Boards
Raid Boards summarize active Raids to their most important information and display them in a single embed. This includes the Gym name, whether it's ex eligible or not, end time, the Pokemon's name, the beginning letter of its form (if needed) and its moveset. They're sorted by end time, so the longest lasting Raid is at the bottom.

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
Pretty much the same as Raid Boards, Egg Boards summarize active Eggs to their most important information and display them in a single embed. This includes an emote showing the actual egg, the Gym name, whether it's ex eligible or not, start and end time. They're sorted by end time, so the soonest hatching egg is at the top.
![](https://media.discordapp.net/attachments/523253670700122144/693072640432144414/unknown.png)

### Limits
One Egg Board can show about 25 Eggs at once. Under normal conditions, that's enough for an area with around 150 Gyms. Gym Names are shortened to 30 characters.

### JSON
- **channel_id**: The ID of the channel the message is in
- **message_id**: The message's ID
- **title**: The embed's title. Defaults to the locale of "Eggs"
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **timezone**: The timezone End times are converted into. Defaults to the one set in config
- **wait**: Seconds to wait after updating the Board. Defaults to 15
- **levels**: Raid Levels included in the Raid Board
- **ex**: Only show EX Gyms or not (True/False)

## Stat Boards
Stat Boards are an easy way to display general Statistics in a single message that always stays updated. It allows several useful stats to be tracked. Depending on which stats are configured, the message may combine multiple
stats in one line that would otherwise use up two. The screenshot below shows a Stat Board with everything enabled.

![](https://media.discordapp.net/attachments/523253670700122144/693073222639288420/unknown.png)

### JSON
- **channel_id**: The ID of the channel the message is in
- **message_id**: The message's ID
- **title**: The embed's title. Defaults to the locale of "Statistics"
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **timezone**: The timezone End times are converted into. Defaults to the one set in config
- **wait**: Seconds to wait after updating the Board. Defaults to 15
- **type**: Which stats to show. Supported stats are listed below

### Possible Stats
**Mons**
- **mon_active**: Amount of Mons currently active
- **mon_today**: Total amount of Mons found today

**Gyms**
- **gym_amount**: Total amount of Gyms
- **raid_active**: Amount of Raids currently ready to be battled
- **egg_active**: Amount of Eggs
- **gym_teams**: Total amount of Gyms each Team is holding currently

**Stops**
- **stop_amount**: Total amount of Stops
- **quest_active**: Total number of Quests scanned today
- **grunt_active**: Amount of Team Rocket Grunts currently ready to be battled
- **leader_active**: Total number of Team Rocket Leaders (incl. Giovanni) today

## Quest Boards
Quest Boards allow to summarize multiple Quests in one message with each Quest only having the most important information: An emote showing the reward, The stop name and a link to that Stop. Depending on your config, that Link will either go to your Map or Google Maps. Additionally, there's also a Static Map that shows all Quests. The Static Map will scale depending on where the Quests are, so there's no space on the sides wasted.

They can be used in two ways:
1. To summarize all rare Quests in one message. So you can see everything on one glance.
2. If you just track one reward, Discordopole makes the Board look a little more fancy. So you could have multiple Boards in one channel which each show one type of Quest.

Quest Boards update hourly and eat up your mapbox requests. So consider setting up Flo's tileserver, if you haven't already.

![](https://media.discordapp.net/attachments/523253670700122144/693076005182636032/unknown.png?width=668&height=677)

### Limits
One Quest Board can show up to 30 Quests. Depending on what types of rewards you track, the amount of Stops one Board covers will vary. Say if you set up one Quest Board for each rare Quest (like Larvitar or Spinda) they can each cover an rea of ~5000 Stops.

Then there's also the Static Map which will look too messy for bigger areas. So go for an area that's still clear when seen as a whole.

Note that to save characters, each link is shortened with tinyurl.

### JSON
- **channel_id**: The ID of the channel the message is in
- **message_id**: The message's ID
- **title**: The embed's title. Defaults to the locale of "Eggs"
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **mons**: The IDs of tracked Mons
- **items**: The IDs of tracked Items

## Raid Channels
Raid Channels are no real Boards, but are treated like one in the config. One message shows one Raid and is therefore more detailed than a Raid Board. When an egg hatched, the message will be edited. When the Raid ends, the message will be deleted.

A Raid message includes the Mon's icon, name, moves and CP for 100% IV at Level 20 and 25. The Gym's name, image, Links to each Google and Apple Maps as well as the Raid's end time.

An Egg message includes the Egg's icon and name (e.g. "Level 3 Egg"), the Gym's name, image, Links to each Google and Apple Maps as well as the Raid's start and end time.

![](https://cdn.discordapp.com/attachments/523253670700122144/693077323909431326/unknown.png)

### Limits
The only thing that limits Raid Channels are the Discord API limits. So you should be able to cover a *huge* area with a single Raid Board.

### JSON
- **channel_id**: The ID of the channel the message is in
- **area**: The area's name. Needs to 1:1 match the area in geofence.json
- **wait**: Seconds to wait after going through all Raids and updating the Channel accordingly. Defaults to 15
- **levels**: Raid Levels included in the Raid Channel