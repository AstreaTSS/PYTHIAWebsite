---
date: 2026-05-28
authors:
  - astrea
categories:
  - Updates

description: An update post detailing the May 2026 visual revamp of the bot.
comments: true
---

# Visual Revamp (May 2026)

Hello! You may have already noticed it, but: *almost every single command in the bot has had a visual revamp!* This has been something building up since the January update announced the beta visual improvements, but this goes one step further than that. Take a look!

<!-- more -->

## Images 

!!! Note
    This is a small selection of the changes that were made - there are many more that you can find by using the bot and exploring the documentation!

---

<div class="grid cards" markdown>

-   **Before**

    <figure markdown>
      ![An example of the old /gacha draw.](https://raw.githubusercontent.com/AstreaTSS/PYTHIAWebsite/71f9c16be421c51ffce31db186668e62b8c39522/docs/assets/gacha/gacha_draw.png)
    </figure>
    

-   **After**

    <figure markdown>
      ![An example of the new /gacha draw.](gacha_draw.png)
    </figure>

</div>

---

<div class="grid cards" markdown>

-   **Before**

    <figure markdown>
      ![The old trigger example for the BDA system.](https://raw.githubusercontent.com/AstreaTSS/PYTHIAWebsite/71f9c16be421c51ffce31db186668e62b8c39522/docs/assets/investigations/trigger_example.png)
    </figure>
    

-   **After**

    <figure markdown>
      ![The new trigger example.](trigger_example.png)
    </figure>

</div>

---

<div class="grid cards" markdown>

-   **Before**

    <figure markdown>
      ![The old create item popup for the items system.](https://raw.githubusercontent.com/AstreaTSS/PYTHIAWebsite/71f9c16be421c51ffce31db186668e62b8c39522/docs/assets/items/create_item_modal.png)
    </figure>
    

-   **After**

    <figure markdown>
      ![The new create item popup for the items system.](create_item_modal.png)
    </figure>

</div>

---

<div class="grid cards" markdown>

-   **Before**

    <figure markdown>
      ![An example of a message before the revamp.](https://raw.githubusercontent.com/AstreaTSS/PYTHIAWebsite/71f9c16be421c51ffce31db186668e62b8c39522/docs/assets/messaging/message_to_user.png)
    </figure>
    

-   **After**

    <figure markdown>
      ![An example of a message after the revamp.](message_to_user.png)
    </figure>

</div>

---

<div class="grid cards" markdown>

-   **Before**

    <figure markdown>
      ![An example of listing dice before the revamp.](https://raw.githubusercontent.com/AstreaTSS/PYTHIAWebsite/71f9c16be421c51ffce31db186668e62b8c39522/docs/assets/dice/dice_list.png)
    </figure>
    

-   **After**

    <figure markdown>
      ![An example of listing dice after the revamp.](dice_list.png)
    </figure>

</div>

---

## Other Changes

...confession: this isn't just a visual revamp. This is actually **a complete rewrite of PYTHIA's codebase.** Most of the rewrite was just done to make the codebase more maintainable and easier to work with, with the visual revamp being a nice side effect of that.

!!! Warning
    Because of this, there may be some bugs that were not present before. If you find any, please report them in the [support server](https://discord.gg/NSdetwGjpK)!

However, there are some changes that were made that aren't just visual, so here are some of those:

- `/gacha-manage add-currency-role` now exists! It allows you to add currency in bulk to anyone with a specified role.
  - `/gacha-manage add-currency-players` is now just an alias of `/gacha-manage add-currency-role` but with the Player role specified for the role.
- If you have `/gacha-config draw-duplicates` enabled (the default), then duplicates are now less often to appear when pulling from the gacha.
- For `/gacha inventory` and `/gacha-manage list-items` (and their aliases/derivatives), `Cozy` was merged into `Modern`.
- If you somehow knew of the undocumented prefixed/text commands variants of `/gacha-manage add/remove-currency`, they have been removed.
- `/help` has been neutered, and now just sends you to this website. The old command was simply too much to maintain for how little it was used.
- *Support for old Discord mobile versions has been dropped.* Warnings were already given months ago, so this shouldn't come as a surprise.