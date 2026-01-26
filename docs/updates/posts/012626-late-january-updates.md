---
date: 2026-01-26
authors:
  - astrea
categories:
  - Updates

description: An update post for late January 2026.
comments: true
---

# Update Post - Late January 2026

Wow, it's been a long while, hasn't it? This isn't because development has stopped - in fact, quite the opposite; this is probably the most active development PYTHIA has seen! However, updates have been smaller and more incremental, so they haven't warranted their own update posts. Still, it's worth noting some of the changes that have happened over the past 6 months!

<!-- more -->

## Gacha Changes

There are a *lot* of changes to the gacha system, so let's break them down:

### Adjustments to `/gacha profile` and `/gacha-manage list-items` 

!!! note
    `/gacha inventory` is an alias for `/gacha profile`, and so changes to one apply to the other as well.

**Both of these commands have a visual revamp!** You can choose which display mode to display items with the `mode` option.

??? note "Using An Old Discord Mobile Version?"
    Users using old Discord mobile versions (older than December 2024) will not be able to use either of the modes with "Modern" in it. This is a technical limitation, as these new modes use new Discord features. Please manually select `Cozy` or `Compact` for `mode` when you use this command instead.

=== "Modern (Default)"

    <figure markdown>
      ![An example of /gacha profile in modern mode.](gacha_profile.png){ width="400" }
    </figure>

=== "Spacious (Modern)"

    ???+ note
        Spacious mode exchanges the number of items that can be displayed on a single page for an extra "View" button that acts as a convenient way to view item details.

    <figure markdown>
      ![An example of /gacha profile in spacious mode.](gacha_profile_spacious.png){ width="400" }
    </figure>

=== "Cozy"

    <figure markdown>
      ![An example of /gacha profile in cozy mode.](gacha_profile_cozy.png){ width="400" }
    </figure>

=== "Compact"

    <figure markdown>
      ![An example of /gacha profile in compact mode.](gacha_profile_compact.png){ width="400" }
    </figure>

Also, **both commands now support sorting by item attributes!** You can use `sort_by` to sort by attributes such as `name`, `rarity`, `times_gotten`, and more. Here are examples of `/gacha profile` with different sorting options:

=== "Name (Default)"

    <figure markdown>
      ![An example of /gacha profile when sorting by name.](gacha_profile.png){ width="400" }
    </figure>

=== "Rarity"

    !!! note
        When sorting by rarity, items will be sorted in ascending order of rarity (common -> legendary). Within the same rarity, items will be sorted by name.

    <figure markdown>
      ![An example of /gacha profile when sorting by rarity.](gacha_profile_rarity.png){ width="400" }
    </figure>

=== "Time First Gotten"

    <figure markdown>
      ![An example of /gacha profile when sorting by the time the item was first gotten.](gacha_profile_time_first_gotten.png){ width="400" }
    </figure>

### "Roll Again" Button

When using `/gacha roll/pull/draw`, there is now a "Roll/Pull/Draw Again" button that allows you to quickly perform another roll without needing to retype the command! Feel free to spam it as much as you want as long as you have the money (within reason, of course).

## Dice System Changes

The dice system has seen a few changes as well:

### Dice Can Be Used In DMs and Non-Server Contexts

Really like the [dice system in PYTHIA](dice.md)? Want to use it in servers where PYTHIA isn't in, or in DMs? Well, now you can!

Simply use [this link](https://discord.com/oauth2/authorize?client_id=843994199187914753) (or `/invite`, or the "Add Bot" option) to add the bot to yourself. Afterwards, you should be able to see the `/dice` commands anywhere.

### Importing/Exporting Registered Dice

You can now export your registered die to a JSON file using `/dice export`, and import them back using `/dice import-ristered`. This is useful for backing up your registered die or transferring them between servers or contexts. See [the documentation](dice.md#exportingimporting-registered-die) for more information.

## Items System Changes

There's only one notable change to the items system: `/items-manage list-items`, `/items-manage list-items-in-channel`, `/inventory-manage user-inventory`, and `/items view-inventory` (and any aliases) have a slight visual revamp. For example, `/items view-inventory` now looks like this when using `mode`:

=== "Cozy (Default)"

    <figure markdown>
      ![An example of /items view-inventory in cozy mode.](view_inventory.png)
    </figure>

=== "Compact"

    <figure markdown>
      ![An example of /items view-inventory in compact mode.](view_inventory_compact.png)
    </figure>

## Beta Testing Opportunities

A new command has been introduced to `/config` called `/config beta`. Enabling this will allow you to access beta features that are still in testing. These features may be unstable or incomplete, so use them at your own risk!

Right now, though, they grant access to (visual) improvements like this:

???+ warning "For Users Using Old Discord Mobile Versions"
    Users using old Discord mobile versions (as in, any version other than the latest one) have been supported as best as possible. However, these beta features use new Discord features that old mobile versions do not support, and so these users may experience broken or unusable interfaces. It is recommended to disable beta features if you are using an old Discord mobile version.

    Eventually, though, these beta features will become the default, and old mobile versions will no longer be supported.

=== "Gacha Roll"

    <figure markdown>
      ![An example of the beta gacha roll interface.](gacha_roll_jan2626.png)
    </figure>

=== "Add Gacha Item"

    <figure markdown>
      ![An example of the beta "add gacha item" interface.](add_truth_bullet_jan2626.png)
    </figure>

=== "Add Truth Bullet"

    <figure markdown>
      ![An example of the beta "add truth bullet" interface.](add_gacha_item_jan2626.png)
    </figure>