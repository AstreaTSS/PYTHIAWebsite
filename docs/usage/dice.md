---
description: How to use the dice system with PYTHIA as a user.
---

# Dice

The dice system is a convenient way to roll and manage dice for yourself in your roleplay server. Noticably, the system is available on every server the bot is in (though dice are registered on a per-server basis).

!!! note
    All user/player-facing dice commands are stored in `/dice`.

## Rolling Dice

To roll dice, you can use `/dice roll` followed by the dice notation you want to roll:

!!! note "Dice Notation"
    The die/dice notation supported by this bot is based on [Avrae's notation](https://avrae.io/commands#roll), so *most* notation for that bot should work here. That being, said modifications have been made to the system to support a few more common dice notations (such as using ! without a number for explosions).

    For a detailed list of the syntax supported by this bot, you can check [the notation parser's page](https://github.com/AstreaTSS/apollo-d20?tab=readme-ov-file#dice-syntax).

<figure markdown>
  ![An example of rolling dice.](dice_roll.png)
</figure>

!!! note "Visibility"
    By default for most servers, the results of dice rolls are only visible to you. You can ask the staff to [change this setting](dice_management.md#configuration) if you want the results to be visible to everyone.

### Adding/Registering Dice

To register a die for yourself, you can use the `/dice register`:

<figure markdown>
  ![An example of registering a die for yourself.](dice_register.png)
</figure>

### Listing/Removing Dice

To see what die are currently registered, you can use `/dice list`:

<figure markdown>
  ![An example of listing die.](dice_list.png)
</figure>

To remove a registered die, you can use `/dice remove`.

### Rolling Registered Die

To roll a registered dice, you can use `/dice roll-registered`:

<figure markdown>
  ![An example of rolling a registered die.](dice_roll_registered.png)
</figure>