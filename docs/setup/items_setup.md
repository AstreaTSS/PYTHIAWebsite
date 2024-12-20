---
description: How to set up the items system with PYTHIA.
---

# Items Setup

!!! note
    You must invite the bot and set up the basic settings before setting up the items system - check [the basic setup page](basic_setup.md) for more information.

The items system is PYTHIA's answer to Ultimate Assistant's investigation and inventory system, allowing you to create items, place them in channels, and have players find and take them (and even let them drop the items again). You can function this system as a simple item management system, or use it as a general-purpose investigation system, or more!

While this system has been made as simple as possible, it is a bit more involved than other systems, and differs from how Ultimate Assistant handled things. As such, we will begin with a brief overview of the system before diving into the setup.

(To skip this overview, click [this link](#configuration) to jump to the configuration section.)

## Overview

The core of the items system, is, well, items. To start off doing anything with the system, **you must create items** *before* you can place them down or give them to users.

For example, in the below diagram, we create a "Pineapple" item for the system.

<figure markdown>
  ![A diagram showing what happens when you create an item.](create_item_diagram.png)
</figure>

*After* we create an item, **we can place down items in a channel/room**. For example, the below shows what happens when we want to place down two pineapples in a channel called "Kitchen."

!!! note
    When items are placed in either a channel or (as discussed later) put in a player's inventory, the channel/user is said to be **possessing** the item. This terminology is used in a few commands and messages.

<figure markdown>
  ![A diagram showing what happens when you place items.](place_items_diagram.png)
</figure>

Once we've placed down items in a channel, **players/users can then look for items in the channel**. For example, in the below diagram, a player finds one of the pineapples we placed down while in the kitchen.

<figure markdown>
  ![A diagram showing a user looking for items in a channel.](items_here_diagram.png)
</figure>

Finally, if the item is takeable, **the player can then take the item**. Here, the player takes one of the pineapples, putting one in their inventory while leaving the other in the kitchen.

<figure markdown>
  ![A diagram showing a user take an item.](items_take_diagram.png)
</figure>

Essentially, in the system:
- **You create/define items** to use in the system.
- **You place created/defined items** in channels/rooms for players to find.
  - Though not shown in the diagrams, you can also put items in a player's inventory directly.
- **Players find items** in channels/rooms.
- **Players take items** they find if they can (some items may be immovable).

## Configuration

All configuration commands for the items systen can be found under the `/items-config` command. To take a look at your current items system configuration, you can use `/items-config info`:

<figure markdown>
  ![An example of an items system configuration.](items_config.png)
</figure>

As you can see, the only option available right now is:
- `/items-config toggle` turns on or off the items system. Players cannot use any of the items commands (as discussed on the [items usage page](items.md)) if the items system is turned off.

## Items

### Creating Items

To create items, you can use the `/items-manage create-item` command. This will pop out a little button that can be used _at any time to create items._

<figure markdown>
  ![An example of the button for creating items.](create_item_button.png)
</figure>

???+ tip "Hate Using the Button?"
    If you don't like using the button and would prefer if the command directly opened the prompt below, you can specify the `send_button` option for `/items-manage create-item` to say "no" instead of the (default) "yes". This will send the prompt directly to you, bypassing the button.

    Do give the button a try, though - you might find it more convenient when you're creating a lot of items!

Once you click that button, a little prompt will appear to fill out the details of the item you want to create:

<figure markdown>
  ![An example of the prompt to create an item.](create_item_modal.png)
</figure>

You get a number of customization options here:
- The name and description are, well, exactly what you expect. Names must be unique across different items. Both of these fields are required.
- The image is optional, but if you provide a URL to an image, it'll be displayed when a player views the item in a channel or in their inventory (as a thumbnail in an embed). This can be useful for showing off what the item looks like.
- The takeable option allows you to specify whether or not the item can be taken by players. If an item is not takeable, players will not be able to take it from a channel.

???+ note "Why make an item not takeable?"
    There are a few reasons you might want to make an item not takeable:
    - The item is immovable.
    - The item is a part of the scenery and not meant to be taken.
    - The item is a part of a puzzle or investigation and should not be taken.

    Players/users will still be able to see the item in the channel though, which may be useful.

Once you fill out the prompt, you should get a message about how the item was created successfully!

### Listing Items

To see what items you've created so far, you can use `/items-manage list-items`. This will give you a list of all items in the items system and a shortened view of their description.

<figure markdown>
  ![An example of /items-manage list-items.](list_items.png)
</figure>

### Viewing Items

If you want to see more information about a single item, you can use `/items-manage view-item` and specify the name of the item you want to see. This will give you a more detailed view of the item.

By default, the command will give you the item's name, description, image (if it has one), and takeable status.

<figure markdown>
  ![An example of /items-manage view-item.](manage_view_item.png)
</figure>

If you specify `view_possessors`, however, you'll also be able to see which channels or players currently possess the item.

<figure markdown>
  ![An example of /items-manage view-item with view_possessors.](view_item_possessors.png)
</figure>

### Editing Items

Editing an item is as simple as using `/items-manage edit-item` and specifying the item's name. A little prompt will appear:

<figure markdown>
  ![An example of the prompt to edit an item.](edit_item.png)
</figure>

As you can see, it already has the old fields populated in it - you'll be able to edit any property you want (including the name!). When you press submit, the item will be edited with the new properties.

### Delete Items

To delete an item, it's as simple as using `/items-manage delete-item` with the name of the item you want to delete. Notably, this removes it from all possessors' (channels and users) item lists, so be careful!

### Clear All Items

If you want to clear all items from the items system, you'll need to run `/items-manage clear-everything`. The command is named as such as deleting all items inherently removes all items from all possessors, effectively clearing everything.

## Channels

### Place Item In Channel

To place an item in a channel, you can run `/items-manage place-item-in-channel` and specify the item you want to place and the channel you want to place it in (and optionally the amount, which defaults to 1).

<figure markdown>
  ![An example of /items-manage place-item-in-channel.](place_items_in_channel.png)
</figure>

### List Placed Items

To list *all* items placed in the server's channels, you can use `/items-manage list-placed-items`. This will give you a list of all items in all channels and their quantity.

<figure markdown>
  ![An example of /items-manage list-placed-items.](list_placed_items.png)
</figure>

### List Items In Channel

To see what items are in a *specific channel*, you can use `/items-manage list-items-in-channel` and specify the channel you want to see. This will give you a list of all items in the channel, a shortened version of their description, and their quantity.

<figure markdown>
  ![An example of /items-manage list-items-in-channel.](manage_list_items_in_channel.png)
</figure>

### Remove Item From Channel

To remove an item from a channel, you can use `/items-manage remove-item-from-channel` and specify the item you want to remove and the channel you want to remove it from.

<figure markdown>
  ![An example of /items-manage remove-item-from-channel.](remove_item_from_channel.png)
</figure>

### Clear All Items In Channel

If you want to clear all items from a channel, you can use `/items-manage clear-items-in-channel` and specify the channel you want to clear items from. This will remove all items from the channel.

## Player/User Inventories

### View Inventory

To see what items a player has in their inventory, you can use `/inventory-manage user-inventory` and specify the user you want to see the inventory of.

!!! warning
    Note that this is *not* using `/items-manage` anymore. In general, inventory management is done through `/inventory-manage` instead of `/items-manage`.

<figure markdown>
  ![An example of /items-manage user-inventory.](manage_view_inventory.png)
</figure>

### Put Item In Inventory

To put an item in a player's inventory, you can use `/inventory-manage put-in-inventory` and specify the user you want to give the item to, the item you want to give, and optionally the quantity you want to give (if not specified, it defaults to 1).

<figure markdown>
  ![An example of /items-manage put-in-inventory.](put_in_inventory.png)
</figure>

### Remove Item From Inventory

To remove an item from a player's inventory, you can use `/inventory-manage remove-from-inventory` and specify the user you want to remove the item from, the item you want to remove, and optionally the quantity you want to remove (if not specified, it defaults to *1*).

<figure markdown>
  ![An example of /items-manage remove-from-inventory.](remove_from_inventory.png)
</figure>

### Drop Item From Inventory

To *drop* an item from a player's inventory into a specified channel, you can use `/inventory-manage drop-from-inventory` and specify the user you want to drop the item from, the item you want to drop, the channel you wish to drop the item into, and optionally the quantity you want to drop (if not specified, it defaults to 1).

<figure markdown>
  ![An example of /items-manage drop-from-inventory.](drop_from_inventory.png)
</figure>

### Clear Inventory

To clear a player's inventory, you can use `/inventory-manage clear-inventory` and specify the user you want to clear the inventory of. This will remove all items from the player's inventory.
