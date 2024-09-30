---
description: The privacy policy for PYTHIA.
---

# Privacy Policy

*Last updated: 2024-09-30 (YYYY-MM-DD).*

This document contains the privacy policy and agreement you accept when adding PYTHIA (PYTHIA#3565, ID 843994199187914753) to a server, or use the bot as a member of a server. This document does not supersede any of the terms laid out by Discord.

## Data Collection

Data is collected for differing reasons in different scenarios. Each scenario covered by this Policy will be explained below.

#### Collected by Command/Features

Certain data is collected whenever a user or staff uses a command/feature. This includes:
- Server specific configuration settings, as set by the server staff. This corresponds to the various `/X-config` commands, with `X` being the feature.
- Information about Truth Bullets as seen through the various commands, including the content of the Truth Bullet, the channel it is meant to be sent in, the keyword/phrase that triggers it, and the triggering user. This is set through `/bullet-manage` and when Truth Bullets are active.
- Information about Gacha items, including the contents of each item and who owns the item. This is set both through `/gacha-manage` and when a user pulls an item through `/gacha roll/draw/pull`.
- Information of a user's Gacha profile, including their currency amount and the items they own. This is set both through `/gacha-manage` and when a user pulls an item through `/gacha roll/draw/pull`.
- Information of a user and their respective messaging channel, including the user's ID and the channel ID. This is set through `/message-manage`.
- Information about a user's registered die, including the die's name, the user's ID, and the die's value. This is set through `/dice-manage` and `/dice`.
- Information about the various names/renamings that the staff set for certain features - mainly, those set through `/X-config names`, with `X` being the feature.

A technical specification of data collected by each command/feature can be found in the [schema file used by the bot](https://raw.githubusercontent.com/AstreaTSS/PYTHIA/refs/heads/main/schema.prisma).

#### Automatically Collected

Some data is automatically collected by the bot. This includes:
- Any data needed for the standard operation of the bot. This typically includes channel data and roles.
  - Notably, this includes messages, message content, and members. However, this is only in the context of the bot's operation - this data is quickly processed and is not permanently stored.
  - Most data of this type will be stored in the bot's cache, which is cleared when the bot is restarted. Before then, some data may get cleared out to make room for new data.
- Data resulting from unhandled errors, such as the error message and the stack trace. This data does not contain any personal information and is used to help improve the bot.

## Why We Collect Data

Data is collected to ensure all of the bot's functions can run. Occasionally, data is collected to provide us with analytical data about the bot's usage and behavioral patterns, largely consisting of the bot's most used commands.

## Who We Share Data With

We do not share data with any 3rd party for any reason whatsoever, unless required by law.

## How Your Data is Stored

All data is stored on protected infrastructure operated by trusted SaaS/VPS solutions (IE Neon, Hetzner). While storage methods may vary, most data will be stored within enterprise-standard databases such as [PostgreSQL](https://www.postgresql.org/). Please keep in mind that even with the highest standard of protection, no data can ever be 100% secure. While we strive to keep data secure and private at all times, absolute security cannot be guaranteed.

## How Long Your Data is Retained

- Data collected through commands/features is retained for as long as the bot is in the server, or until it is cleared by the server staff.
- Data collected automatically is retained for as long as the bot is running, or until it is cleared to make room for new data.

## Your Rights to Your Data

Pursuant to various jurisdictions, you have the right to request a machine-readable copy of your data for portability's sake and the right to have your data deleted from the bot.

Should you wish to enforce one of these rights, please send an email to [discord@astrea.cc](mailto:discord@astrea.cc) - we will strive to respond to your request within 30 days.

## Children's Privacy

This bot does not address anyone under the age of 13. We do not knowingly collect personally identifiable information from anyone under the age of 13. If you are a parent or guardian and you are aware that your child has provided us with personal data, please contact us. If we become aware that we have collected personal data from anyone under the age of 13 without verification of parental consent, we will take steps to remove that information from our servers.

## Feedback

Feedback for the bot is appreciated! However, you agree that upon submission of feedback, you forego any rights to the content, title, or intent of the provided feedback. Additionally, the feedback you provide may be used in any way.

## Agreement

By utilizing any of the before mentioned Services, you are consenting to the policies outlined in this document.

If you, as a server staff, do not agree to the terms laid out in this document, you may remove PYTHIA from the server and stop using the bot.

If you, as a server member, do not agree to the terms laid out in this document, you may leave server that contain PYTHIA.