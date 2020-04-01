## Contents
- [!pokemon]()
- [!gyms]()
- [!quest]()

# Commands
Regular Commands are meant to be used by regular users. They're translated and easy to use, aiming to provide an easy overview over certain stats or other information.

The config allows to set your own aliases for each command. Those aliases are just diufferent ways to write the command. So `!p` could be used instead of `!pokemon` for example. Additionally, the config allows to commands to only be used in certain Channels or by users with certain roles.

## !pokemon
    !pokemon [Mon Name] [Area] [Timeframe]
    !pokemon gible oslo 2/7/2019

`!pokemon` is used to get statistics of a specific Pokemon. This includes Shiny rate, 100% IV count, different factors for rarity and more.

### Arguments
- The **Mon Name** is the only required argument and used to specify the Pokemon you want its Stats of. It has a built in "autocorrection" so it will try to match the given name to any Pokemon, even if it's written wrong
- The **Area** has to match a set area in geofence.json 1:1 and can be used without a timeframe. If the given area does not match any configured areas, it will default to no area filter
- The **timeframe** can be used to filter Stats by exact times. To work, it also requires any area (which can be anything). It accepts all kinds of timestamps. E.g. `8:00 pm`, `feb 3 2019` or `3/7/2020` would all work. Additionally, you can also specify an end time by dividing two times with a `-` - e.g. `03.02. - 19.02.`

## !gyms
    !gyms [Area]
    !gyms moscow

`!gyms` shows basic Gym Stats of your configured area. That includes the total gym count, EX Gym ratio and active Raids. Additionally, it also has a pie chart that shows how many gyms each team owns.

## !quest
    !quest [Area] [reward]
    !quest nairobi spinda

`!quest` basically works the same as a [Quest Board](https://github.com/ccev/Discordopole/wiki/Boards#quest-boards) with the difference that it can only show one reward. That reward can be both an item or a Pokemon. The item has to match theactual item name 1:1.

Note that the command will temporarily upload an emote to your trsh server.