---
description: How to set up the messaging system with PYTHIA.
---

# Messaging Setup

!!! note
    You must invite the bot to your server to set up the messaging system. However, you do *not* need to set the player role for this system.

    Still, you should read up [the basic setup page](basic_setup.md) for more information on setting up the bot.

## Configuration

All configuration commands for the system can be found under the `/message-config` command. To take a look at your current gacha configuration, you can use `/message-config info`:

<figure markdown>
  ![An example of a messaging system configuration.](message_config.png)
</figure>

You can get a pretty good idea of what options are available to you just from this alone, but to change them:
- `/message-config toggle` turns the messaging system on or off. If the messaging system is turned off, players will not be able to send messages through the bot. By default, it is off.
- `/message-config anonymous-messaging` allows you to toggle whether or not users can send messages anonymously (IE a player can send a message without the receiver knowing who sent it). By default, they cannot.

And that's all for this part!

## Links

Even with an enabled messaging system, the system still has to be able to send messages to users. To do this, you need to set up links between a user and a channel the bot can send messages to.

Configuration of these links is largely done through `/message-manage`.

### Adding/Updating Links

To add or update a link, you can use the `/message-manage link` command, specifying the user to link and the channel to link them to. If all goes well, you should get a message back saying the link was added successfully:

<figure markdown>
  ![An example of adding a link.](message_link.png)
</figure>

!!! note
    The channel you link a user to must be a channel the bot can send messages to. Make sure your permissions are set up correctly!

### Listing Links

To see what links are currently in the system, you can use `/message-manage list-links`. This will give you a list of all links in the system, showing the user and the channel they are linked to.

<figure markdown>
  ![An example of /message-manage list-links.](message_list_links.png)
</figure>

### Removing and Clearing Link

To remove a link, you can use `/message-manage remove-link` and specify the user to remove the link from. If you want to remove all links, you can use `/message-manage clear-links`.

## Finally...

That's all! You should now have a fully functional messaging system set up with PYTHIA. You can now refer to the [messaging usage page](messaging.md) to see how players can use the messaging system.