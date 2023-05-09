---
layout: page
title: Spaced Repetition
permalink: /spaced_repetition/
---
### Overview
Memorization is a big part of my life. Every day, I spend ~5–15 minutes reviewing flashcards in an app called [Anki](https://apps.ankiweb.net), which is a popular implementation of a technique called **spaced repetition**. Plenty has been written about spaced repetition, so this page is intended as a pratical guide rather than a detailed explanation.

In spaced repetition, you don't just look through your whole deck of flashcards: instead, each of your cards has its own due date, and **you only review the cards that are due today**. Every time you get a card right, the time before its next due date gets longer, so you don't waste your time reviewing facts you already know well.

This makes it possible to have a very large library of flashcards without spending an overwhelming amount of time reviewing them. As of mid-2023, I have a personal library of ~4500 flashcards, but each day I only review ~75.

Here are some examples of things I use Anki to remember:

- Facts I could look up but want to have on the tip of my tongue:
    - Phone numbers and birthdays of friends and family
    - Unit conversions. How many grams in a pound?
    - Math identities. log(xy) = log(x) + log(y)
    - What's the difference between serum and plasma?
- Personal facts, harder to look up:
    - Who was the person who first taught me how to do proteomics?
    - What's the name of that great tiny variety of mandarins that are hard to find?
- Concepts I've had to work to understand:
    - Why don't your T cells kill other cells in your body?
    - What's the difference between git merge and git rebase?

It took a while to get used to writing flashcards for more complicated concepts, but it has helped me feel more confident putting in effort to learn new things. I have less fear that I'll just forget them again.

Here are some sources for more information about spaced repetition:
- [The Wikipedia page](https://en.wikipedia.org/wiki/Spaced_repetition)
- [Gwern's deep dive](https://gwern.net/spaced-repetition)
- [Michael Nielsen's "Augmenting Long-term Memory"](http://augmentingcognition.com/ltm), which put me onto spaced repetition in the first place
- Some popular alternatives to Anki: [Supermemo](https://supermemo.com) and [Mnemosyne](https://mnemosyne-proj.org).

### How to use Anki
1. Make yourself an account on the [Anki website](https://apps.ankiweb.net) and download the desktop Anki app for your computer.
2. If you want, get the Anki app for your [Android](https://play.google.com/store/apps/details?id=com.ichi2.anki) or [Apple](https://apps.apple.com/us/app/ankimobile-flashcards/id373493387) phone. There are other apps available with “Anki” in their names, but as far as I know these are the only real ones that sync with your Anki account. The Android app is free, but the Apple app costs money, so no pressure to install until you decide you really want to make this a habit.
3. Start making flashcards for things you want to remember! More on this [below](#making-cards).
4. Review your flashcards. I recommend doing this every day. If you can keep up with your reviews, the number of reviews due per day stays very manageable, but it’s possible to get into an unpleasant cycle of getting behind and then having a frustrating time catching up.

#### Reviewing flashcards
Here is what it looks like when you select a deck in Anki and hit `Study Now`:
- The front side of a card will appear, along with some numbers about how many cards are due to review and a `Show Answer` button:

![Front of Anki card](../assets/anki_front.png){: width="70%" }

- Once you hit `Show Answer` (or spacebar or Enter on the computer), you’ll get options for how hard the card was for you, which will affect how long it will be before you see the card again. There’s no test—you just have to be honest.

![Back of Anki card](../assets/anki_back.png){: width="70%" }

The options are `Again`, `Hard`, `Good`, and `Easy`, but I practically only use `Again` and `Good`. `Again` means that you didn’t know the answer and the card should reset its review interval. `Good` means that you knew the answer and the review interval should get longer. On the computer, these have shortcuts 1–4, and `Good` is the default option, so spacebar or Enter also select `Good`. When I’m reviewing on the computer I’m just hitting Enter for `Good` over and over as I go through cards I know, and when I don’t know one I hit the 1 key for `Again`.


#### Making cards
Anki makes it possible to organize your cards into decks, but **I actually barely use different decks**—I have some decks, but they’re all subdecks of one big main deck that I review every day.

You might want to put your cards in different decks if you know you might want to turn off a bunch of cards in the future, e.g. if you want to remember the names of people who you will only interact with this year, or if you want to try learning a whole new topic but aren’t certain you’ll want to keep it up.

I like to make new cards on the computer rather than the phone because it’s easier to type. Anki has powerful tools for making cards, but you can get 95% of the utility with just the two simplest tools that come preinstalled: **“Basic” and “Cloze”**.

- The Basic note type is just like a physical flashcard: you type in what should be on the “front” and “back”, and then when you review the card later you’ll be shown the front and have to remember what the back says.
- The Cloze note type is for filling in the blank. Rather than having to type e.g. `Grandma’s phone number is _____` on the front and `Grandma’s phone number is 555-555-5555` on the back, you can just type `Grandma’s phone number is 555-555-5555`, select the phone number and hit the “cloze deletion” button in the little menu above the text box (or Cmd-shift-C on a Mac). This adds special text to the card (which you can also just type in if you prefer), so the resulting text will be {% raw %}`Grandma’s phone number is {{c1::555-555-5555}}`{% endraw %}, which will show you a blank when you review the card later.
If you want, you can put in multiple deletions—you could do e.g. {% raw %}`{{c2::Grandma’s}} phone number is {{c1::555-555-5555}}`{% endraw %}, so you’ll also be shown `________ phone number is 555-555-5555` and have to remember who the phone number belongs to.


#### Advanced features
I will quote [Michael Nielsen](https://augmentingcognition.com/ltm) directly here:
>I know many people who try Anki out, and then go down a rabbit hole learning as many features as possible so they can use it “efficiently”. Usually, they're chasing 1% improvements. Often, those people ultimately give up Anki as “too difficult”, which is often a synonym for “I got nervous I wasn't using it perfectly”. This is a pity. As discussed earlier, Anki offers something like a 20-fold improvement over (say) ordinary flashcards. And so they're giving up a 2,000% improvement because they were worried they were missing a few final 5%, 1% and (in many cases) 0.1% improvements. This kind of rabbit hole seems to be especially attractive to programmers.

If you're sure you want to go down the rabbit hole, you can start **messing around with note types**. You may have noticed that I referred to Basic and Cloze as “tools for making cards” or “note types” rather than just flashcards. This is because Anki actually has you enter the information you want to remember in the form of a “note” (what a database person would call a "record") and then uses rules to generate the flashcards that you actually review.

More complex note types can be useful when you have multiple pieces of information about the same thing. For instance, I have a “Person” note type in which I can enter someone's name, phone number, birthday and address (or leave some of them blank), and then the appropriate flashcards (“What is Jack’s address?”; “Whose birthday is on January 1?”) will be created automatically.

![Person note fields](../assets/anki_person_fields.png){: width="70%" }

To help you get started with note types, [here is an Anki deck](../assets/note_type_example.apkg) containing a couple of examples: the Person note type shown above and the Molecule note type that I use for  chemical structures.

If you are struggling with Anki's advanced features, get in touch and I am happy to help you get up the learning curve!