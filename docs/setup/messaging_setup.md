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
- `/message-config mode` changes the mode of the messaging system, which changes how messages are sent to users. See the [Modes](#modes) section below for more information on the different modes.
- `/message-config anonymous-messaging` allows you to toggle whether or not users can send messages anonymously (IE a player can send a message without the receiver knowing who sent it). By default, they cannot.
- `/message-config ping-on-message` allows you to toggle whether or not the bot will ping the receiver when they receive a message. By default, it is *off*.

### Modes

`/message-config mode` allows you to change the mode of the messaging system. The mode changes how messages are sent to users.

By default, the mode is *"Public Thread Per User"*, which means that when a message is sent to a user, the bot will look for a public thread in the linked channel that matches the user.
If it finds one, it will send the message there; if it doesn't, it will create one and then send the message there.

Here's an example of what that looks like when `@astrea.tss` sends a message to `@hecatetss`:

<figure markdown>
  ![An example of AstreaTSS sending a message to HecateTSS.](message_mode_threads.png)
</figure>

There are two other modes available as well:

- *"Private Thread Per User"* is the same as "Public Thread Per User", except the bot will create private threads instead of public threads. This is only recommended if the linked channel is a public channel.
- *"Classic (All Messages In One Channel)"* is a more classic way of doing messaging systems, where all messages to users are sent in the linked channel directly, without using threads. This replicates the behavior of Ultimate Assistant.

<figure markdown>
  ![An example of the classic messaging mode.](message_mode_classic.png)
  <figcaption>An example of the classic messaging mode when @astrea.tss sends a message to @hecatetss.</figcaption>
</figure>

!!! note "Old Mode Setting"
    Before June 18th, 2026, the messaging mode defaulted to "Classic" instead of "Public Thread Per User". As such, servers that had PYTHIA before this date and used the messaging system will have the mode set to "Classic" unless it was changed.

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

### Threads

!!! warning
    - **These commands only work for messaging modes that use threads** (IE "Public Thread Per User" and "Private Thread Per User").
    - **These commands are only meant for power users!** By default, PYTHIA will automatically create and manage threads for users as needed.

If you are using a messaging mode that uses threads, then PYTHIA will automatically create threads for users when it needs to send them a message.
However, if you want to manage these threads yourself, you can use the `/message-manage threads` commands.

#### View For User

To view the thread for a user, you can use `/message-manage threads view-for` and specify the user. This will give you a list of the thread(s) for that user.

<figure markdown>
  ![An example of viewing threads for a user.](message_threads_view_for.png)
  <figcaption>In this example, we can see anonymous messages meant for Hecate are sent to one threads, and messages sent by Astrea to Hecate are sent to another thread.</figcaption>
</figure>

#### Set Thread

To set a thread for a user, you can use `/message-manage threads set`:
- `user` specifies the user to set the thread for.
- `other_user` specifies the other user in the conversation. For example, if `user` is @Hecate and `other_user` is @Astrea, this would set the thread for messages between Hecate and Astrea *for Hecate*.
- `thread` specifies the thread to set.

<figure markdown>
  ![An example of setting a thread for a user.](message_threads_set.png)
</figure>

To set a thread for anonymous messages, you can use the same `/message-manage threads set-anonymous` command, which has the same options except `other_user`.

#### Unset Thread

`/message-manage threads unset` and `/message-manage threads unset-anonymous` work the same way as the set variants, except they unset the thread instead of setting it.

## Finally...

That's all! You should now have a fully functional messaging system set up with PYTHIA. You can now refer to the [messaging usage page](messaging.md) to see how players can use the messaging system.