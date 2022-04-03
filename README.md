# discord-js13-tips
i will add sum discord.js v13 scripts / tips here

<details>
<summary><h4>Base for Discord.js V13 Bot</h4></summary>
  
```js
const { Client, Intents } = require('discord.js');
const client = new Client({ intents: [Intents.FLAGS.GUILDS] });

client.on('ready', () => {
  console.log(`Bot Have been Successfully started: ${client.user.tag}`);
});

client.login('token');
```
  
</details>

<details>
<summary><h4>Discord V13 Bot - Intents</h4></summary>

**Basic Intents**
```js
    intents: [
        Intents.FLAGS.GUILDS, // Basic Guild stuff.
        Intents.FLAGS.GUILD_MESSAGES, // Bot Can react to Messages sent in guilds.
        Intents.FLAGS.GUILD_BANS, // Bot can manage bans
        Intents.FLAGS.GUILD_PRESENCES, // Guilds can manage bot Precense.
        Intents.FLAGS.DIRECT_MESSAGES, // Bot can send / react to DMS.
        Intents.FLAGS.MANAGE_MESSAGES, // Bot can manage messages.
    ]
```

**All Intents**
```js
    const kaikkiintentit = new Intents(32767); // Will give all intents.

    intents: [
        kaikkiintentit // written in finnish but means all intents
    ]

```

</details>

<details>
<summary><h4>Discord V13 Bot - Handlers</h4></summary>

**Example Command ["SLASH"]**
```js
const { SlashCommandBuilder } = require("@discordjs/builders");

module.exports = {
    data: new SlashCommandBuilder()
        .setName("sayhello")
        .setDescription("Command Desc"),

    async execute(interaction) {

        interaction.reply({
            content: "Hello!", // Content "message"
            //Embeds: [], // Embeds
            ephemeral: true, // Will reply as interaction creator sees only
        });
    },
};
```

**Command Handler from** `commands` **folder**
```js

const fs = require("fs");

const commandFiles = fs.readdirSync("./commands").filter(file => file.endsWith(".js"))
const commands = [];

client.commands = new Collection();

for (const file of commandFiles) {
    const command = require(`./commands/${file}`);
    commands.push(command.data.toJSON());
    client.commands.set(command.data.name, command)
}
```

**Event Handler from** `events` **folder**
```js
const fs = require("fs");

const eventFiles = fs.readdirSync('./events').filter(file => file.endsWith('.js'));
for (const file of eventFiles) {
	const event = require(`./events/${file}`);
	if (event.once) {
		client.once(event.name, (...args) => event.execute(...args));
	} else {
		client.on(event.name, (...args) => event.execute(...args));
	}
}
```

</details>

<details>
<summary><h4>Discord.js V13 Bot - Messages</h4></summary>

**Normal Messages**
```js

const embedi = new Discord.MessageEmbed()
.setAuthor({ name: "test embedi" });

message.channel.send({
  content: "hello", // Content = message
  embeds: [embedi] // message Embeds
});

message.reply({
  content: "hello", // Content = message
  embeds: [embedi] // message Embeds
});
```

**Interaction Messages**
```js
const embedi = new Discord.MessageEmbed()
.setAuthor({ name: "test embedi" });

interaction.channel.send({
  content: "hello", // Content = message
  embeds: [embedi], // message Embeds
});

interaction.reply({
  content: "hello", // Content = message
  embeds: [embedi], // message Embeds
  ephemeral: true or false // True = private msg | false = public
});
```

</details>

<details>
<summary><h4>Discord.js V13 Bot - Web Server</h4></summary>

**Simple Web Server index.js**
```js
const fs = require("fs");

fs.readdirSync("handlers/").forEach(dirs => require("./handlers/" + dirs)(client));
```

**Simple Web Server handlers/monitor.js**
```js
const express = require("express"); // Import Express module
const app = express(); // INIT Express as app
const port = 6969; // Web Listener Port

module.exports = (client) => {
    // App will give response if url = localhost:6969 not localhost:6969/lolxd
    app.get("/", async (req, res) => { 
        res.send("Copyright (c) 2022 mazk All rights reserved.")
    });
    
    // Listen localhost:6969 or public:6969 if firewall allow
    app.listen(port, async () => {
        console.log("Started Hosting on: http://localhost:" + port);
    });
};
```
--------------------------------------------------
<details>
<summary><h5>Addon [uptimerobot.com] Status Page</h5></summary>

```md
1: Register or Login.
2: Create new Monitor
3: Name it like "Discord Bot"
4: Set Monitor type as "HTTP(s)"
5: Set URL (or IP) as "http://publicip:port/" like ["128.218.12.34:6969/"]
6: Save Changes
```


</details>

--------------------------------------------------

</details>


<details>
<summary><h4>Discord.js V13 Bot - Embeds</h4></summary>

```js
const { MessageEmbed } = require('discord.js');

const ExampleEmbed = new MessageEmbed()
	.setColor('#4278f5') // https://g.co/kgs/AJQC7D google color picker
	.setTitle('Embed Title') // Embed Title
	.setURL('https://github.com/mazk5145') // Embed Title Url
	.setAuthor({ name: 'Author Name', iconURL: 'https://i.imgur.com/sZFxUoj_d.webp', url: 'https://github.com/mazk5145' }) //Author Name, Icon, Link
	.setDescription('Desc Content') // Embed Desc Content
	.setThumbnail('https://i.imgur.com/sZFxUoj_d.webp') // Thumbnail Picture
	.addField('Field Title', 'Field Value', true) // Fields
	.setImage('https://i.imgur.com/sZFxUoj_d.webp') // Embed Image
	.setTimestamp() // Add timestamp to your embed
	.setFooter({ text: 'Footer Text', iconURL: 'https://i.imgur.com/sZFxUoj_d.webp' }); // Embed Footer text + icon
```

**Credits**
```
https://discordjs.guide/popular-topics/embeds.html
```

</details>

<details>
<summary><h4>Template for later use</h4></summary>

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

### (TEMPLATE DON'T DELETE)
```js

```

</details>




## Usefull Sites
```
NPM: https://npmjs.com/
Discord Docs: https://discord.com/developers/docs/intro
Discord JS Docs: https://discord.js.org
Discord JS Github: https://github.com/discordjs/discord.js
```
