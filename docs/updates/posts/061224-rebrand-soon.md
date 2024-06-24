---
date: 2024-06-12
authors:
  - astrea
categories:
  - Rebrand

description: A rebrand is coming soon! Read on to learn about breaking changes and what to expect.
comments: true
---

# Rebrand Coming Soon!

Hello! As hinted at in the previous post, a rebrand will come soon! This means a new name and icon, an increased scope... and a bunch of renamings.

<!-- more -->

The bot will be renamed to **PYTHIA**, named so after my OC who's the Ultimate Robotic Assistant. The bot will also have a new icon, but that's in the works.

!!! warning
    To clarify, the rebrand isn't happening now, and none of the changes have happened *yet*. This is just to prepare you for what will come in a week or two.

## Breaking Changes

Many commands are getting moved over to make room for other features. Don't worry, the original investigation features will continue to be supported, but they'll just be put into this own section.

The changes are below:

- Managing Truth Bullets:
  - A new command, `/bullet-manage`, will hold all of the subcommands for managing Truth Bullets.
  - `/add-bullet` will become `/bullet-manage add`.
  - `/remove-bullet` will become `/bullet-manage remove`.
  - `/clear-bullets` will become `/bullet-manage clear`.
  - `/list-bullets` will become `/bullet-manage list`.
  - `/bullet-info` will become `/bullet-manage info`.
  - `/edit-bullet` will become `/bullet-manage edit`.
  - `/unfind-bullet` will become `/bullet-manage unfind`.
  - `/override-bullet` will become `/bullet-manage override`.
  - `/add-alias` will become `/bullet-manage add-alias`.
  - `/remove-alias` will become `/bullet-manage remove-alias`.
- Truth Bullet Configuration:
  - A new command, `/bullet-config`, will hold all of the subcommands for configuring Truth Bullets.
  - `/config info`'s functionality will be largely moved to `/bullet-config info`.
    - That being said, `/config info` will still exist, but only to list out *general* configuration. I'll talk about that in a bit.
  - `/config bullet-channel` will become `/bullet-config channel`.
  - `/config best-truth-bullet-finder` will become `/bullet-config best-finder`.
  - `/config investigation-mode` will become `/bullet-config mode`.
  - `/config toggle` will become `/bullet-config toggle`.
  - `/config names` (for anyone who used an unannounced feature) will become `/bullet-config names`.
- General Configuration:
  - `/config` will now only list out general configuration options.
  - `/config player` is thus the same, being a general configuration option.
  - `/config info` now shows general configuration settings... which is just the player role for now.
- Website:
  - The website will be moved to a new subdomain, pythia.astrea.cc. The current subdomain (ui.astrea.cc) will redirect to the new one.
  - The server setup guide will become the server setup guide*s*, with a home page and a page for each feature.
  - Same thing with the "how to use the bot" guide - it'll become a home page and a page for each feature worth explaining.

## What To Expect
- You may have noticed `/config names` being a thing. That's currently usable in Ultimate Investigator to edit the display name for Truth Bullets and the like, but it'll get a proper announcement alongside the rebrand.
- Gacha is coming along with the rebrand! It'll be a bit different from Ultimate Assistant's, but it'll be there.