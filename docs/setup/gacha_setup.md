---
description: How to set up the gacha system with PYTHIA.
---

# Gacha Setup

!!! note
    You must invite the bot and set up the basic settings before setting up the gacha system - check [the basic setup page](basic_setup.md) for more information.

## Configuration

All configuration commands for the gacha can be found under the `/gacha-config` command. To take a look at your current gacha configuration, you can use `/gacha-config info`:

<figure markdown>
  ![An example of a gacha configuration.](gacha_config.png)
</figure>

You can get a pretty good idea of what options are available to you just from this alone, but to change them:
- `/gacha-config names` allows you to change how the gacha system names things in most messages.
- `/gacha-config cost` sets the cost of each roll. By default, it costs 1 currency to roll, and users will need at least that amount to do so - you can adjust it how you like, though.
- `/gacha-config draw-duplicates` allows you to toggle whether or not users can draw items they already own from the gacha. By default, they can.

Finally `/gacha-config toggle` turns on or off the gacha system. Players cannot use any of the gacha commands (as discussed on the [gacha usage page](gacha.md)) if the gacha system is turned off. It's suggested that you add your items before turning the gacha system on.

## Items

### Adding Items

A gacha system isn't a gacha system without items! To add items, you can use the `/gacha-manage add-item` command. This should send you a prompt to fill out:

<figure markdown>
  ![An example of the prompt to add an item.](add_gacha_item_modal.png)
</figure>

???+ note "Is Using Slash Commands Repeatedly Too Slow?"
    If you find that using slash commands is too slow for you while adding items, you can use the `send_button` option for `/gacha-manage add-item` to send a button. The button, every time it's clicked, will send the (above) prompt to add an item. While this may seem unorthodox, it can really help, so try it!

    <figure markdown>
      ![An example of the button for adding gacha items.](add_gacha_button.png)
    </figure>

    At some point in the future, this may be made the default behavior for adding items.

You get a number of customization options here:
- The name and description are, well, exactly what you expect. Names must be unique across different items. Both of these fields are required.
- The quantity is, well, how many of this item you want to add to the gacha system. By default, there will be infinite amounts of this item - otherwise, for each time someone draws the item, its quantity decreases until it reaches 0 and can no longer be drawn for.
- The image is optional, but if you provide a URL to an image, it'll be displayed when a player draws the item (as a thumbnail in an embed). This can be useful for showing off what the item looks like.

Once you fill out the prompt, you should get a message about how the item was added successfully!

### Listing Current Items

To see what items are currently in the gacha system, you can use `/gacha-manage list-items`. This will give you a list of all items in the gacha system, a shortened view of their description, and their quantity (if they have one that isn't infinite).

<figure markdown>
  ![An example of /gacha-manage list-items.](list_gacha_items.png){ loading="lazy" }
</figure>

### Viewing Item

If you want to see more information about a single item, you can use `/gacha-manage view-item` and specify the name of the item you want to see. This will give you a more detailed view of the item, including its description, quantity, and image (if it has one).

<figure markdown>
  ![An example of /gacha-manage view-item.](view_gacha_item.png)
</figure>

### Editing and Removing Items

Editing an item is as simple as using `/gacha-manage edit-item` and specifying the item's name. A little pop-up will appear:

<figure markdown>
  ![An example of the prompt to edit an item.](edit_gacha_item_modal.png)
</figure>

As you can see, it already has the old fields populated in it - you'll be able to edit any property you want (including the name!). When you press submit, the item will be edited with the new properties.

To remove an item, it's as simple as using `/gacha-manage remove-item` with the name of the item you want to delete. Notably, this removes it from all player's item lists, so be careful!

### Adding Items To/Removing Items From Players

If needed, you can manually add or remove items from a player's inventory.

To add an item to a player, you can use `/gacha-manage add-item-to` and specify the user, the item, and optionally, the quantity you want to add (if not specified, it defaults to 1):

<figure markdown>
  ![An example of /gacha-manage add-item-to.](gacha_add_item_to.png)
</figure>

To remove an item from a player, you can use `/gacha-manage remove-item-from` and specify similar properties. For quantity, if not specified, it defaults to *however many of the item the player has*.

!!! note
    By default, `/gacha-manage add-item-to` and `/gacha-manage remove-item-from` will not adjust the quantity of the item in the gacha system. To do so, use the option:
    - `remove_amount_from_gacha` for `/gacha-manage add-item-to`.
    - `replenish_gacha` for `/gacha-manage remove-item-from`.

## Currency

Everything about currency is managed by you through bot commands. To clarify: *there are no ways for players to earn currency on their own, so you must give it to them manually.*

### Adding Currency

Adding currency to a single player is easy. Simply use `/gacha-manage add-currency` with the user and the amount you wish to give:

<figure markdown>
  ![An example of /gacha-manage add-currency.](add_currency_gacha.png)
</figure>

However, this may take a while when you want to add currency to every player. PYTHIA includes a shortcut in the form of `/gacha-manage add-currency-players`, which will add the currency given to all members with the players role. This may take a while!

### Removing Currency

Removing currency is as simple as using `/gacha-manage remove-currency` with the user and the amount you wish to take away:

<figure markdown>
  ![An example of /gacha-manage remove-currency.](remove_currency_gacha.png)
</figure>

There is no way of directly transferring currency from one member to another as a staff member, but you can simulate the process with the available commands

### List Currency Amounts

To see how much currency every player has, you can use `/gacha-manage list-currency-amounts`. This will give you a list of all players with the players role and how much currency they have.

<figure markdown>
  ![An example of /gacha-manage list-currency-amounts.](list_currencies_gacha.png)
</figure>

## View Profile

To view the items and currency a user has, you can use the `/gacha-manage user-profile` commands:

<figure markdown>
  ![An example of /gacha-manage user-profile.](user_profile_gacha.png)
</figure>

## Resetting and Clearing

- `/gacha-manage reset-currency` resets the currency amount for a particular user.
- `/gacha-manage reset-items`, in a similar manner, resets all items for a particular user.
- `/gacha-manage clear-user` clears *all* data about a user, including both currency and items.
- Finally, `/gacha-manage clear-everything` clears *all* data about *every* user, including both currency and items. _This action is irreversible!_

## Finally...

Once you're settled, feel free to enable the gacha system with `/gacha-config toggle`, as mentioned earlier! Players will then be able to use the gacha system as described in the [gacha usage guide](gacha.md).
