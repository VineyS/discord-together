<div align="center">
    <a href="https://pypi.org/project/discord-together"><img src="https://i.ibb.co/nCr7dnf/DT-Logo-New.png" alt="discord-together logo" height="128" style="border-radius: 50%"></a>
    <div>
        <h1><strong>Discord Together</strong></h1>
    </div>
    <div>
        <a href="https://pypi.org/project/discord-together"><img src="https://img.shields.io/pypi/dm/discord-together?color=%23EF0BB9&?style=flat" alt="discord-together downloads"></a>
        <a href="https://pypi.org/project/discord-together"><img src="https://img.shields.io/pypi/v/discord-together?color=%23EF0BB9&label=version&?style=flat" alt="discord-together version"></a>
        <a href="https://pypi.org/project/discord-together"><img src="https://img.shields.io/badge/made%20for-discord.py-23EF0BB9?color=%23EF0BB9&?style=flat" alt="discord-together version"></a>
    </div>
</div>
<br>
<br>

# 👋 Welcome!
<h3>Discord has released a BETA feature that they call Discord Party Games to only a certain hand-picked servers. This module allows you to temporarily enable such features for your servers!</h3>
<br>
<h4>As of  v1.1.0, this BETA feature is only supported on web and updated PC app versions of Discord and is not supported on mobile.</h4>

<br>

# 🔩 Installation
## Install [discord-together](https://pypi.org/project/discord-together/)
```
pip install discord-together
```

#### Package dependencies only include [discord.py](https://pypi.org/project/discord.py/)
<br>

# 🔑 Features
- Easy to use and lightweight
- Actively maintained
- [discord.py](https://pypi.org/project/discord.py/) support
- Dynamic error handling with custom errors
- Debug mode for invalid invites

<br>

# 💻 Code example
This is a simple example of code using this package.

```py
from discord.ext import commands
from discordTogether import DiscordTogether

client = commands.Bot(command_prefix="~")
togetherControl = DiscordTogether(client)

@client.event
async def on_ready():
    print(f"Bot logged into {client.user}.")

@client.command()
async def startYT(ctx):
    link = await togetherControl.create_link(ctx.author.voice.channel.id, 'youtube')
    await ctx.send(f"Click the blue link!\n{link}")

client.run("BOT_TOKEN_HERE")
```
Within cogs :
```py
from discord.ext import commands
from discordTogether import DiscordTogether

class YoutubeTogetherCog(commands.Cog):
    def __init__(self, client):
        self.client = client
        self.togetherControl = DiscordTogether(client)
    
    @commands.command()
    async def start(self, ctx):
        link = await self.togetherControl.create_link(ctx.author.voice.channel.id, 'youtube')
        await ctx.send(f"Click the blue link!\n{link}")

def setup(client):
    client.add_cog(YoutubeTogetherCog(client))
```
<br>

# 🔧 General Usage
### **create_link() Format**
```py
link = await togetherControl.create_link(VC_ID, 'APP_ID')
# VC_ID : Integer
# APP_ID : String
```

- **Options for APP_ID:**
<br>- &nbsp;Youtube
<br>- &nbsp;Poker
<br>- &nbsp;Chess
<br>- &nbsp;Betrayal
<br>- &nbsp;Fishing
<br>- &nbsp;`Custom Activity ID` (Only use this if you know the exact ID for an activity)

<br>

### **Error Handling**
- ```discordTogether.errors.InvalidChannelID```:&nbsp; Raised when an invalid Voice Channel ID is entered.
- ```discordTogether.errors.InvalidActivityChoice``` :&nbsp; Raised when an invalid activity choice is entered.
- ```discord.ext.commands.errors.BotMissingPermissions``` :&nbsp; Raised when the bot does not have *CREATE_INVITE* permission.
- ```discord.errors.ConnectionError``` :&nbsp; Raised when a connection error from Discord API occurs.
- ```discord.errors.InvalidArgument``` :&nbsp; Raised when a custom activity ID is invalid.

<br>

# 📷 Image 

![Invite link](https://cdn.discordapp.com/attachments/678298437854298122/860210951222460446/msedge_Gntg4yflYw.png)

<h3>⚠️ Advisory Note:</h3>
<h4>
At least one person needs to click on the <strong>BLUE LINK</strong>, not the 'Play' button, in order to start the activity! Once the activity is started, people can join by clicking 'Play'.

Multiple people clicking the blue link at once can cause a "Activity Ended" error screen, however it's not a common occurence.</h4> 

<br>

![YouTube Together](https://cdn.discordapp.com/attachments/678298437854298122/860210751448547328/msedge_HpqALcJCcD.png)

<br>

# 🚀 Others

**This package is under MIT license.** Appropriately tested PR's are more than welcome.

*Note: This package is not affiliated with Discord or YouTube.*

If you have any problems or enquiries, join the [discord-together Support Server](https://discord.gg/2fbyXn2hJV) or you can contact me personally on Discord: `Bxllistic#4444`.

This project was converted to support discord.py from the npm package [discord-together](https://www.npmjs.com/package/discord-together) made by [RemyK888](https://github.com/RemyK888)

<br>
<hr>

## **Made with ❤ by Bxllistic#4444**
Credits to [@RemyK888](https://github.com/RemyK888) for application IDs and foundations
