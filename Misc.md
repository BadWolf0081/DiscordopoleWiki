## Contents
- [Static Maps](https://github.com/ccev/Discordopole/wiki/Misc#static-maps)

# Misc

## Static Maps
Discordopole utilizes brings Static Maps to its limits. It supports both mapbox and Flo's tileserver. Using latter one is recommended, since mapbox is more meant as an option for people who *really* can't afford setting up their own tileserver.

When putting your information in the config, please note `key` can either be your mapbox key or the URL to your tileserver (ending with a /).

Flo's tileserver is great for (basically) unlimited and free requests. That includes both tiles for your map frontend and static maps. See its [Github for installation instructions](https://github.com/123FLO321/SwiftTileserverCache). If you already have it set up, please make sure you're on a version above 1.0.2 (released on April 2nd 2020)

When using mapbox, please be aware that each Quest Board generates a Static Map hourly and Raid Channels need one request per message. So you might reach your API limit pretty fast.