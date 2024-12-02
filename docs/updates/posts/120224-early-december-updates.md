---
date: 2024-12-02
authors:
  - astrea
categories:
  - Updates

description: An update post for early December 2024.
comments: true
---

# Update Post - Early December 2024

Since the last update post, there have been a few changes to the bot, including new configuration settings. Let's get into it!

<!-- more -->

## Breaking Changes

### Adding Items to the Gacha System

The `/gacha-manage add-item` command now *sends a button by default.* This is to make it easier to add items to the gacha system, as the time to type out the slash command over and over again can add up.

You should give it a try before doing so, but if you don't like using the button and would prefer if the command directly opened the prompt (like before), you can specify the `send_button` option for `/gacha-manage add-item` to say "no" instead of the (now default) "yes". This will send the prompt directly to you, bypassing the button.

### Dice Visibility

For servers that invite PYTHIA after December 2nd, 2024, the visibility of dice rolls will default to "public" instead of the old "hidden". This means that by default, everyone in the server will be able to see the results of dice rolls.

## Other Changes

### `/message-config ping-on-message`

The messaging system has a new (at least since the last update) configuration setting: `/message-config ping-on-message`. This setting allows you to toggle whether or not the bot should ping the user who sent the message when a message is sent. This replices the behavior of Ultimate Assistant.

### `/bullet-config announce-best-finders`

The BDA investigation system has a new configuration setting: `/bullet-config announce-best-finders`. This setting allows you to toggle whether or not the bot will announce (and ping) who found the most Truth Bullets at the end of an investigation. This is on by default, but turning this off may be ideal if you wish to deemphasize the competitive aspect of the system.

On a related note, the final message the bot sends after a BDA investigation has ended has been updated to look more modernized and to support the above.
