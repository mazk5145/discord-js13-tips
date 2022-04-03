# discord-js13-tips
i will add sum discord.js v13 scripts / tips here


<details OPEN>
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

<details OPEN>
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

## Usefull Sites
```
NPM: https://npmjs.com/
Discord Docs: https://discord.com/developers/docs/intro
Discord JS Docs: https://discord.js.org
Discord JS Github: https://github.com/discordjs/discord.js
```
