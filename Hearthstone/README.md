## Context

[Hearthstone](http://eu.battle.net/hearthstone/en/) is a very popular collectible card game published by [Blizzard Entertainment](http://blizzard.com) in 2014. The goal of the game consists in building a 30 cards deck in order to beat your opponent. A few weeks ago, I decided to download all the decks posted by players at [Hearthpwn](http://www.hearthpwn.com/). The code to download the data is available [here](https://github.com/rmnvncnt/pystone/tree/master).

## Content

This upload is composed of two files :

### `data.json` / `data.csv`
Contains the actual Hearthstone deck records. Each record features :

 * **date (str)** : the date of publication (or last update) of the deck.
 * **user (str)** : the user who uploaded the deck.
 * **deck_class (str)** : one of the nine character class in Hearthstone (`Druid`, `Priest`, ...).
 * **deck_archetype (str)** : the theme of deck labelled by the user (`Aggro Druid`, `Dragon Priest`, ...).
 * **deck_format (str)** : the game format of the deck on the day data was recorded (`W` for "Wild" or `S` for "Standard").
 * **deck_set (str)** : the latest expansion published prior the deck publication (`Naxxramas`, `TGT Launch`, ...).
 * **deck_id (int)** : the ID of the deck.
 * **deck_type (str)** : the type of the deck labelled by the user :
    - *Ranked Deck* : a deck played on ladder.
    - *Theorycraft* : a deck built with unreleased cards to get a gist of the future metagame.
    - *PvE Adventure* : a deck built to beat the bosses in adventure mode.
    - *Arena* : a deck built in arena mode.
    - *Tavern Brawl* : a deck built for the weekly tavern brawl mode.
    - *Tournament* : a deck brought at tournament by a pro-player.
    - *None* : the game type was not mentioned.
    
 * **rating (int)** : the number of upvotes received by that deck.
 * **title (str)** : the name of the deck.
 * **craft_cost (int)** : the amount of dust (in-game craft material) required to craft the deck.
 * **cards (list)** : a list of 30 card ids. Each ID can be mapped to the card description using the reference file.

### `refs.json` 
Contains the reference to the cards played in Hearthstone. This file was originally proposed on [HearthstoneJSON](https://hearthstonejson.com/). Each record features a lot of informations about the cards, I'll list the most important :

* **dbfId (int)** : the id of the card (the one used in `data.json`).
* **rarity (str)** : the rarity of the card (`EPIC`, `RARE`, ...).
* **cardClass (str)** : the character class (`WARLOCK`, `PRIEST`, ...).
* **artist (str)** : the artist behind the card's art.
* **collectible (bool)** : whether or not the card can be collected.
* **cost (int)** : the card play cost.
* **health (int)** : the card health (if it's a minion).
* **attack (int)** : the card attack (if it's a minion).
* **name (str)** : the card name.
* **flavor (str)** : the card's flavor text.
* **set (str)** : the set / expansion which featured this card.
* **text (int)** : the card's text.
* **type (str)** : the card's type (`MINION`, `SPELL`, ...).
* **race (str)** : the card's race (if it's a minion).
* **set (str)** : the set / expansion which featured this card.
* ...

If you need help cleaning the data take a look at my [start over kernel](https://www.kaggle.com/romainvincent/exploration-classification/)!

## What you could do :

* Try to predict the deck archetype based on the cards features in the deck.
* Seek relationships between the cost of the deck and it's popularity.
* Describe the evolution of the meta-game over-time.
* Find out unbalanced (overplayed) cards
