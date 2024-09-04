---
date: 2024-09-04
authors:
  - astrea
categories:
  - Updates

description: An update post for early September 2024.
comments: true
---

# Update Post - Early September 2024

It's been a while since the last update post, mostly thanks to college starting up again. But I'm back with some new features and changes to the bot, all centered on the gacha system. Let's get into it!

<!-- more -->

## Adding Items To/Removing Items From Players

A new feature has been added to the gacha system: the ability to manually add or remove items from a player's inventory. This can come in handy for a number of reasons, like simulating trades or giving items to players for free.

To add an item to a player, you can use `/gacha-manage add-item-to` and specify the user, the item, and optionally, the quantity you want to add (if not specified, it defaults to 1):

<figure markdown>
  ![An example of /gacha-manage add-item-to.](gacha_add_item_to.png)
</figure>

To remove an item from a player, you can use `/gacha-manage remove-item-from` and specify similar properties. For quantity, if not specified, it defaults to *however many of the item the player has*.

!!! note
    By default, `/gacha-manage add-item-to` and `/gacha-manage remove-item-from` will not adjust the quantity of the item in the gacha system. To do so, use the option:
    - `remove_amount_from_gacha` for `/gacha-manage add-item-to`.
    - `replenish_gacha` for `/gacha-manage remove-item-from`.

## Faster Way Of Adding Items To Gacha

Ever found adding items to the gacha system a bit tedious? Well, now you can add multiple items at once! Just use `/gacha-manage add-item` with the `send_button` to send a button. The button, every time it's clicked, will send the (above) prompt to add an item. While this may seem unorthodox, it can really help, so try it!

<figure markdown>
  ![An example of the button for adding gacha items.](add_gacha_button.png)
</figure>

At some point in the future, this may be made the default behavior for adding items.

## Other Adjustments

- `/gacha profile` and `/gacha-manage user-profile` now group together items, meaning that items of the same type will be listed together with a note noting how many the player has.
- Items are now sorted alphabetically throughout the gacha system.
- Truth Bullets are also now sorted alphabetically. No, this is not part of the gacha system, but it was a change that was made.