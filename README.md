# Discord-Embed-Pages-Selection

Swap embed pages using discord's selection option!
# Functions:

**There is only one function in this package:**

menupages.pageSelect(message, arrayOfSelectionData, arrayOfEmbeds, timeout, placeholder, disbut)

**message:**

This is your discord message.

**arrayOfSelectionData:**

This is an array of the menu options data. (See example at the bottom of the page)

**arrayOfEmbeds:**

This is an array of Discord Message Embeds

**timeout:**

This is the amount of time (in milliseconds) that the bot will listen to the menu for. After this time, the embeds cannot be swapped through.

**placeholder:**

This is a string of what the menu selection should say when no option is selected.

**disbut:**

This is the disbut instance that you use.

# Example:
```
const Discord = require("discord.js");
const disbut = require("discord-buttons");
const menupages = require("discord-embed-pages-selection");

const client = new Discord.Client();
disbut(client);

client.login(process.env.token);

client.on("message", async message=>{
  if(message.author.bot || message.channel.type == "dm")return;
  if(message.content == "selectionEmbed"){
    const embed = new Discord.MessageEmbed()
    .setColor("YELLOW")
    .setTitle("PAGE 1")
    
    const embed2 = new Discord.MessageEmbed()
    .setColor("GREEN")
    .setTitle("PAGE 2")
    
    menupages.pageSelect(message,[
  {
    "name": "PAGE 1",
    "description": "PAGE 1",
    "emoji": {
      "name": "🧀",
      "animated": false
    }
  },
  {
    "name": "PAGE 2",
    "description": "PAGE 2",
    "emoji": {
      "name": "😳",
      "animated": false
    }
  }
],[embed, embed2], 60*1000,"TO THE MOON", disbut)
  }
})
```
# Support

Join the discord for support and for other packages/discord bots:

https://discord.gg/u9gFdnu
