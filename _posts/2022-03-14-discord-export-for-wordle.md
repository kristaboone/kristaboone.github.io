---
layout: post
title: "Discord Export for Wordle"
tags: programming javascript
---

Wordle- the latest internet craze that gives you the chance to compete with your friends to test your literary chops.
My friends and I like to share our daily Wordle scores in a Discord channel, and someone got the idea to hide our guesses in spoiler text so that we
could see the struggle (or epicness) of the guessing journey to find the correct 5-letter word of the day.

The process became a big tedious- click the share button on Wordle's website, paste into the Discord channel, go back to the website, edit each line
of emojis to have your guess, get the formatting right, etc.

As a programmer, I abhor tedious work that can be easily automated. And so, Discord Export for Wordle was born!
You can check it out on [my GitHub page](https://github.com/kristaboone/discord-export-for-wordle).
Below are the details from the README.

> Note that this will only work on Desktop, the extensions will need to be available on the extension stores before their able to be used on mobile
> (which I might pursue at a later time...)


## About

Discord export for Wordle (DEW) is a web extension that will alter the functionality of the `Share` button on the NYTimes Wordle site. When the player has completed the game and clicks `Share`, instead of the clipboard containing just the emojis for the game, it will also have guesses appended to each line of emojis- hidden in a spoiler.

Take this Wordle game for example:

<img src="https://github.com/kristaboone/discord-export-for-wordle/blob/main/img/game.PNG?raw=true" alt="game" width="400"/>

Upon winning the game, the user will be shown their stats and a share button:

<img src="https://github.com/kristaboone/discord-export-for-wordle/blob/main/img/stats.PNG?raw=true" alt="stats" width="400"/>

Clicking the share button will copy this text to their clipboard to paste onto social media sites:

```
Wordle 269 4/6

🟨🟨🟨🟨⬛
⬛🟨🟨🟨🟨
🟩🟩🟩⬛🟨
🟩🟩🟩🟩🟩
```

DEW will edit this output so that it becomes:

```
Wordle 269 4/6

🟨🟨🟨🟨⬛ ||`steam`||
⬛🟨🟨🟨🟨 ||`dates`||
🟩🟩🟩⬛🟨 ||`teals`||
🟩🟩🟩🟩🟩
```

This output, when pasted into Discord, will render as the following:

<img src="https://github.com/kristaboone/discord-export-for-wordle/blob/main/img/discord-1.PNG?raw=true" alt="discord" width="400"/>

This allows you to share your guessing journey with your friends, but keeping things spoiler-free- let's just hope they don't take a peek at those words until they've finished their game. ;)

## Installation

The current iteration has been tested with Firefox and Chrome.

### Firefox

1. Clone this repository, or download `dew-1.0-an+fx.xpi` in `/xpi`
2. Open FireFox
3. Use `ctrl + shift + a` to open the Add-Ons Manager tab
4. Click the gear on the upper right-hand side of the screen
5. Click "Install Add-On from File"
6. Navigate to and select the XPI file you obtained from step 1
7. Head over to the [NYTimes Wordle Site](https://www.nytimes.com/games/wordle/index.html) and try it out!

### Chrome

1. Clone this repository
2. Open Chrome
3. Click the puzzle piece in the upper right-hand side of the taskbar (OR if you do not see this, type "chrome://extensions/" into the address bar)
4. In the upper right-hand corner of the screen, click on the "Developer mode" toggle button
5. Click the "Load unpacked" button that was just revealed by unlocking developer mode
6. Navigate to and select this repository folder
7. Head over to the [NYTimes Wordle Site](https://www.nytimes.com/games/wordle/index.html) and try it out!
