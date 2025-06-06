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

Some basic options include:
- `/gacha-config names` allows you to change how the gacha system publicly displays the names of things like the currency and gacha rarities.
- `/gacha-config cost` sets the cost of each roll. By default, it costs 1 currency to roll, and users will need at least that amount to do so - you can adjust it how you like, though.
- `/gacha-config draw-duplicates` allows you to toggle whether or not users can draw items they already own from the gacha. By default, they can.
- Finally `/gacha-config toggle` turns on or off the gacha system. Players cannot use any of the gacha commands (as discussed on the [gacha usage page](gacha.md)) if the gacha system is turned off. It's suggested that you add your items before turning the gacha system on.

### Rarities

Rarities are a way to indicate how likely an item is to be drawn from the gacha. The rarer the item, the less likely it is to be drawn. The defaults for rarities are shown in the above configuration image, but you can change the fields you want to with `/gacha-config rarities`.

#### Rarity Colors

Editing rarity colors will determine the color of the embed (the color to the side of them) for items with a particular rarity.

<figure markdown>
  ![An example of editing rarity colors.](gacha_rarity_color.png)
</figure>

!!! note "Values for Rarity Colors"
    The values for rarity colors are in hexadecimal format, which is the same format used for colors in HTML and CSS. You can use a color picker to find the color you want, or you can use a website like [this one from Google](https://g.co/kgs/TxT34xV) to find the hex code for the color you want. The # is optional, and shortened hex codes (like #f00 for red) are *not* supported.

#### Rarity Odds

Editing rarity odds will determine how likely an item of that rarity is to be drawn from the gacha.

!!! note "Odds and Rolling Items"
    When a user rolls/draws/pulls an item, the bot will randomly select a rarity based on the odds you set. It will then randomly select an item from that rarity to give to the user.

    However, if there are no items of that rarity, the bot will *first* try to find an item of a lower rarity in descending rarity order, and if that fails, *then* it will try to find an item of a higher rarity in ascending rarity order. This means that even if you set the odds to 0% for a rarity, it may still be possible to get an item of that rarity if the bot has to do this search.

The odds are represented as a percentage, and the sum of all odds must equal 100%.

<figure markdown>
  ![An example of editing rarity odds.](gacha_rarity_odds.png)
</figure>

!!! note "Values for Rarity Odds"
    - If you wish, you can also use raw decimal values for the odds, such as 0.1. In that case, all values must add up to 1.0.
    - For percentage values, the max decimal precision is 2, so you can use values like 10.01%, for example. For raw decimal values, the max precision is 4, so you can use values like 0.1001.

#### Rarity Names

Rarity names can be changed through `/gacha-config names`. Do note that even if you change the names, when adding/editing items, you will still need to use the default rarity names (common, uncommon, rare, epic, legendary) in order to assign rarities to items.

## Items

### Adding Items

???+ note
    A gacha item is different from [item system](items_setup.md) items - it can only be interacted with through gacha commands and gotten through `/gacha roll/draw/pull`.

A gacha system isn't a gacha system without items! To add items, you can use the `/gacha-manage add-item` command. This will pop out a little button that can be used _at any time to add gacha items._

<figure markdown>
  ![An example of the button for adding gacha items.](add_gacha_button.png)
</figure>

???+ tip "Hate Using the Button?"
    If you don't like using the button and would prefer if the command directly opened the prompt below, you can specify the `send_button` option for `/gacha-manage add-item` to say "no" instead of the (default) "yes". This will send the prompt directly to you, bypassing the button.

    Do give the button a try, though - you might find it more convenient when you're adding a lot of items!

Once you click that button, a little prompt will appear to fill out the details of the item you want to add:

<figure markdown>
  ![An example of the prompt to add an item.](add_gacha_item_modal.png)
</figure>

You get a number of customization options here:
- The name and description are exactly what you expect. Names must be unique across different items. Both of these fields are required.
- The rarity is the rarity of the item, which will determine how likely it is to be drawn from the gacha. By default, items get created with a common rarity, but you can choose one of: common, uncommon, rare, epic, or legendary.
  - If you have changed the rarity names in the gacha configuration, those will *not* be reflected here.
  - Rarities are discussed more in the [rarities section](#rarities) above.
- The quantity is how many of this item you want to add to the gacha system. By default, there will be infinite amounts of this item - otherwise, for each time someone draws the item, its quantity decreases until it reaches 0 and can no longer be drawn for.
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

### Editing and Deleting Items

Editing an item is as simple as using `/gacha-manage edit-item` and specifying the item's name. A little pop-up will appear:

<figure markdown>
  ![An example of the prompt to edit an item.](edit_gacha_item_modal.png)
</figure>

As you can see, it already has the old fields populated in it - you'll be able to edit any property you want (including the name!). When you press submit, the item will be edited with the new properties.

To delete an item, it's as simple as using `/gacha-manage delete-item` with the name of the item you want to delete. Notably, this removes it from all player's item lists, so be careful!

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


### Exporting/Importing Items

If you wish to transfer items to another server, or just wish to create a shareable list of items in general, the process is simple.

To *export* items, you can use `/gacha-manage export-items`. This should give you a file ending in `.json`; this is a [JSON file](https://en.wikipedia.org/wiki/JSON), and it can be shared around freely. No private information is stored on these other than basic information about the items themselves.

You can also edit it directly if you wish; this should not be necessary, but can be done for advanced usecases. If you choose to do so, please expand the below note.

??? note "Notes for Editing JSON"
    While editing the JSON file, please keep in mind some limitations:

    - **You are generally expected to know how JSON files work. There will be no support given for editing JSON files.**
    - Keep the version number the same! The version number is used to indicate the format of the items, which makes sure JSON files work even in the future. Changing it can lead to unexpected side effects.
    - Stay to the format that your JSON file has. Any deviations will likely not be tolerated.
    - `rarity` can range from 1-5, and represent (in order) common, uncommon, rare, epic, and legendary.
    - When `amount` is `-1`, that means it is unlimited.
    - The bot enforces the same limitations as making items through the bot itself.

Regardless, you may import exported items through `/gacha-manage import-items` and giving your JSON file. This may be done from other servers other than the server where the file was exported from.

The bot, by default, will error out if there are any items in the export that overlap with items already in the server. To get around this, you can use the `override` option in `/gacha-manage import-items` to replace those items.

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
