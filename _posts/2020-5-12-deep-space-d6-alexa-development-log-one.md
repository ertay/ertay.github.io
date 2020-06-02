---
title: "Deep Space D-6 Alexa Development Log #1"
categories: [BoardGames, Alexa]
permalink: /boardgames/deep-space-d6-alexa-development-log-one/
---
In this post, I talk about the current development state of my Deep Space D-6 Alexa adaptation. This is the first post of a series that is exclusively available to my Patreon members.

After I released [Dungeon Roll]({{ site.baseurl }}/boardgames/dungeon-roll-improving-board-game-accessibility-with-alexa/){:target="_blank"} and [Desolate]({{ site.baseurl }}/boardgames/desolate-for-alexa/){:target="_blank"}, a few people asked me how  they can support my work so I can keep working on board game adaptations for Alexa. I decided to create a [Patreon](https://patreon.com/sightlessfun){:target="_blank"} account and one of the benefits that my patrons get are exclusive development diaries while I am working on the games. You can find the first diary entry below.

## The Development Log

Hello everyone,

First, I would like to welcome the folks that became patrons after I posted the previous welcome message. Thank you for supporting this project and I hope you will find the stuff that I am working on worthwhile!

Now, here's the development progress update for the past week. 

At the start of the week, all I had was rough skeletons and notes on how I will structure my code. It basically comes down to having a main class that keeps track of the game state, keeps track of the player's ship, and one more object that manages the threats and their actions.

In Deep Space D-6, during the player's turn you assign your crew to various stations on the ship so they can perform an action. The crew is represented by crew dice, and you have 6 of them. So, for every round you have a different set of crew dice to work with. 

The first thing I wanted to implement was the weapons and the ability to fire them at enemy threats. But, before I could work on the weapons, I needed to create some basic enemies to fire at. I went through the card list and created objects for all the enemies that have a single basic attack, with no special abilities.

Now that I had some sitting ducks to shoot at, I moved on to implement the weapons on the ship. There's two different weapons on the ship that is provided with the free print-and-play version of the game: a stasis beam that disables enemy threats for a round, and the standard lasers that do damage. The stasis beam can be operated by science crew, while the standard weapons are activated by using tactical crew. When you activate  your standard weapons for the first time in the round, they deal a single point of damage, but subsequent activations deal two damage. So, if you assign three tactical units to the weapons, you will deal a total of five damage.

I decided to use a single command that player's will provide to Alexa to fire the weapons: "Fire weapons", and Alexa then asks you to provide a target if you did not provide the target with your command. When a valid target is provided, one available tactical unit on your ship activates the weapons and deals damage to the provided enemy. If this was not the first activation of the weapons, two damage is dealt to that enemy. Nothing too complicated, right? Well that's what I thought until I realised that something was off with this approach a few days later.

Next, the stasis beam was pretty straightforward. You just use the fire stasis beam command and provide your target. If the target is valid, it gets disabled for this round and cannot trigger it's abilities when it is the enemy's turn.

Besides using the stasis beam, the science crew can also recharge the ship's shields. This was the functionality I implemented next which completed all of the science crew's abilities.

Next up was the engineering crew. The engineering unit has a single action, and  that is to repair hull damage on the ship. If you use a single engineer per round, you can repair one damage to the ship. Just like the weapons, subsequent ship repairs will repair two points of damage to the ship. So, if you repair the ship twice in the round, you will repair three damage to the hull.

The medical crew has two abilities. The first one is quite thematic and intuitive, which is to heal crew that is stuck in the infirmary. Some threats may cause some of your crew dice to be sent to the infirmary, and these dice are not available until you use a medic to heal them. The second action that a medical unit can do is remove a threat die from the scannerse. Now what does this mean?

When you roll your crew dice at the beginning of a round, you may roll threats. These immediately get locked in the ship's scanners. When there  are three threats locked in the scanners, a new enemy is drawn from the threat deck. So, if you have played Dungeon Roll, it is similar to how the dungeon dice that roll Dragons get locked in the Dragon's Lair.

The main problem  with the locked threats is that these dice stay locked until you either remove them using a medical crew, or the scanners fill up with three threat dice and a new threat is drawn from the threat deck. They do not reset at the end of a round, so you will have a smaller number of crew dice to  roll. As I mentioned earlier, the medical crew being the one to remove threats from the scannerse is not very thematic or intuitive, but I guess the other crew types were already too occupied with other actions they can do.

Finally, the last crew member functionality I implemented was the commander. In  the free print-and-play version of the game, the commander  has two actions: transform another available crew member to a type of your choice, or roll all the available crew dice. In the retail game, the ability to roll the dice is removed, and I think the main reason for this is probably the fact that it rarely was used. I have played the print-and-play version multiple times, and I have never used this ability. So, at the moment, I have only implemented the ability to transform crew members from one type to another.

With that, I finished implementing the crew actions. At least that's what I thought until I realised that there is a bug with the weapons code. In the game rules, it says that you can split the damage that you are about to deal however you want between multiple targets. The problem with the approach I took for firing the weapons was that when you fire the weapons for the second, third, or fourth  time, you deal two damage to the provided target, regardless whether that target only has one health remaining. So, it was time to refactor and come up  with a new approach. 

The solution I decided to go with was the following: First the user asks Alexa to assign a number of tactical units to the weapon systems. Once that request is validated, Alexa tells the user what the total damage is and to fire the weapons, the user needs to give that command to open fire. When you fire the weapons now, you need to provide two pieces of information: The first is the target, just like before, and the second piece of information is the amount of damage you are going to deal to that target. This approach solved the problem with being able to split the damage between multiple targets. The main drawback is that to open fire, you now need to issue two commands instead of just one.

With that solved, it was time to add some logic to the threat manager and give an attack ability to the enemies. The enemey's turn is quite simple. You roll a six sided die, and depending on the result, the enemies get activated. At the moment, I only have generic enemies that have no special abilities, and all they do is open fire when they are activated. Enemies that are disabled with the stasis beam are ignored during the enemy activation phase until the next round.

Coding the enemy attacks also required to code how the damage to the player ship is processed. When the player ship is attacked, the damage first goes to the shields and if your shields are brought down to zero, you start taking hull damage. There are also some enemies that can ignore  your shields and cause damage to your hull directly.

So there you have it, the first progress report of Deep Space D-6 for Alexa. I'm currently a bit stuck with how to implement the ability  to send  your crew on missions as some enemies can be defeated by sending different crew types on missions instead of destroying  them with your weapons. After I figure that out, I am planning to work on adding the remaining enemies that have special abilities and implement all of their functionalities. If all goes as planned, I should be done with this by the end of next week. At that point, we should have a fully playable game, so I will add some rules to teach you how the game is played and publish the beta for you to try it out. While the game is in beta, I will work on adding sound effects to improve the experience.

If you read this far, thanks for reading, and feel free to let me know if you have any comments or questions.

Until next  time, over and out!

Ertay

## [Become a Patron for Early Access](https://patreon.com/sightlessfun){:target="_blank"}

Posts like the one you just read are exclusive to my patrons. A lot of  time and effort goes into developing the adaptations of these games and releasing  them for free. If you like what I do and enjoy playing these games, or you just want to support something that makes the hobby more accessible to a wider audience by making those games playable for the blind and visually impaired players, you can [become a patron on Patreon](https://patreon.com/sightlessfun){:target="_blank"}. In return, you will be able to get early access to the beta versions of the games while they are still in development and help shape up the final product. You will also be able to participate and vote on future games that I will be adapting next.