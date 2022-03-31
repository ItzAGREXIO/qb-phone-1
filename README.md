# qb-phone
WIP (still work in progress)
This is my redesign of the qb-phone.
Any contribution in the phone's progress is appreciated
Advanced Phone for QB-Core Framework :iphone:
# License

    QBCore Framework
    Copyright (C) 2021 Joshua Eger

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>

## Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-policejob](https://github.com/qbcore-framework/qb-policejob) - MEOS, handcuff check etc. 
- [qb-crypto](https://github.com/qbcore-framework/qb-crypto) - Crypto currency trading 
- [qb-lapraces](https://github.com/qbcore-framework/qb-lapraces) - Creating routes and racing 
- [qb-houses](https://github.com/qbcore-framework/qb-houses) - House and Key Management App
- [qb-garages](https://github.com/qbcore-framework/qb-garages) - For Garage App
- [qb-banking](https://github.com/qbcore-framework/qb-banking) - For Banking App
- [screenshot-basic](https://github.com/citizenfx/screenshot-basic) - For Taking Photos
- A Webhook for hosting photos (Discord or Imgur can provide this)


## Screenshots
![Home](https://cdn.discordapp.com/attachments/902862654903844914/959086943453474907/unknown.png)
![Bank](https://cdn.discordapp.com/attachments/902862654903844914/959087154166911056/unknown.png)
![Mail](https://cdn.discordapp.com/attachments/902862654903844914/959087027628933130/unknown.png)
![Garage](https://cdn.discordapp.com/attachments/902862654903844914/959086989750177852/unknown.png)
![Garage Detail](https://cdn.discordapp.com/attachments/902862654903844914/959087799703838761/unknown.png)
![Twitter](https://cdn.discordapp.com/attachments/902862654903844914/959087159216861234/unknown.png)

## Features
- Garages app to see your vehicle details
- Mails to inform the player
- Banking app to see balance and transfer money
- Racing app to create races
- App Store to download apps
- MEOS app for polices to search
- Houses app for house details and management

## Installation
### Manual
- Download the script and put it in the `[qb]` directory.
- Import `qb-phone.sql` in your database
- Add the following code to your server.cfg/resouces.cfg
```
ensure qb-core
ensure screenshot-basic
ensure qb-phone
ensure qb-policejob
ensure qb-crypto
ensure qb-lapraces
ensure qb-houses
ensure qb-garages
ensure qb-banking
```

## Configuration
```

Config = Config or {}

Config.RepeatTimeout = 2000 -- Timeout for unanswered call notification
Config.CallRepeats = 10 -- Repeats for unanswered call notification
Config.OpenPhone = 244 -- Key to open phone display
Config.PhoneApplications = {
    ["phone"] = { -- Needs to be unique
        app = "phone", -- App route
        color = "#04b543", -- App icon color
        icon = "fa fa-phone-alt", -- App icon
        tooltipText = "Phone", -- App name
        tooltipPos = "top",
        job = false, -- Job requirement
        blockedjobs = {}, -- Jobs cannot use this app
        slot = 1, -- App position
        Alerts = 0, -- Alert count
    },
}
```
## Setup Webhook in `server/main.lua` for photos
Set the following variable to your webhook (For example, a Discord channel or Imgur webhook)
### To use Discord:
- Right click on a channel dedicated for photos
- Click Edit Channel
- Click Integrations
- Click View Webhooks
- Click New Webhook
- Confirm channel
- Click Copy Webhook URL
- Paste into `WebHook` in `server/main.lua`
```
local WebHook = ""
```
