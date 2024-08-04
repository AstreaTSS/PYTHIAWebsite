---
description: How to use the messaging system with PYTHIA as a user.
---

# Messaging

The messaging system is a way for you to send messages to other players through a set channel in your roleplay server. If the staff members in your server have set it up, here's how you can use it!

!!! note
    All user/player-facing messaging commands are stored in `/message`.

## Sending a Message

To send a message, you can use `/message send` followed by the user you want to send a message to and the message you want to send. Once you send the message, it will be sent to the user's channel, and a copy of the message will be sent to your channel. Here's an example of what that looks like:

<figure markdown>
  ![An example of the message that appears in your channel.](message_receipt.png)
  ![An example of the message that appears in the user's channel.](message_to_user.png)
</figure>

### Multi-line Messages

You may have noticed that slash commands don't allow for multi-line messages. To send a multi-line message, you can instead use the text/prefixed variant of the command, `@BOTMENTION message send @USER <message>`. Here's an example:

<figure markdown>
  ![An example of a multi-line message using a text command.](message_send_prefixed.png)
</figure>

This is also convienent for sending messages fast, though try not to spam the bot with too many messages at once!

!!! note "Usage Notes"
    In this example, the testing bot was mentioned. Of course, you should mention the main "PYTHIA" bot instead.

    If you think `message` takes up too many characters, you can replace it with `msg`. If you're feeling a bit old-school, you can also replace `send` with `whisper`.

## Anonymous Messages

*If* the staff members have enabled anonymous messaging, you can send messages without the receiver knowing who sent it. To send an anonymous message, you can use `/message anon` followed by the user you want to send a message to and the message you want to send.

The receiving user will then receive a message that will not show who sent it. Here's an example of what that looks like:

<figure markdown>
  ![An example of an anonymous message.](message_anon.png)
</figure>

!!! note
    Anonymous messaging is not enabled by default. If you want to send an anonymous message, you will need to check with the staff members in your server to see if they have enabled it.

    Anonymous messages are not truly anonymous - a copy of the message is still sent to your channel, so staff members can still see who sent the message.

    You can send multi-line anonymous messages in the same way as regular messages, just using `message anon` instead of `message send`.