# Items

The items system allows you to find items in channels and potentially take them into your inventory. Here's how to use it!

!!! note
    All user/player-facing item system commands are stored in `/items`, although there are aliases.

## Finding Items

To find items in a channel, you can use `/items here` while in a channel. The autocomplete will give you a list of items in the channel, and filling out the command with an item's name will allow you to see more information about it.

???+ note "Alias"
    As an alias, you can use `/investigate here`.

???+ note "Hidden Option"
    For `/items here` and the upcoming `/items take`, you can use the `hidden` option to make it so the response is only visible to you. This is useful if you want to keep the item a secret from other players.

<figure markdown>
  ![An example of /items here.](items_here.png)
</figure>

## Taking Items

If an item is available to take (double check the footer of `/items here`), you can use `/items take` and specify the item's name (and optionally the amount, which defaults to 1). This will add the item to your inventory.

???+ note "Alias"
    As an alias, you can use `/investigate take`.

<figure markdown>
  ![An example of /items take.](items_take.png)
</figure>

## Viewing Inventory

To see what items you have in your inventory, you can use `/items view-inventory`. This will give you a list of all the items you have, along with their descriptions.

???+ note "Alias"
    As an alias, you can use `/inventory view`.

This command has a `mode` option to adjust how the inventory is displayed:

=== "Cozy (Default)"

    <figure markdown>
      ![An example of /items view-inventory in cozy mode.](view_inventory.png)
    </figure>

=== "Compact"

    <figure markdown>
      ![An example of /items view-inventory in compact mode.](view_inventory_compact.png)
    </figure>

## Viewing Item In Inventory

If you want to see more information about a single item in your inventory, you can use `/items view-item` and specify the name of the item you want to see. This will give you a more detailed view of the item, including its description.

???+ note "Alias"
    As an alias, you can use `/inventory view-item`.

<figure markdown>
  ![An example of /items view-item.](view_item.png)
</figure>

## Dropping Items

If you want to drop an item from your inventory, you can use `/items drop` and specify the name of the item you want to drop. This will remove the item from your inventory.

???+ note "Alias"
    As an alias, you can use `/inventory drop`.

<figure markdown>
  ![An example of /items drop.](items_drop.png)
</figure>