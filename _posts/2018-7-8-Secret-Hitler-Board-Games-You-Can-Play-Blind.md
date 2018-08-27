---
title: "Secret Hitler - Board Games You Can Play Blind"
categories: "Board Games"
permalink: /Secret-Hitler-Board-Games-You-Can-Play-Blind/
---
It is the early 1930s in Germany. The fascist party is on the rise and they can be ruthless when it comes to completing their main goal: get Hitler, their cold-blooded leader, to power. How effective can you be at helping or stopping him as a blind politician? Let's find out...

## Introduction

Welcome back to the second post of the 'Board Games You Can Play Blind' series! Today we will talk about one of my most played games, and the game that introduced me to the world of modern board games, _Secret Hitler_. 

Similar to the [first post]({{ site.baseurl }}/Pandemic-Board-Games-You-Can-Play-Blind/) of this series, we will start with a brief overview of the game and the rules. Then, we will have to switch gears becuse unlike _Pandemic_, _Secret Hitler_ has hidden information, so we will analyse the visual accessibility problems that are introduced as a result. We will then finish with my solution to problems. 

![Image showing production copy of Secret Hitler]({{ site.baseurl }}/images/SecretHitler-Production.jpg "Secret Hitler Production Copy")
_Image showing production copy of Secret Hitler_

## Game Overview

* Game name: **Secret Hitler**

* Publisher: **Goat Wolf & Cabbage**

* Player count: **5-10**

* Playing time: **45 minutes**

Secret Hitler is a social deduction party game in which each player takes the role of a German politician from one of two opposing parties, liberals and fascists. One of the fascist players becomes Secret Hitler. In order to win, the liberals must either find and assassinate Hitler or enact five liberal policies. On the other hand, the fascists win if Hitler becomes the chancellor after three fascist policies are enacted or if a total of six fascist policies are enacted.

In the beginning of the game, each player is secretly assigned a role. Once everyone has looked at their own role, all the players close their eyes. The player that has Hitler's role raises a thumb, while the other fascist players open their eyes to see each other and also see who Hitler is. In the beginning of the game, the liberals and Hitler have no idea about which party each player belongs to. Because of this, the liberals always have the majority at the start of the game, as they start with a disadvantage with the lack of information.

In each turn of the game, one player becomes the president and nominates another player to become the chancellor. Next, all players take a vote whether they accept or decline the nomination. If the vote passes, the president draws three policy cards,  discards one policy card, and passes the remaining two cards to the chancellor. The chancellor, then, chooses one of the policy cards they wants to enact and discards the other. The chancellor and president can then tell the other players what policies they had drawn, but they are free to lie if they want to.

For instance, if the president is a liberal player and draws two fascist and one liberal policy card, the player discards one fascist policy and passes the rest to the chancellor. Now, if the chancellor is a fascist, they could enact the fascist policy and claim that the president gave them two fascist policies and they had no choice. The president will then deny those claims, but as one of the other players it is up to you to deduce who is telling the truth.

Depending on the number of players, there are different abilities that activate when a fascist policy is enacted. For example, in a 7-8 player game, when the second fascist policy is enacted, the president is able to look at any other player's party card to find out their true allegiance. So, sometimes a liberal president may force a fascist policy in order to gain information about a suspicious player.

The game usually lasts around 45 min, but they can also last over an hour if the players are experienced in the game, so discussions and accusations may last longer. At the bottom of this post, you can find a few links to the full game rules and a gameplay video.

![Image showing my personal copy of the print and play version]({{ site.baseurl }}/images/secret_hitler_pnp.jpg "Secret Hitler Print and Play")
_Image showing my personal copy of the print and play version_

## Visual Accessibility Problems

If you carefully read the game overview above, you might have noticed a couple areas that are problematic for blind players. Even though there only are two problems, they practically make the game unplayable if you are blind. Both of these issues are caused by one mechanic, _hidden information_. Unlike Pandemic, you cannot just ask another player to read your cards for you.

The first obstacle is in the role assignment and fascist reveal phase. If you have drawn a role that does not require you to open your eyes to see your teammates, great! But, what if you drew a fascist role and need to know who Hitler and who your teammates are? Playing as a blind fascist is a huge disadvantage. Before I came up with a solution to this problem, I played a game where I was a fascist player and accidentally shot Hitler because I had no idea who he was (and Hitler usually disguises as the most liberal to avoid suspicion).

The second issue lies with the policy cards. I only have the print and play version of the game, but I'm assuming the production version also has this problem. As a president or chancellor, you need to be able to distinguish between liberal and fascist policy cards. The only indicators on the cards are the color, icon and text.

There are some people that would think that playing blind is a huge disadvantage in any social deduction game, since you cannot see other players' body language or just look straight at their eyes when they are lying to you. Personally, I haven't felt disadvantaged, as the game is designed in a way that players' decisions help you deduce what their true intentions are. You can always pick up the changes in their voice when some players are nervous, too.

## Tech and Tape To The Rescue!

After a couple stressful rounds as a fascist, I had to come up with a solution to the role assignment and fascist reveal phase. The solution had to be simple and not extend the duration of the role assignment by too much. Since I'm a software engineer, I came up with a smartphone app idea. After a few hours of prototyping, _Board Game Aid_ was born (working title, feel free to suggest a better name).

![Image shows two screenshots of the prototype app, edit players page and role assignment page]({{ site.baseurl }}/images/BoardGameAid-Screenshot-1.jpg "Board Game Aid Prototype Screenshots 1")
_Image showing my personal copImage shows two screenshots of the prototype app, edit players page and role assignment page_

The main purpose of this app is to randomly assign player roles. Each player looks at their own role and then passes the phone to the next player. If a player gets the fascist role, they can also see the names of other fascist teammates and the name of the player that got Hitler's role. In the initial version, I only  increased the text size, slapped on a dark theme because I can still read light text on a dark background, and brought the app with me for our next meeting with my friends.

The first playtest went really well, but it wasn't without kinks that needed to be fixed. The main issue was with players passing the phone to the next player too fast when they were assigned a liberal role or the role of Hitler, while fascists needed a few more seconds until they read the names of their fellow fascists. 

To fix this, I simply added a countdown timer that starts ticking after you click to reveal your own role. The player is not allowed to pass the phone until the timer hits zero. A few days ago, I also added text-to-speech capabilities for blind players. When adding the players in the 'Edit Players' page, you have the option to enable voice capabilities for a certain player, so when it is their turn to look at their role, they put on headphones and tap on 'Speak Role'. The speech synthesizer speaks their role, and if they are a fascist player, reads the names of the other fascists and Hitler.

When the last player sees their role, you can then use the app for the 'Party Inspection' ability that I talked about above, where a player can find out which party another player belongs to.

![Image shows two screenshots of the prototype app, fascist role assignment and party inspection]({{ site.baseurl }}/images/BoardGameAid-Screenshot-2.jpg "Board Game Aid Prototype Screenshots 2")
_Image shows two screenshots of the prototype app, fascist role assignment and party inspection_


For the second problem with the policy cards, I had a much simpler fix: tape. Since there only are six liberal policy cards, I just marked the insides of the cards with a little piece of tape. Now, I could easily distinguish between a liberal and a fascist policy card by touch. For those of you who can read braille, you could print out braille labels to put on the policy cards, but since it's only a choice of two different types of cards, a simple tactile marker is more than enough.

![Image shows a liberal policy marked with a piece of tape and an unmarked fascist policy card]({{ site.baseurl }}/images/SecretHitlerPolicy-Tape.jpg "Secret Hitler Accessible Policies")
_Image shows a liberal policy marked with a piece of tape and an unmarked fascist policy card_

With these solutions, the game becomes fully accessible for the blind and visually impaired. If I didn't know how to code, I don't know if I would've been able to find a better alternative that does not involve having an extra person around to do the role assignment and reveal phase. If you happen to have other creative solutions, feel free to share them in the comments below!

## Board Game Aid - Where can I get it?

I was planning to publish the app in the Google Play Store, but right now it's in a very rough visual state if you can see from the screenshots above (even though you wouldn't really care about the visuals as a blind player, most of your friends are probably sighted).

Because of this, I decided to put the [source code on GitHub](https://github.com/ertay/board-game-aid/){:target="_blank"} and if anyone reading this would like to contribute to the project to make it look prettier, feel free to get in touch with me! The app is created using Xamarin, if you want to contribute to the iOS version, let me know!

For now, you can grab the Android prototype package from [here](https://1drv.ms/u/s!As0NUJnxyVaqktUujLwTlUZ2aT6uvw){:target="_blank"}. To install, you will first need to enable the installation of apps from unknown sources in your phone settings. On my phone, that option is located under Settings -> Security.

You will notice that you can also play the base version of _The Resistance_, another social deduction game that suffered from the same problems as Secret Hitler. I'm planning to add all the roles of the _Avalon_ variant. There probably are other hidden identity games that can benefit from this approach, feel free to suggest any and I will try to add them to the app.

## Conclusion

I have played over 60 games of Secret Hitler in the past 2 years. It would really have been sad if I had stop playing it due to the accessibility problems. Creating the app was a fun project, and I am sure there are plenty of other games out there that can benefit from simple ideas like these to make them fully accessible for the blind.

I would love to hear any of your thoughts or suggestions. As I stated above, if you would like to contribute to the project, just drop me a message on [Twitter](https://twitter.com/ertaysh){:target="_blank"}, or get in touch via email at sightlessfun@outlook.com.

Auf Wiedersehen!

### Resources

Below you can find a link to the .apk of Board Game Aid, the PDF file for the print and play version that I am using, a PDF of the game rules, a gameplay video, and also a link to a _Harry Potter_ re-thame of the game, _Secret Voldemort_. If you want to play the game, but the theme is off-putting for your group, _Secret Voldemort_ is a great alternative.

- Android App Package: Board Game Aid Prototype - [Link](https://1drv.ms/u/s!As0NUJnxyVaqktUujLwTlUZ2aT6uvw){:target="_blank"}

- PDF: Secret Hitler print-and-play, color version, credit /u/panoramix87 on reddit - [Link](https://1drv.ms/b/s!As0NUJnxyVaqktUqxcXgO3g-HsqK8g){:target="_blank"}

- Video: Secret Hitler Sunday - TotalBiscuit - [Link](https://www.youtube.com/watch?v=k69PbHoSWm4&list=PLe6giXxNj6JlwhA7JUZK8R96O8AYjFcAk){:target="_blank"}

- PDF: Secret Hitler Game Rules - [Link](http://secrethitler.com/assets/Secret_Hitler_Rules.pdf){:target="_blank"}

- Secret Voldemort on BoardGameGeek - [Link](https://boardgamegeek.com/filepage/154533/secret-voldemort){:target="_blank"}