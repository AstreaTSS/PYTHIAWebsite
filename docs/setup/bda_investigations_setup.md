---
description: How to set up BDA investigations with PYTHIA.
---

# BDA Investigations Setup

!!! note
    You must invite the bot and set up the basic settings before enabling BDA investigations - check [the basic setup page](basic_setup.md) for more information.

!!! warning
    The BDA investigation system present in PYTHIA is *vastly different* from the investigation system present in Ultimate Assistant - this system is meant more for murder investigations. It is suggested you read the respective ["Using the Bot" guide](bda_investigations.md) to understand the flow of this system compared to Ultimate Assistant.

    A general purpose investigation system is planned but may not come for a while; for now, you may want to check out [Chiaki Nanami](https://discord.com/application-directory/781034602533879838) (not affiliated), which has some (but not all) investigation features.

## Setting Up the Config

To use the BDA investigations feature, you need to establish a Truth Bullets (or whatever your RP calls them) channel, so that the bot knows where to send publicly discoverable Truth Bullets. To do that, select the `/bullet-config channel` command, _use the channel option_, and select the channel you want Truth Bullets to go in.

And you're technically ready! However, there are other commands worth noting:

* `/bullet-config best-finder` can be used to set a roll given to the people who find the most Truth Bullets. If this is not given, no role will be handed out to those who find the most, though as of right now, a message for who sent the most is still sent.
* `/bullet-config announce-best-finders` toggles whether or not the bot will announce who found the most Truth Bullets at the end of an investigation. This is on by default.
* `/bullet-config mode` allows you to change how Truth Bullets can be discovered. By default, they can be discovered through sending messages and through `/bda-investigate`, but you can change this so that only `/bda-investigate` works.
* `/bullet-config names` allows you to change how Truth Bullets (and the Best Finder) are named in *public-facing* messages. 
* `/bullet-config toggle` turns on or off triggering Truth Bullets. This'll be important later.

Saving the most important of the `/bullet-config` commands for last, to take a look at all of your configration settings for BDA investigations, you can use `/bullet-config info`:

<figure markdown>
  ![An example of a BDA investigation configuration.](bullet_config.png)
</figure>


## Setting Up Truth Bullets

### Adding Truth Bullets

Let's get started by adding Truth Bullets - use `/bullet-manage add` and select a channel to, well, add a Truth Bullet to a specific channel. This'll pop out a little button that can be used _at any time to add Truth Bullets to that channel._

<figure markdown>
  ![An example of said button.](add_bullets_button.png){ loading="lazy" }
</figure>

???+ tip "Hate Using the Button?"
    If you don't like using the button and would prefer if the command directly opened the pop-up below, you can specify the `send_button` option for `/bullet-manage add` to say "no" instead of the (default) "yes". This will send the prompt directly to you, bypassing the button.

    Do give the button a try, though - you might find it more convenient when you're adding a lot of Truth Bullets!

Once you click that button, a little pop-up will appear, asking you the trigger, a description (supports Discord markdown!), an optional image, and if you want to make the Truth Bullet you're adding hidden.

<figure markdown>
  ![The pop-up that appears while adding Truth Bullets.](add_bullet_modal.png){ loading="lazy" }
</figure>

???+ tip "Flexibility with Triggers"
    The trigger is designed to be flexible, so here are a few notes about what you can get away with:
    - You can use multiple words or a single word as a trigger.
    - Triggers are case-insensitive in terms of how they're triggered, so "oven" and "Oven" will act the same.
    - Trigger detection is _not_ word-bound, so "book" trigger will trigger on messages containing "*book*", "*book*s", "*book*shelf", "*book*!", etc., since they all have "book" in them.
    - If you need multiple triggers, look at aliases, described later.

??? note "Note about Images"
    Images, unlike in other systems, will be displayed at their full size in the Truth Bullet embed.

???+ tip "Hiding Truth Bullets"
    If you want to hide a Truth Bullet, you can do so by making the second question a "yes" instead of a no. This makes it so only the finder of the Truth Bullet sees it, instead of the Truth Bullet being published to a public channel. This is useful for secrets or other things you don't want everyone to know about.

    Doing this requires the bot to DM the user if investigating Truth Bullets through messages. If you use this, you may want to warn ahead of time that you should have DMs enabled with the server and/or the bot.

Specify those and press send - you should get a message able how that was done successfully!

Truth Bullets are unique _by their trigger by channel_, so while *multiple* channels can have a Truth Bullet with the same trigger, a *single* channel cannot have multiple Truth Bullets with the same trigger.

### Seeing Current Truth Bullets

After adding Truth Bullets, you probably want to get a good overview of them. Let's use `/bullet-manage list` to list out the ones we've made so far:

<figure markdown>
  ![An example of /bullet-manage list.](list_bullets.png){ loading="lazy" }
</figure>

As you can see, it already has a Truth Bullet in it. This command will list out Truth Bullets for every single channel and if they were found - this is a useful reference to have as you make Truth Bullets or even watch over an investigation (Truth Bullets that have been found will be marked as such).

To see a specific Truth Bullet's information, you can use `/bullet-manage info` with the channel and trigger of the Truth Bullet you want to see:

<figure markdown>
  ![An example of /bullet-manage info.](bullet_info.png){ loading="lazy" }
</figure>

As you can see, it's pretty basic, but it does list everything you would need to know. Most of these fields are empty (as expected), but we can always reference these later.

### Editing and Removing Truth Bullets

Editing a Truth Bullet is as simple as using `/bullet-manage edit` and specifying the channel and trigger of the Truth Bullet you wish to edit. A little pop-up will appear:

<figure markdown>
  ![The pop-up that appears while editing Truth Bullets.](edit_bullet_modal.png){ loading="lazy" }
</figure>

As you can see, it already has the Truth Bullet details - you'll be able to edit them from there (though you may want to temporarily move the contents to a proper text editor to edit things better). When you press submit, the Truth Bullet will be edited with the new trigger and description.

To remove a Truth Bullet, it's as simple as using `/bullet-manage remove` with the channel and trigger of the Truth Bullet you want to delete:

<figure markdown>
  ![An example of removing a Truth Bullet.](remove_bullet.png){ loading="lazy" }
</figure>

Removing _all_ Truth Bullets is as simple as running `/bullet-manage clear`. _This action is irreversible!_

### Other Commands

* To add an alias (an alternative trigger to trigger the same Truth Bullet), simply use the `/bullet-manage add-alias` command with the channel, trigger of the Truth Bullet, and the alias you wish to add to the Bullet. As you can imagine, `/bullet-manage remove-alias` follows a similar process.
* `/bullet-manage override-finder` and `/bullet-manage unfind` are more useful _during_ investigations, as you can imagine, but they simply allow you to either re-define who found a Truth Bullet or un-discover it so its trigger can be triggered once again.
* `/bullet-manage manual-trigger` allows you to manually trigger a Truth Bullet in the current channel, even allowing you to specify a finder if needed.
  * This can be used even when triggering Truth Bullets are *off*. If you prefer your players to discover Truth Bullets in a different way than what the bot allows but still would like some organization, this may be for you!
* `/help` is your friend! Use it to find more commands that could be useful to you!

## Starting a BDA Investigation

To start off a BDA investigation with all your Truth Bullets, simply run `/bullet-config toggle` and enable triggering Truth Bullets! Your players will now be able to discover any Truth Bullets you laid out for them, as seen in the [BDA investigations usage guide](bda_investigations.md). It's suggested that you do this once you get in your first BDA message with the initial hints in, though the bot gives you freedom on how to really do that.

A BDA investigation ends when _all Truth Bullets currently defined has been found_. Till then, keep an eye on your player's progress through `/bullet-manage list` and give hints as needed. Once all have been found, _the bot will automatically disable triggering bullets._ You'll need to turn on `/bullet-config toggle` again if you add a Truth Bullet for people to find them.

_**Truth Bullets are not deleted after an investigation. You MUST do this manually by using `/bullet-manage clear`!**_  Don't forget to do this - not doing so turns your Truth Bullets into a confusing mess of found and unfound Bullets. If you don't know if you've done it, use `/bullet-manage list` to verify it.
