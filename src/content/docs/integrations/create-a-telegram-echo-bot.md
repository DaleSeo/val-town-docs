---
title: Telegram  bot
generated: 1701279907743

---

You can create Telegram bots using vals.

In this example, you’ll create a val that uses the [HTTP Val](../http-val) to
receive webhooks from Telegram.

When users message your bot, the bot will reply with the same message.

### Create your bot by talking to `@BotFather`

Speak to Telegram’s [https://t.me/botfather](https://t.me/botfather) to create
your bot and obtain a bot token.

![Screenshot 2023-06-23 at 11.46.35.png](./create-a-telegram-echo-bot/screenshot_2023-06-23_at_114635.png)

### Add the bot token as a secret

Copy the bot token you just received and save it as a Val Town secret as
`telegramBotToken`.

### Check your token works

Call `@vtdocs.telegramGetMe` with your newly created secret to check that it
works.

<div class="not-content">
  <iframe src="https://www.val.town/embed/vtdocs.getMeExample" width="100%" frameborder="no" style="height: 400px;">
    &#x20;
  </iframe>
</div>

### Create a secret so you can verify webhooks

Generate a random string and save it as a Val Town secret as
`telegramWebhookSecret`.

### Create a webhook handler to receive messages

When Telegram users send messages to your bot, they will be forwarded to your
webhook handler. We’ll use the secret we just created to verify that the message
came from our bot.

Fork this val that uses the [HTTP Val](../http-val) :

<div class="not-content">
  <iframe src="https://www.val.town/embed/neverstew.telegramWebhookEchoMessage" width="100%" frameborder="no" style="height: 400px;">
    &#x20;
  </iframe>
</div>

### Tell your bot about the webhook handler

Use `@vtdocs.telegramSetWebhook` to tell your bot where to send webhooks.

<div class="not-content">
  <iframe src="https://www.val.town/embed/neverstew.setWebhookExample" width="100%" frameborder="no" style="height: 400px;">
    &#x20;
  </iframe>
</div>

### Send a message to your bot to check it works!

It should echo back the message like this:

![Screenshot 2023-06-23 at 13.17.52.png](./create-a-telegram-echo-bot/screenshot_2023-06-23_at_131752.png)

Not working? Try debugging the webhook handler you created via the
[Evaluations tab](https://www.val.town/settings/evaluations). Or get help on Val
Town’s [Discord](https://discord.gg/dHv45uN5RY).