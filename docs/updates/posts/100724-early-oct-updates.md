---
date: 2024-10-07
authors:
  - astrea
categories:
  - Updates

description: An update post for early October 2024.
comments: true
---

# Update Post - Early October 2024

Since the last post discussing the dice system, there has been quite the number of minors change, and one upcoming rename. Let's get into it!

<!-- more -->

## Rename of `/investigate`

Starting with important news first: `/investigate` will be renamed to `/bda-investigate` around Saturday, October 12th, 2024, at 12:00 AM UTC. This is to make way for new features that will be coming soon. The command will still work as before, but you may want to inform people of this change.

You may have already gotten a message from the bot about this - those messages will not be repeated, but do keep it in mind.

## Aliases for `/gacha roll`

The specific action of *using a gacha* to get items has quite a lot of names to it, such as "rolling", "pulling", or the more boring "drawing". In the past, this bot referred to it exclusively as "rolling", and while that's the case for the documentation, the command itself now has a few aliases.

`/gacha roll` now has aliases under `/gacha draw` and `/gacha pull` - these are all the same command, so you can use any of them to get items from the gacha system.

## Clear Commands for the Dice System

Removing all of the registered dice rolls for a user (or yourself) can be a bit of a hassle, especially if you have a lot of them. To make this easier, a couple of new commands have been added:
- `/dice clear` will clear all of *your* dice rolls for the server you run it in.
- `/dice-manage clear-for` will clear all of the dice rolls for a specific user.
- `/dice-manage clear-everyone` will clear all of the dice rolls for *every* user in the server.
