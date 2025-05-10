---
date: 2025-05-10
authors:
  - astrea
categories:
  - Updates

description: An update post for early May 2025.
comments: true
---

# Update Post - Early May 2025

It's been a while since the last update post, but this doesn't mean there haven't been updates! Over the past 6 months, small updates have dropped, but they have not been noted until this very post except for on the [support server](https://discord.gg/NSdetwGjpK). As such, some of these updates may be months-old.

Still, let's get into it!

<!-- more -->

## Gacha System Updates

- You can now import and export gacha items between servers! You can check out how to do that [in this part of the gacha setup guide](gacha_setup.md#exportingimporting-items).
- `/gacha inventory` now exists as an alias for `/gacha profile`.
- `/gacha roll/pull/draw` now takes into account the specific alias you are using for error messages.
- `/gacha-manage delete-item` now exists, serving as an alias for `/gacha-manage remove-item`.
- `/gacha give-currency` now works correctly for people who haven't gotten currency or a gacha item before.
- `/gacha-manage add-currency-players` should be *much* more reliable.

## BDA Investigation System Updates

- Truth Bullets can now have images! Just create or edit a Truth Bullet and you'll be able to put a URL. Unlike in other systems, they will be displayed at full size.
- For `/bullet-manage manual-trigger`:
  - You can now specify a finder to set who will be noted as finding a Truth Bullet.
  - The command now works even when Truth Bullet discovery is turned off (aka when Truth Bullets are not "active"). This should allow some flexibility to those that would like manual control over how Truth Bullets should be discovered.

## Items System Updates

- You can now disable auto-suggestions for players when investigating items with the items system with `/items-config auto-suggestions`! Basically, when a user uses `/investigate here/take` (or `/items here/take`), you can make it so those commands don't suggest a list of items in the current channel.
- The `hidden` attribute for `/items here` and `/items take` (and their respective `/investigate here` and `/investigate take` aliases) now properly functions.
- `/items view-inventory` (and its alias `/inventory view`) is now ephemeral.