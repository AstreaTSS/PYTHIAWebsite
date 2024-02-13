---
title: Ultimate Investigator
description: A bot made to help automate investigations during Danganronpa roleplays.
---

# Ultimate Investigator

<figure markdown>
  ![Ultimate Investigator's Banner](assets/ui_banner.jpg)
</figure>

Ultimate Investigator is a bot meant to help out investigations with Danganronpa roleplays. More specifically, this helps out with "typical" investigations: investigations where users are expected to find key words to get Truth Bullets.

For example, moderators can:

- Set up Truth Bullets for users to find in specific channels:
<figure markdown>
  ![The pop-up that appears while adding Truth Bullets.](assets/add_bullet_modal.png){ loading="lazy" }
</figure>

- Manage Truth Bullets, including editing and removing them:
<figure markdown>
  ![An example of /list-bullets.](assets/list_bullets.png){ loading="lazy" }
</figure>
<figure markdown>
  ![An example of /bullet-info.](assets/bullet_info.png){ loading="lazy" }
</figure>

- Adjust other settings, like who can trigger Truth Bullets and if a role is awarded to the person who finds the most Truth Bullets:
<figure markdown>
  ![An empty server /config info.](assets/guild_config.png)
</figure>

Then, when Truth Bullet discovery is enabled, users can trigger a Truth Bullet by saying a specific phrase in a channel:
<figure markdown>
  ![Example of a message triggering a Truth Bullet.](assets/trigger_example.png)
  <figcaption>Notice how the trigger is "ink", as represented by the underline and the word in codeblocks in the embed.</figcaption>
</figure>

And the bot, as seen above, will reply with the Truth Bullet in the same channel and in a separate channel "Truth Bullets" channel.

To see more information, you can either look at:
- [Using the Bot as a User](using_the_bot.md)
- [The Server Setup Guide](server_setup.md)