# discord-gs2
Connect to discord (sorta) using GS2

 First create the client

```js
  this.bot  = new TDiscord("Bot");
  Bot.debug = true;
  Bot.login(TOKEN);
```

 Then do stuff with it

```js
  temp.embed = TDiscord.newRichEmbed()
  .setTitle(getServerName())
  .setDescription("Some info here")
  .setURL("http://www.someSite.com")
  .addField("Playercount", allplayers.size())
  .addField("CPU", getprocesscpuusage() * 100)
  .setAuthor("NPC-Server", "http://www.somesite.com", "https://cdn.discordapp.com/embed/avatars/0.png");

  temp.channel = Bot.guilds.find("id", "69696969").createChannel("server-" @ getServerName() , "text");
  temp.channel.sendEmbed("Hello discord!", temp.embed);
```

Also,

You can connect to a webhook easily

```js
  this.client = new TWebhookClient();
  this.client.connect(idOrUrl, token); // token not needed if using url
  this.client.sendMessage("This is a webhook");
```
