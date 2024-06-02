---
date: 2024-06-02
authors:
  - astrea
categories:
  - Updates

description: An update post for early June 2024.
comments: true
---

# Update Post - Early June 2024

Hello! For the first time in a while, the bot's receiving some new features, so I thought I'd make a post about them (and make a whole blog-like system while I'm at it).

These features include a new "hidden" setting for Truth Bullets, a new way of investigating Truth Bullets, and a potential rebanding. Let's get into it!

<!-- more -->

## Hidden Truth Bullets

Staff now have the ability to mark Truth Bullets as "hidden." This means that only the person who triggers the Truth Bullet will see it (through DMs or a response only visible to them), and it won't be posted in the Truth Bullets channel. This is useful for secrets that only one person should know.

To do so, just add/edit a Truth Bullet and make the new second option a "yes":

<figure markdown>
  ![The pop-up that appears while adding Truth Bullets.](add_bullet_modal.png){ loading="lazy" }
</figure>

!!! warning "Hidden Truth Bullets Usage"
    If you're planning on using hidden Truth Bullets, it's a good idea to warn your players ahead of time that they should have DMs enabled with the server and/or the bot. This is because the bot will need to DM the user if they trigger a hidden Truth Bullet through messages.

## Alternate Investigation Method

As a solution matching a certain other bot, you can now use `/investigate` with the *exact trigger* (case insensitive) to trigger a Truth Bullet. For example, if you have a trigger called "ink", someone can use `/investigate ink` to trigger the same Truth Bullet as if they had sent a message with the trigger in it. Hidden Truth Bullets are even treated slightly different - instead of the bot DMing the triggerer, it'll send a response only visible to them.

If you feel inclined to make this the *only* available method, you can! A new configuration option, `/config investigation-mode`, allows you to make it so that only `/investigate` works for discovering Truth Bullets.

## Potential Rebranding

If you haven't heard, [Ultimate Assistant](https://github.com/Firefly042/ultimate-assistant-pycord), the biggest Danganronpa RP bot and the bot that heavily inspired this one, will be discontinued on July 5th, 2024, as discussed on [its support server](https://discord.com/invite/VZYKBptWFJ). While that doesn't mean the bot will be *shut down*, per se (it likely won't be able to be added to new servers), it's pretty evident to me that the bot will leave a large void in the space.

Ultimate Investigator was limited in scope in part because Ultimate Assistant existed, but with its discontinuation, I'm considering expanding the bot's scope to include more features that Ultimate Assistant had, like its gacha system. This would likely come with a rebranding to reflect the new features and the new direction the bot would take.

I would really love feedback on this move, so I highly suggest either using the comment section below or joining [my support server](https://discord.gg/NSdetwGjpK) to give your thoughts. I'm excited to see what you all think!

*Note: if the rebrand were to go through, I'd likely name it either PYTHIA or Ultimate Helper. PYTHIA is the name of an OC of mine who's the Ultimate Robotic Assistant, and Ultimate Helper is a (generic) name that reflects the bot's new direction.*