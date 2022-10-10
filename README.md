# Formal, a Discord moderation bot.

## How to use.

First, you need to clone the repository: `git clone https://github.com/FormalSnake/Formal.git`

Then you go into the Formal directory: `cd Formal`

Then you need to install the dependencies, but make sure you have nodeJS installed: `npm install`

When you run `npm start`, you might see an error saying you have an invalid token, so what you need to do is go here: https://discordjs.guide/preparations/setting-up-a-bot-application.html
Then you make a config.json file in the root directory, with the following contents:

```
{
  "token": "Your bot token, keep this safe!",
  "clientId": "The client ID of your bot account",
  "guildId": "The ID of your server"
}
```

And that is it! You can now add your bot to your Discord server and then run `npm start`

## How to add commands.

Making commands has been made easy for you, but you need JavaScript knowledge.

head to `src/commands` and create a script called `greeting.js`.

At the top of the script, add the following line: `const { SlashCommandBuilder } = require("discord.js");`, this imports the discord.js SlashCommandBuilder package.
Then, you need to add the actual contents of the command, and what it needs to do:

```
module.exports = {
  // This configures the command name and description
  data: new SlashCommandBuilder()
    .setName("Greeting")
    .setDescription("Replies with a nice greeting!"),
  async execute(interaction) {
    // In here, you can execute functions, or in this case send a message!
    return interaction.reply("Hello there!");
  },
};
```

And now it is ready! Just make sure to stop the bot, execute `npm run deploy-commands`, and if it does not give any errors, you can start your bot!

## If you have problems...

Just create a issue.
