# discord-gs2
Connect to discord (sorta) using GS2

Some stuff you need:
http://forums.graalonline.com/forums/showthread.php?t=134265118

 First create the client

```js
function onCreated() {
  createBot();
}

function createBot() {
  this.bot  = new TDiscord("Bot");
  Bot.debug = true;
  Bot.login(TOKEN);
}
```

 Then do stuff with it

```js
// called from login() func
function Bot.onReady() {
  temp.embed = Bot.newRichEmbed()
  .setTitle(getServerName())
  .setDescription("Some info here")
  .setURL("http://www.someSite.com")
  .addField("Playercount", allplayers.size())
  .addField("CPU", getprocesscpuusage() * 100)
  .setAuthor("NPC-Server", "http://www.somesite.com", "https://cdn.discordapp.com/embed/avatars/0.png");

  Bot.channels.find("id", 69696969).sendEmbed("Bot ready!", temp.embed);
}

// Bot synced data
function Bot.onSynced() {
  Bot.channels.find("xmlname", "General").sendMessage("Bot updated!", {
    {"tts", true}
  });
}
```

Also,

You can connect to a webhook easily

```js
  this.client = new TWebhookClient();
  this.client.connect(idOrUrl, token); // token not needed if using url
  this.client.sendMessage("This is a webhook");
```
