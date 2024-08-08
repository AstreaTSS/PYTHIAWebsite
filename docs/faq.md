---
description: Frequently asked questions about PYTHIA.
---

# Frequently Asked Questions

## General

### What is PYTHIA?

PYTHIA is a Discord bot meant to assist with various parts of running Danganronpa/Killing Game RPs, of course. The [home page](./index.md) has a bit more information on what it can do.

### How do I set up PYTHIA?

You can find a list of setup guides on the [setup page](./setup/index.md). The [basic setup guide](basic_setup.md) is a good place to start.

### A server I'm in is using PYTHIA. How do I use it?

You can find a list of usage guides on the [usage page](./usage/index.md).

### Is this meant to be a replacement for Ultimate Assistant?

Short answer: kind of.

This bot was initially created just for its [investigation system](investigations.md) under the name of Ultimate Investigator. Knowing that Ultimate Assistant existed, the bot didn't expand out to other features because there was no point in doing so. However, once I got the news that Ultimate Assistant was going to be deprecated, I decided to expand the bot to include features previously only found in Ultimate Assistant.

However, PYTHIA's new systems are *not* an exact copy of Ultimate Assistant's systems. While Ultimate Assistant's command names and arguments/options were sometimes referenced, the systems themselves were built from scratch. I didn't hestitate on making changes to the systems if I felt it was necessary.

Most notably, many of the systems do not rely on making an entire profile per player to function - instead, they rely on a player role (or nothing at all, in the case of the messaging system). This, in my opinion, makes the systems easier to use and set up.

### Will you implement the currently missing features/systems from Ultimate Asisstant?

Maybe. I tend not to like developing things that are already done (well) by other bots. However, if there's a feature that I think would be a good addition to the bot, I'll consider adding it.

For now, for alternatives to the missing features, you can check out:
- [Carl-bot's Autofeeds](https://docs.carl.gg/#/feeds?id=autofeeds) for the announcement system.
- [Chiaki Nanami](https://discord.com/application-directory/781034602533879838) for a general purpose investigation/inventory system. Notably, PYTHIA *can* be used as a general purpose system, but it's meant more for murder investigations.
- Any dice bot, including (but not limited to) [Avrae](https://avrae.io/), [Dice Maiden](https://discord.com/application-directory/572301609305112596), and [Rollem](https://rollem.rocks/), for the dice system. Notably, most of these bots do not allow you to set up dice rolls specific to your character - Avrae does.
- I do not know of any alternative for the profile system Ultimate Assistant had.

!!! note
    These are listed as-is, and I (AstreaTSS) take no responsibility for them. These recommendations are based on research and are not sponsors, nor are they necessarily endorsed. That being said, if you wish to talk to me about one of these bots or to add one, you can [join my support server](https://discord.gg/NSdetwGjpK) to do so.

Just because features are in the above list does not mean they will not be added to PYTHIA in the future.

### Where can I find information about updates/new features?

There are two places you can find updates - the [updates page](updates/index.md) and the [support server](https://discord.gg/NSdetwGjpK). The updates page always will contain new features and major adjustments, but the support server will also contain bug fixes and other miscellaneous announcements (IE downtime announcements) that you may find useful.

### I want to suggest a feature. Where can I suggest it?

In the [support server](https://discord.gg/NSdetwGjpK), of course!

### There's another problem not answered here. Where can I ask about it?

Also in the [support server](https://discord.gg/NSdetwGjpK), of course!

## Technical

### I wanted to add something to the website/I noticed a mistake on the website. Can I do something about it?

Of course! The website is open source, and you can find the repository [over here](https://github.com/AstreaTSS/PYTHIAWebsite). The website uses MkDocs Material and markdown, so you'll need to know a bit about that to make changes. If you're not comfortable with that, you can always ask in the [support server](https://discord.gg/NSdetwGjpK) and point me in the right direction.

### I want to add a feature to PYTHIA. Can I do that?

Yes! The bot is also open source, [as can be seen here](https://github.com/AstreaTSS/PYTHIA). The bot is written in Python and uses Prisma and Git, so I'd suggest knowing a bit about those (and Discord bot making) before you start. If you're not comfortable with that, you can always ask in the [support server](https://discord.gg/NSdetwGjpK) and point me in the right direction.

Self-hosting steps (for testing) can be found on the next question.

### Can I self-host PYTHIA?

You can! Using [the source code](https://github.com/AstreaTSS/PYTHIA), you can self-host the bot. 

!!! warning "Note about Self-Hosting"
    Self-hosting is not recommended for most users, being a complicated process that requires at least some technical knowledge. Only do this if you have a personal interest in self-hosting, or if you want to contribute to the bot's development.
    For most people, the public instance of the bot is more than enough - see the [Server Setup Guides](setup/index.md) for more information.

    If you run into issues, I will only give limited support on my [support server](https://discord.gg/NSdetwGjpK), and will expect you to have a reasonable understanding of Python, Discord, Git, and potentially Docker. I am not tech support.

#### Recommended Process (Docker)

That being said, the recommended process is:
1. Clone the repository.
2. Install [Docker Engine](https://docs.docker.com/engine/install/) and [Docker Compose](https://docs.docker.com/compose/install/).
3. Run `docker compose build` in the repository.
4. Make a `.env` file in the repository with the following contents:
    ```env
    MAIN_TOKEN="YOUR_BOT_TOKEN"
    BOT_COLOR=7487408
    DOCKER_MODE="true"
    POSTGRES_PASSWORD="A_STRONG_PASSWORD"
    ```
5. Set up the database by running `docker compose run --env DB_URL="postgresql://postgres:YOUR_POSTGRES_PASSWORD_FROM_THE_LAST_STEP@db:5432/postgres" bot python -m prisma migrate deploy`.
6. Use `docker compose up -d` to start the bot. You can use `docker compose logs -f` to view the logs of the bot.
  - To sync slash commands, run `@BOT_MENTION debug sync` in Discord (replace `BOT_MENTION` with the bot's mention, like `@PYTHIA`).'

#### Non-Docker Setup

If you don't want to use Docker, your steps will be a bit different. You'll need to:
1. Clone the repository.
2. Install Python 3.10+ (the latest Python is usually the best one to use). Ideally, [make a virtual environment for this project](https://realpython.com/python-virtual-environments-a-primer/).
3. Make a `.env` file in the repository with the following contents:
    ```env
    MAIN_TOKEN="YOUR_BOT_TOKEN"
    BOT_COLOR=7487408
    DB_URL="URL_TO_YOUR_POSTGRES_DATABASE"
    ```
4. Run `pip install -U -r requirements.txt` in the repository.
5. Set up Prisma by running `python -m prisma generate`.
6. Set up the database by running `python -m prisma migrate deploy`. This may complain if you already have tables - you can run `python -m prisma migrate dev` to wipe the database and start fresh.
7. Start the bot by running `python -m main.py`.
  - To sync slash commands, run `@BOT_MENTION debug sync` in Discord (replace `BOT_MENTION` with the bot's mention, like `@PYTHIA`).'

#### Updating

To update the bot, you can:
1. Run `git pull` in the repository.
2. To update dependencies, run: 
  - `docker compose build` for Docker setups.
  - `pip install -U -r requirements.txt` and `python -m prisma generate` for non-Docker setups.
3. If there are any database changes (visible as a new migration in `migrations`), you can run the following command to apply them:
   - `docker compose run --env DB_URL="postgresql://postgres:YOUR_POSTGRES_PASSWORD_FROM_YOUR_ENV@db:5432/postgres" bot python -m prisma migrate deploy` for Docker setups.
   - `python -m prisma migrate deploy` for non-Docker setups.