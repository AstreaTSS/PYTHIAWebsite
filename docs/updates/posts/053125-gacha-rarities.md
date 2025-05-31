---
date: 2025-05-31
authors:
  - astrea
categories:
  - Feature

description: Gacha rarities have been added to PYTHIA, allowing for more complex gacha systems.
comments: true
---

# Gacha Rarities

PYTHIA now supports gacha rarities! This allows for more complex gacha systems, where items can have different rarities and thus different chances of being drawn.

<!-- more -->

## Description

Gacha rarities are a way to categorize items in the gacha system based on their rarity. This categorization affects how likely an item is to be drawn when a user rolls/draws/pull in the gacha system. For example, a "common" item might have a higher chance of being drawn than a "legendary" item.

<figure markdown>
  ![An example of /gacha pull pulling a common item.](gacha_draw.png)
</figure>

By default, the rarities are:
- Common (60%)
- Uncommon (25%)
- Rare (10%)
- Epic (4%)
- Legendary (1%)

However, these can be customized by the server staff to fit their needs, as discussed in a later section.

## Current Items

As of right now, current items in the gacha system have a rarity of "common" by default. Because *all* items will be common, all items will have an equal chance of being drawn. This replicates the previous behavior of the gacha system, where all items had an equal chance of being drawn.

Note that if all items in the gacha system are set to the same rarity, the bot is programmed to not display the rarity when rolling/drawing/pulling an item or when viewing the item with `/gacha view-item`. Once again, this is to replicate the previous behavior of the gacha system... although the color of the rarity will still be displayed, making the embed gray instead of PYTHIA's purple. To change this, you can set the color of the common rarity to PYTHIA's purple (#c156e0) in the gacha settings (how to do so is discussed below).

## Setting Up Rarities For Items

To edit the rarity of an item, you can use `/gacha-manage edit-item` as per usual:

<figure markdown>
  ![An example of the prompt to edit an item.](edit_gacha_item_modal.png)
</figure>

A new rarity field has been added, and it can be set to one of the following: common, uncommon, rare, epic, or legendary. Note that even if you change the names of the rarities, these names will still be used in the item rarity field.

Adding a new item will also prompt you to set the rarity of the item, so you can set it when you add the item to the gacha system.

## Rarity Configuration

By default, rarities can be used right away, but you can customize them to fit your needs. To do so, you can use `/gacha-config rarities` to edit rarity colors and their odds, while `/gacha-config names` can be used to edit the names of the rarities.

More information on how to do this can be found in the [rarities section](gacha_setup.md#rarities) of the gacha setup guide.