---
title: "Dungeon Roll - Improving Board Game Accessibility With Alexa"
categories: [BoardGames, Alexa]
permalink: /boardgames/dungeon-roll-improving-board-game-accessibility-with-alexa/
---
With the ongoing Corona Pandemic, I am not able to play much with my group. So, thanks to Alexa, I can still get my board gaming fix.

## Introduction

Hey folks, it's been a while since my last post and podcast episode. First, I hope anyone reading this is following the safety recommendations and staying at home until everything gets back to normal. Like everything else, this will also come to pass, but it is up to us on how it is eventually resolved.

In the past couple of months, I have been spending most of my time adapting solo board games for Amazon's voice assistant, Alexa. I have mentioned this on the podcast, but as you might guess, blind people can have a lot of difficulties with solo board games, especially if they can’t read braille. When playing multiplayer games, we usually have someone sighted nearby to provide assistance when we need it, but when playing solo, we have to somehow modify the game components to be able to identify them. If we use Alexa, we don’t need to do any of that, and we can jump straight to playing the game.

## The Initial Idea

I am a member of a small [blind board gaming community](https://bbg.groups.io/){:target="_blank"}, and once a month, one of the members hosts a group voice chat where we talk about board games. The discussions usually focus on the games we have recently played, modifications that we’ve done on certain games to make them accessible, and general talk about how we can play certain games.

At one of these monthly meetings, one of our members, Brian Counter, presented the idea that it would be great if we could play some board or card games by using Alexa. At the moment, I am only familiar with one single game that has been adapted for Alexa, and that’s [No, Thanks!](https://www.amazon.com/Fangtastico-No-Thanks/dp/B07D72XHLL/ref=sr_1_1?dchild=1&keywords=no+thanks&qid=1587422140&s=digital-skills&sr=1-1){:target="_blank"} It actually works very well, and even has AI opponents if you do not have anyone else nearby to play with.

One game that Brian wanted to play independently was [Dungeon Roll](https://boardgamegeek.com/boardgame/138788/dungeon-roll){:target="_blank"}, a push your luck dice game where you enter a dungeon to fight monsters, a dragon, and collect loot to earn points. Even though this game supports multiple players, it actually works very well as a solo experience. Since the game only has dice, a few cards, and tokens, it is not very hard to make it fully accessible, even without braille. You could use standard six sided dice with pips to identify what you roll, create a reference sheet where you have information about what each die number means, and mark the tokens to make them easy to identify. There are still going to be some difficulties, but most importantly it will take you much longer than 20 minutes to play a full game with this approach.

What if we have Alexa as the dungeon lord to run the game for us? What if we could tell her “Attack skeletons with cleric”, and she does all the heavy lifting for us? Back in January, this was just a dream. I told Brian that I will look into developing the game for Alexa, but didn’t make any promises.

## From Zero To Playable Hero

It had been a long while since I had programmed anything, and back then I still had enough vision to see the text on the screen. Besides learning how to develop skills for Alexa, I also had to learn how to use the development tools with a screen reader. After spending a few days on setting up my development environment and familiarizing with the new keyboard shortcuts I needed to use, plus a few emails to ask how other programmers using a screen reader do all of this, I was ready to start coding an Alexa game.

If you are familiar with the Dungeon Roll rules, you know that there can be a lot of variables, especially with all the different hero powers. Because of this, I had to find a different game to adapt; something that would be shorter to play, and had simpler rules. This game was [Desolate](https://boardgamegeek.com/boardgame/249675/desolate){:target="_blank"}, designed by Jason Glover, and published by Grey Gnome Games. 

Desolate is a science fiction card and dice game that uses a very clever mechanic to explore a space station and fight aliens. The main game loop was quite simple, and there also was a [command line implementation of this game available on itch.io](https://kemp.itch.io/desolate-text){:target="_blank"}. So, this game was a perfect fit for my first project while I got used to coding for Alexa.

It took me about two weeks to get the first playable version of Desolate ready. My brother helped every time I needed sighted assistance to figure things out on the Alexa Developer Dashboard. The website has some unlabeled buttons, and is not very screen reader friendly, but with some help and memorization of where things are, I can use it independently 90% of the time.

The good thing about Alexa development is that you can set up a beta version for the skills pretty fast. There are no certification requirements and wait times, so I sent out invites to my blind friends to test it out. I received some great feedback from them about some user experience improvements which later helped me with the development of Dungeon Roll as well. I had a lot of fun developing Desolate, and all it needed now was a little bit of polish before release, but I really wanted to start working on Dungeon Roll, so I put Desolate on hold.

Developing Dungeon Roll was definitely more complex. Since I had taken a long break from coding, I had to spent much longer coming up with an architecture that wouldn’t cause problems later down the line. The main challenge was coming up with a system that was flexible enough to add all the different hero types with their own abilities. It took me roughly two and a half weeks to have a playable version with two heroes, the Spellsword and the Mercenary. 

At this point, it was time to send out beta invites to see what other people thought, and more importantly does this feel like actually playing the physical board game even though all you do is talk to Alexa. It was very nice to read those positive comments and how much people were enjoying the game. With some great feedback from the testers, I kept working on the game for another month to iron out the bugs, adding all eight heroes from the base version of the board game, and also the ability to save your progress if you can’t do a full run in one sitting.

Slowly but surely, I reached a level where I was satisfied with the state of the game, so it was ready to be marked as version 1.0 and released to the public.

## Dungeon Roll Alexa Skill

The skill is available for free in all the countries that support the English locale: US, Canada, UK, Australia, and India. You can use the Alexa app to search for Dungeon Roll, or you can simply try saying “Alexa, enable Dungeon Roll Game” to launch it. [Also here is a direct link](https://www.amazon.com/Ertay-Shashko-Dungeon-Roll/dp/B0872F4LT5/ref=sr_1_1?dchild=1&keywords=dungeon+roll&qid=1587423065&s=digital-skills&sr=1-1){:target="_blank"} where you can enable the skill from your browser. You do not need to own an Echo device to play the game, you can also use the Alexa app on your smartphone. The Windows 10 Alexa app is also supported.

With that, as blind and visually impaired players, we can play Dungeon Roll independently without any assistance from someone who is sighted. If you try the game, I would love to hear what you think about it.

## Where Do We Go From Here?

Right now I am working on finalizing Desolate and submitting it for certification to be published on the Amazon Skills marketplace. I have a release candidate ready to go, but I am waiting to see if some of my beta testers find a bug or request a change before I push it. If all goes well, the skill should be available for everyone next week.

After that is done, I will start working on adapting Deep Space D-6, a very popular spaceship survival game. I have played multiple games of  this as it also has a free print-and-play version, and I believe it should be a great fit for Alexa. To play the physical version, I had to create a reference sheet for the cards, and then use the Seeing AI app to determine the cards I drew. This extended the game-time quite a bit, and it took me over an hour to play a single round, so with Alexa this should be improved quite a bit.

## Credits

I’d like to thank Brian Counter for sharing this idea with me which eventually led me to get back into coding again. I really enjoyed working on these two games the past two and a half months and I will keep doing this a little longer.

Chris Lehman was my number one beta tester as he provided tons of feedback, and even recorded himself playing to help me figure out some weird issues and give me an idea how other people would play the game.

Ryan Peach for organizing the monthly group calls. This wouldn’t have happened if he didn’t take the initiative to bring a few blind board game enthusiasts together.

Nancy Feldman and Zack Cline for taking part in the beta and for providing super useful feedback.

Peter Hansen for listening to my ramblings about how to structure the game code and sometimes giving some decent insight on how I should do certain things.

Finally, Chris Darden, the designer of Dungeon Roll, and Jason Glover, the designer of Desolate, for designing highly entertaining games for us to enjoy, even though we needed to put some time and effort to make them fully accessible for the blind and visually impaired!