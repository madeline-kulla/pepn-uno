# UNO

The time you spent looking at this readme could have been spent being productive.  
Readmes kill. Play UNO instead. UNO saves lives.

## Table of Contents

1. [Description](#description)
2. [Configurable Rules](#configurable-rules)
3. [Selfhosting](#selfhosting)
4. [Disclaimer](#disclaimer)

## Description

This is an UNO bot designed for the Discord chat platform. The intent of this bot is to provide a fun and fulfilling UNO experience with your friends!

### Commands

```
UNO HELP - Shows this message!
UNO SUPPORT - Gets a link to my support guild!
UNO JOIN - Joins (or creates) a game in the current channel!
UNO QUIT - Quits the game! Party pooper.
UNO START - Starts the game! Can only be used by the player who joined first.
UNO TABLE - Shows everyone at the table.
UNO PLAY <colour> <value> - Plays a card! Colours and values are interchangeable.
UNO PICKUP - Picks up a card!
UNO CALLOUT - Calls a player out for only having one card left!
UNO HAND - Checks your hand!
UNO RULES - Checks or sets the game rules!
UNO! - Let everyone know that you only have one card left!

You can execute up to two commands in a single message by separating them with &&!
```

The player will get their cards in a PM by the bot itself but to the command needs to be executed in the room where the players are playing (not privately).

## Configurable Rules

One of the features of UNO is configurable rules, to make sure your games are as customizable as possible! You can view these using the `uno rules` command.

To set, the creator of the game has to run the command: `uno rules <key> <value>`.

Current rules:

### Decks

Key: `DECKS`
Type: integer
Default: 1

This is the number of decks to use in the game.

### Initial Cards

Key: `INITIAL_CARDS`
Type: integer
Default: 7

This is how many cards to pick up at the beginning of the game.

### Draws Skip

Key: `DRAW_SKIP`
Type: boolean
Default: true

This is whether pickup cards (+2, +4) should also skip the next person's turn.

### Must Play

Key: `MUST_PLAY`
Type: boolean
Default: false

This is whether a player has to play a card if they're able to, instead of drawing.

### Callouts

Key: `CALLOUTS`
Type: boolean
Default: true

This is whether other players are able to call someone out for having only one card but not saying uno!

### Callout Penalty

Key: `CALLOUT_PENALTY`
Type: integer
Default: 2

This is how many cards a player has to pick up with someone successfully calls them out.

### False Callout Penalty

Key: `FALSE_CALLOUT_PENALTY`
Type: integer
Default: 2

This is how many cards a player has to pick up if they try to call someone out, but everyone has more then one card.

### Automatically Play After Draw

Key: `DRAW_AUTOPLAY`
Type: boolean
Default: false

Automatically plays a card after drawing, if possible. If a wild card is drawn, will give a prompt for color.

## Selfhosting

You may selfhost (AKA run your own instance of) this bot under the following circumstances:
- Your instance (referred to as a "clone") must be **private**.
    - As such, your clone must not be listed on any sort of public bot listing.
- You understand that no support will be provided to aid you in self-hosting.
- You agree to not submit any issues, features, or pull requests related to bugs exclusively related to self-hosting.

### Configuration

config.json (`config.example.json`), the oauth part is not mandatory (it is used for the web interface) but if you don't needed you need to leave the settings with default values.

config/config.json (`config/config.example.json`), support various database with this example will use SQLite.

### Dependencies

After running `npm install` it is required to migrate the new database (after put the configuration files) and run `npm run sequelize db:migrate`.
Now, you can run the bot with `node index.js`.

## Disclaimer

This bot is not associated with UNO or Mattel in any ways.
