---
title: "Deep Space D-6 Alexa Development Log #3"
categories: [BoardGames, Alexa]
---
This is the third Deep Space D-6 for Alexa development log post that was published for my patrons on Patreon on May 29th 2020.

## The Development Log

Another week has passed and I am back with a new development log. Before I begin, I just want to let you know that your support and feedback is making all of  this possible, so thank you very much!

Last Friday I published the first beta version for Deep Space D-6 and all of you that are in the $5 or higher tier should have access to the sign up link and see the instructions for enabling the beta on your Amazon accounts. If you are having any difficulties with this, let me know and I will try to sort things out for you.

As I have mentioned before, this game is more complex compared to the past two games, and it also takes longer to play a full game… unless you are doing pretty bad and you get destroyed in a handful of turns! Because of this, finding more obscure bugs will take longer as there are a small amount of playthroughs in the same time period compared to the previous two games. You can easily play three or four Desolate rounds, while Deep Space D-6 can take a full hour to go through the threat deck. But, this is where thet save game feature is handy as your progress is saved and you can continue where you left off the next time you launch the game.

I just published a new update and all of you that are in the beta should have access to it. Beta version 2 contains sound effects, and bug fixes for some of the issues that you reported. While I was playing myself I discovered a couple other bugs that I fixed.

Deep Space D-6 is the first game where I wanted to use custom sound effects, i.e. sound effects that were not from the free Amazon Alexa Sound library. Finding public domain sounds or sounds with royalty free licenses took most of my time this week. I probably went through over 2000 sound effects and settled on about 20 that are now included in the game. I still used some sounds from the free Amazon library as  they fit some of the scenarios quite well. All of the explosion sounds for example are from Amazon’s free library. I was also struggling with the fire weapons sound effect for the player’s ship, but eventually found one that is similar to the one in Desolate.

When you get a chance to try this new version, I would love to hear what you think about the added sound effects. Also, if you have ideas for other parts in the game and the types of sounds you think would fit there, let me know. Moreover, since I do not have an Alexa Echo, or a smart speaker that supports Alexa, I have no idea how these sound on the actual devices. They sound different when I compare them on my cheap $5 earbuds vs my over ear headphones, so let me know if you hear any glitches on your Amazon speakers. Sadly the highest bitrate for Alexa sounds is only 48kbps, so hopefully some of the custom sounds I used are not completely destroyed after the compression.

When it comes to the bug fixes, there were a couple of grammar mistakes or typos in the text that I  fixed. One of you reported a problem with the Bombers. Looks like Alexa doesn’t like these dudes and usually has trouble identifying the keyword. When I ran some extra tests, I noticed that when you say Bomber One, it resolves into Number One. Apparently Alexa sometimes also is committed to piss you off and resolves it into Momma One. To work around this, I added another keyword in front of the name, so now the bombers are all called Strike Bombers followed by their number. I believe in the retail game the publisher has also renamed the bombers into strike bombers. I should also mention here that in the actual game, enemy threats that have duplicates do not have numbers associated with them. In the Alexa adaptation, I had to find a way to distinguish between those duplicates, and I decided to go with numbers after their names. 

Initially, I was thinking of going with keywords like Alpha, Gamma, Delta, instead of numbers after the enemy threats’ names, but eventually settled on numbers. If anyone has a better idea than using the numbers, let me know. However, this solution seems to work fine so far. If you experience issues with the bombers or any other threat, drop me a message and I will look into it. One of the problematic keywords in Dungeon Roll is the Elixir which Alexa resolves to ‘Alexa’ so when you say Elixir she thinks you are using the wake word which confuses her. I was more cautious this time around when creating the keywords, but someone can still run into issues with some of the words depending on their accent.

There were a few other bugs that I discovered while playing the game. One of them was with the Meteoroid. If the meteoroid was the last active external threat with an empty  threat deck, and during the threat activation phase it destroyed itself, the game was supposed to end. This didn’t happen until you ended your turn, so I fixed that it automatically ends the game now.

Another bug was with the scanners when the threat deck is empty. This was not in the print and play game rules, but in the retail game, if the threat deck is empty and your scanners are filled up with three locked threat dice, you are supposed to take one damage because there are no more threats to draw. I accidentally ran into this bug and had to check BGG  to see what happens when you have no more cards to draw from the deck. This functionality is now included in the game.

That’s about it for this development progress report. But, before I sign off, there’s two things I want to mention.

The first is about the exclusivity of these development log posts. I have been considering making them timed exclusives for you, the patrons. For example, you get to read them first, and after a week they would also be publicly accessible to non-patrons. This should help with the discoverability of these projects and help me reach more people. 

The second one is that Patreon will start including sales tax for member subscriptions starting from July 1st 2020. Now there are some states in the US and countries in the world that have different tax rates for different categories, but since this membership of yours is general support, you should not be paying any sales tax. I spent some time going through the sales tax options that became available in my admin panel to make sure none of the tiers get taxed, but if you notice a sales tax is added to your membership after July 1st, please let me know so I can look into it.

With that said, we have reached the end of this update. If you read this far, thanks for sticking around, and enjoy your weekend!

## [Become a Patron for Early Access](https://patreon.com/sightlessfun){:target="_blank"}

Posts like the one you just read are timed exclusives for my patrons. A lot of  time and effort goes into developing the adaptations of these games and releasing  them for free. If you like what I do and enjoy playing these games, or you just want to support something that makes the hobby more accessible to a wider audience by making those games playable for the blind and visually impaired players, you can [become a patron on Patreon](https://patreon.com/sightlessfun){:target="_blank"}. In return, you will be able to get early access to the beta versions of the games while they are still in development and help shape up the final product. You will also be able to participate and vote on future games that I will be adapting next.