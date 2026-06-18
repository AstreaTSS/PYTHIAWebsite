---
description: How to manage the dice system with PYTHIA.
---

# Dice Management

!!! note
    You must invite the bot to your server to use the dice system. However, you do *not* need to set the player role for this system.

    Still, you should read up [the basic setup page](basic_setup.md) for more information on setting up the bot.

## Configuration

As per usual, all configuration commands for the dice system can be found under the `/dice-config` command. To take a look at your current dice configuration, you can use `/dice-config info`:

<figure markdown>
  ![An example of a dice configuration.](dice_config.png)
</figure>

Noticably, there is only one option here: `/dice-config visibility`. This command allows you to toggle whether or not the results of dice rolls are visible to everyone in the server. By default, they are visible to everyone in the channel the roll was made in.

!!! note "Old Visibility Setting"
    Before December 2nd, 2024, the visibility defaulted to "hidden" instead of "public". As such, servers that had PYTHIA before this date will have the visibility set to "hidden" unless it was changed.

=== "Public (Default)"

    <figure markdown>
      ![An example of rolling dice while visibility is set to public.](dice_roll.png)
    </figure>

=== "Hidden"

    <figure markdown>
      ![An example of rolling dice while visibility is set to hidden.](dice_roll_hidden.png)
    </figure>

This does mean the dice system *cannot be disabled through the bot* - this is purposeful, because at worst, the system will not create messages in the server proper anyways. That being said, you can disable the `/dice` command through [Discord's application command permissions](https://web.archive.org/web/20240519053816/https://support.discord.com/hc/en-us/articles/4644915651095-Command-Permissions) (links to archive.org as page has been deleted).

## Management

Also per usual, all management commands for the dice system can be found through `/dice-manage`.

Notably, *users can manage their set of die through the `/dice` commands* (as seen in the [dice usage guide](dice.md)). These commands allow you to manage their dice too though, so this may be useful for roleplays where stat systems are used.

### Adding/Registering Dice for Users

To register a die for a user, you can use the `/dice-manage register-for`:

!!! note "Dice Notation"
    The die/dice notation supported by this bot is based on [Avrae's notation](https://avrae.io/commands#roll), so *most* notation for that bot should work here. That being, said modifications have been made to the system to support a few more common dice notations (such as using ! without a number for explosions).

    For a detailed list of the syntax supported by this bot, you can check [the notation parser's page](https://github.com/AstreaTSS/apollo-d20?tab=readme-ov-file#dice-syntax).

<figure markdown>
  ![An example of registering a die for a user.](dice_register_for.png)
</figure>

From there, the user would be able to use this die [through `/dice roll-registered`](dice.md#rolling-registered-die).

### Listing/Removing Users' Registered Dice

To see what dice are currently registered for a user, you can use `/dice-manage list-for`:

<figure markdown>
  ![An example of listing die for a user.](dice_list_for.png)
</figure>

To remove a die from a user, you can use `/dice-manage remove-from`. This will remove the die from the user's set of die.

To clear all registered dice for a user, you can use `/dice-manage clear-for`. To clear *every registered die for every user*, you can use `/dice-manage clear-everyone`.

### Rolling Users' Registered Die

To roll a user's die, you can use `/dice-manage roll-registered-for`:

<figure markdown>
  ![An example of rolling a registered die of the user.](dice_roll_registered_for.png)
</figure>

This command, by default, makes the message visible to all. If you do not want this, you can use the `hidden` option to make the message only visible to you.

### Exporting/Importing Registered Dice For A User

If you wish to transfer registered dice for a user to another server, or just wish to create a shareable list of registered dice in general, the process is simple.

To *export* dice, you can use `/dice-manage export-for` and specify the user. This should give you a file ending in `.json`; this is a [JSON file](https://en.wikipedia.org/wiki/JSON), and it can be shared around freely. No private information is stored on these other than basic information about the items themselves.

You can also edit it directly if you wish; this should not be necessary, but can be done for advanced use cases. If you choose to do so, please expand the below note.

??? note "Notes for Editing JSON"
    While editing the JSON file, please keep in mind some limitations:

    - **You are generally expected to know how JSON files work. There will be no support given for editing JSON files.**
    - Keep the version number the same! The version number is used to indicate the format of the items, which makes sure JSON files work even in the future. Changing it can lead to unexpected side effects.
    - Stay to the format that your JSON file has. Any deviations will likely not be tolerated.
    - The bot enforces the same limitations as making items through the bot itself.

You may import exported dice for a user through `/dice-manage import-for` and giving your JSON file. This may be done from other servers other than the server where the file was exported from.

The bot, by default, will error out if there are any dice in the export that overlap with dice already in the server for the user. To get around this, you can use the `override` option in `/dice-manage import-for` to replace those dice.