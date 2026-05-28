---
description: How to use BDA investigations with PYTHIA as a user.
---

# BDA Investigations 

You're likely here because a server you're in is using PYTHIA and is using it to power BDA investigations (murder investigations). Essentially, the bot (mostly) automates what a "traditional" investigation done by the staff of a server would do, but this'll guide you on what that means.

Typically, the mods will give you some sort of starting message for an investigation in a particular channel. Let's look at an example for a kitchen that has important Truth Bullets:

> *The kitchen seems to have a few details worth looking at... like the bleach that's everywhere.*

This message contains hints about a **trigger** - words/phrases that are needed to trigger a new Truth Bullet.

## Triggers

Trigger can be a lot of things - it can be a body, a piece of paper, the trash can, etc. That may sound vague, but it'll make sense once we take a closer look at this message.

Here, the mods pretty clearly want us to investigate that bleach first. The question is how to investigate that with the bot... and it's actually really simple!

All you need to do is send a message with the word "bleach" (case-insensitive) somewhere in it in the kitchen channel. For example, it could look like these:

> In normal cases, seeing a bit of _bleach_ in the kitchen wasn't a cause of concern, but this wasn't a normal scenario. Might as well investigate it.
>
> "I could smell that _bleach_ from a mile away, I swear..."
>
> "Was someone *bleach*ing the kitchen floor or something?"  (OOC Note: This is meant to show how the trigger does not have to be a standalone word.)
> 
> Bleach (OOC Note: Yes, this simple example works - after all, it does have the word "bleach." Try not to do this though - it ruins the fun of investigating for everyone.)

Usually, a staff member would step in to show a Truth Bullet related to the bleach, but in this case, the bot will reply instead with something like this in both the channel you're in and your Truth Bullets channel:

<figure markdown>
  ![Example of a message triggering a Truth Bullet.](trigger_example.png)
  <figcaption>The message that triggered the Bullet, in this case.</figcaption>
</figure>


And that's it - you've investigated the bleach! The trigger here was "bleach" - the staff set it up so that the bot would do this with that phrase. You can try to say multiple triggers, but the bot will only do one (decided essentially at random) - best to space them out, or even let other players do them for you.

You could investigate the rest of the suspicious things in the same way. Things like "\[My OC] decided to look at the _bucket_." would trigger a new Truth Bullet, and there are some triggers in the above example image to find even more of them. The idea is to keep following the little hints about triggers/important things to investigate until you've found them all, which the bot will note if you've done so in the Truth Bullets channel.

### Alternate Investigation Method

As a solution matching a certain other bot, if you don't wish to send a whole message, you can use `/bda-investigate` with the *exact trigger* (case insentiive) to trigger a Truth Bullet. For example, `/bda-investigate bleach` would trigger the same Truth Bullet as the examples above.

Some servers may require only this method, so it's good to know about it.

### Hidden Truth Bullets

Some Truth Bullets may be marked as hidden - this means that only you, the finder of the Truth Bullet, will see it. The bot will DM you if you sent a message with the trigger, or send a response only visible to you if you use `/bda-investigate`, to show you the Truth Bullet. The staff will likely want you to keep them secret until a certain point, so be careful with them!

This does require DMs with the bot to be enabled. Hopefully, the staff will warn you ahead of time if they're planning on using hidden Truth Bullets.

## Notes

* It's worth noting that depending on who sets up the Truth Bullets, you may be able to get away with using _alternative phrases_ to trigger a Truth Bullet. These are called _aliases_, and they're handy in case, for example, you have to face the differences between American and British English.
* There can only be one Truth Bullet with a specific trigger _per channel._ You may need to look around in other channels to find everything!
* The final "All Truth Bullets have been found" message will also include who found the most Truth Bullets, and if your staff members set it up, it'll also give a special role to them.
