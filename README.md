<p align="center"><a href="https://nodei.co/npm/discord.js-adblock/"><img src="https://nodei.co/npm/discord.js-adblock.png"></a></p>

# discord.js-adblock

A simple module with quick setup and different options to implement discord.js-adblock features in your bot.

## Installation

To install this module type the following command in your console:

```
npm i discord.js-adblock --save
```
## Example

Example of a basic bot handling using this module.

```js
const Discord = require('discord.js');
const discordAdblockPlus = require('discord.js-adblock');
const client = new Discord.Client();

client.once('ready',async() => console.log('READY!'));

client.on('message', async(message) => { 
    discordAdblockPlus.options({
        maxwarnings: 3,
        whitelistlinks: ["first link","second link"],
        bot_block: true
    });

    const adDetected = await discordAdblockPlus.checkAdMessage(message); 
    if(adDetected) {
       message.member.roles.add('muted_role_id').catch(err => console.log(err.message));
       //message.member.ban({reason:'null'}).catch(err => console.log(err.message));
       //message.member.kick({reason:'null'}).catch(err => console.log(err.message));
       //...
       //...
    };
});

client.login('TOKEN');

```

## Support Server

Join our [Support Server](https://discord.gg/YbWSTBMEpb) where we help you with issues regarding the module.

## Bug Reports

If you have any bugs or trouble setting the module up, feel free to open an issue on [Github](https://github.com/KaanPNX/discord.js-adblock)

# discord.js-adblock
