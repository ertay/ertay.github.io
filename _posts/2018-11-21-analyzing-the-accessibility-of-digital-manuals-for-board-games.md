---
title: "Analyzing The Accessibility Of Digital Manuals For Board Games"
categories: BoardGames
excerpt: "An analysis of the current state of PDF rulebook accessibility and screen reader support."
---
## Introduction

The manual is the foundation of any board game. Without it you end up with overpriced cardboard and plastic. Most people learn how to play a game by being taught by someone else around the table. In most cases, this person is the owner of the game. Now, what if the owner is blind? 

In this article I will talk about the current state of the accessibility of _digital_ manuals for board games. In my group, I am the person that brings the board games, hence I am the person that usually teaches the game rules to others. As I am legally blind, not Being able to read the text makes the physical manual useless. Well, besides using it to light the fireplace... 

## Why digital manuals?

I specifically emphasized the type of manual because when you talk about board game manual accessibility, that is a very broad topic. It can be about the form factor of the manual, the choice of fonts, structure, clarity of sentences etc. Michael over at Meeple Like Us has an excellent post about it. You can find the link in the Resources section at the bottom of this post.

Blind people consume textual information by touch using Braille, and through sound by having someone or something read the text to them. Thanks to computers and the smart people who invented screen readers, we are able to consume huge amounts of textual information quickly with speech synthesizers. Board game manuals don't come with a braille version, so we either need to bother someone else to read the manual to us every time we need to look something up, or get the digital version (PDF) from the internet and use a screen reader program that does not yell 'I read that part to you already!". You see, screen readers know that good manuals are not very common, so they do not protest or question your intelligence when you ask them to repeat a paragraph for the 25th time because your brain malfunctioned and could not process what it just heard. Amazing, right?

## Problems With PDF Manuals

By now, you are probably thinking, "Oh that's nice, blind people are not excluded and can read a rulebook just like anyone else!". But, unfortunately you are so wrong, because you are still not aware that creating a screen reader accessible PDF is harder than sending a Tesla to Mars. So, naturally most publishers do not have the budget for such a task.

The most common problem with PDF manuals is that when they are created, they are exported to PDF as images. It is very likely that you have come across such a PDF document and you've probably cursed immediately after trying to copy part of the text or used the 'Find' function to quickly find a keyword in the document. When you have a document like this, screen readers are not able to detect any text, so they will either say "Image" or in most cases produce an error sound because the image isn't even tagged as an image; all the screen reader can 'see' is a blank page.

Then, there are PDF documents where the raw text is readable by the screen reader, but the whole page is highlighted as one single block. I was super excited when I saw that my iPhone started reading the text of the _Dice Forge_ manual, and when I swiped left to make it repeat the last paragraph, it started reading the whole page from the beginning. But hey, at least this gives me the same thrilling feeling as _Diablo 2_ in hardcore mode did, back when I could play that game. You get one chance mister, otherwise back to the starting line! 

After testing the _Dice Forge_ manual in multiple PDF reader apps, I discovered that the native Books app on iPhone is able to separate it into lines, but it still struggled and instead of highlighting a line, it often reads a single word or two. Navigation in such PDF files is a huge pain. There's no distinction between headings and normal text. 

Next, there are PDF manuals that are semi-accessible to a screen reader. In such files, you can listen to the separate paragraphs, but other types of items are not properly tagged. For example, headings are not marked as headings which prevents you from navigating the document using the headings of different sections. Furthermore, images have no descriptive text, so you have no idea what the image shows. Then there could be structural problems which may make the screen reader say something like "In the game IMAGE your main FOOD TOKEN objective is...". This happens when there are some graphics and text near the paragraph. For sighted people, this is not a problem because usually the designs are made to guide the eye to consume the information in an orderly fashion. However, for the screen reader, this needs to be explicitly marked so that it doesn't produce the sounds of a drunk robot. An example of such a manual is the official _Keyforge_ manual which is only available in digital format.

Lastly, I have also found some semi-accessible PDFs that have the necessary accessibility tags, but for some reason they are not picked up by the reader apps. One such file was the manual of _Nyctophobia_. Acrobat Reader on my iPhone didn't detect the headings, so I just thought they are simply not marked. I tried the Books app, and it just froze when trying to open the file. After opening the PDF using Acrobat Reader on PC, I realized that the tags were there, but they weren't detected on the phone apps. To do a simple test, I tried applying auto tagging to the document, which processes the whole document and tags the content automatically. This process is not very accurate, but it still did an acceptable job. I copied the PDF back to my phone and voila, headings were recognized, though the auto tagger hadn't detected all of them to mark them. The interesting thing was that the Books app could now open the new PDF with auto tags. My best guess is that there's some kind of corruption with the way the original tags are constructed. The Acrobat Reader app on the phone most likely ignored them, while the Books app did not, hence  it froze.

## Accessibility Requirements

Most word processor and design programs provide tools for properly tagging PDF objects, however based on the number of inaccessible digital manuals, it seems like the authors don't use them at all. Even after exporting a document to the PDF format, if it wasn't exported as an image, programs like Adobe Acrobat give you the ability to tag the objects so that screen readers can understand the different object types. Besides specifying objects, you are also able to modify the order in which they are read. This is represented by a tree, so you can divide each section to a different branch. Most board game rulebooks require these sections to be structured manually since board game rulebooks are not as simply structured as a novel. 

When there are multiple columns, blurbs, emphasized parts in a corner that give an example, or a graphic in the middle with lines sticking out from all sides with explanations to different parts of the graphic, you need to make sure that the items are tagged in a logical order so that it can make sense when a blind user navigates the information from one item to the other.

There also are items that should be explicitly marked to be ignored, such as decorative borders or artwork that are used to guide a sighted person from one section to the other as they are reading the manual. You certainly don't want to hear "diagonal line, image' in the middle of the text as you're listening to the speech synthesizer. 

Images, once tagged as such in a document, have an extra text field called _alternate text_ or simply _alt text_. This field is used to describe the image and when the screen reader processes an image object, it reads this description aloud. Note that this text is not visible on the actual page of the PDF, it gets embedded in the 'code' that the screen reader uses. 

It is extremely important to describe icons, especially if they are not mentioned by name in the manual. Many manuals show a graphic icon on the left, while on the right side they describe the action that is represented by that icon, e.g. an arrow icon that represents a 'Move' action. One could argue that there is no need for the blind person to know what the icon looks like because they can't see it, so they need a different form of communication to distinguish the actions, like braille or other tactile markers for the cards. However, when a blind person is the one teaching the game, they still need to know what the icon looks like so they can explain the action of each icon.

Headings are used to structure different parts of a game, like game components, setup, player's turn etc. When headings are properly tagged so that the screen reader can distinguish them from normal text, they can be used for navigation in the document. Using a screen reader, you can quickly jump from one heading to another, just like a sighted person would do when skimming the manual for a specific part they need. A hyperlinked table of contents would also be nice to have.

Tables also require proper care. Tables in manuals are usually used when there are different setups for different numbers of players. So, you need to make sure the screen reader can detect each cell properly.

The concepts of making a PDF accessible are very similar to those used in web accessibility. To find out more about PDF accessibility guidelines and techniques, check the Resources section at the bottom of this article.

## Alternatives to PDF Manuals

You now see that blind players not only have to deal with poorly written and ambiguous manuals, but also with inaccessible or semi-accessible PDF files. There are a few alternatives to learn a game on your own and then teach others.

### Rule Summaries

The first resource are rule summaries on Board Game Geek. You simply navigate to the web page of the board game you are interested in and then go to the Files section. There are plenty of summaries written by the community that sometimes do an even better job at explaining the rules than the actual manual. But, there also can omissions of more obscure scenarios, so you might still need the official manual in some cases.

These summaries are usually written in a word processor without any graphics or extra bells and whistles and then exported to a PDF file. The text in most cases is accessible, however it may not be enough to learn the game..

### Rulebook.io

Few days ago I was searching for the PDF manual of _Jamaica_, a pirate themed racing game. I found the PDF and, of course, it was a godforsaken image that was completely inaccessible. 

This forced me to check few other links on Google and I discovered Rulebook.io. This website is a board gamer's passion project and the idea is to save mobile data by converting the PDF rules into plain text, without the extra graphics and overhead. The content of the website is open-sourced and anyone can contribute. All you need to know is how to write in Markdown (Reddit uses markdown for formatting the text). 

The main drawback here is that there are no graphics, however that shouldn't be a hard problem to work around. The posts can still be text only, but at the end, having a textual description for any icons or necessary colors could work just fine.

The developer of the site is not aware that a project like this can be very useful to the blind and I tried contacting him to ask him to do some minor fixes to the HTML of the site so that it is even more accessible to screen readers. Right now, the site does not use proper 'heading' tags to mark different headings, though at the moment there is a hyperlinked table of contents at the beginning of each rulebook to help with navigation. 

If you feel like contributing to the site by adding a manual that is not there, you can check this [page](https://rulebook.io/how-to-help){:target="_blank"}.

### How To Play Videos

Finally, how to play video tutorials on YouTube can help when all else fails or you need some extra clarification for specific parts of a game. The drawbacks of videos is that sometimes the author of the video shows a card and states the action but does not describe what an icon looks like, because they assume the viewer is sighted. In any case, these videos can complement the rule summaries I mentioned above.

## Conclusion

As of today, the accessibility of digital manuals is quite poor. Blind players have to jump over extra hurdles in order to learn a game independently and I really hope more people make an effort to talk about this and force publishers to improve their work. 

I am quite aware that writing a good rulebook is not an easy task. I know that a lot of work and effort goes into writing a good rulebook and I really appreciate the time that is spent on them. But it really is very frustrating that all that effort is thrown to the trash can when the publisher uploads an inaccessible image scan to their official website. If you are a publisher reading this post, for the love of everything that is holy, stop uploading an image. It really does not take much time and effort to apply the most basic accessibility techniques and follow accessibility guidelines to make the final product shine.

### Resources

- [Meeple Like Us Article - The Universal Inaccessibility in Board Games](http://meeplelikeus.co.uk/the-universal-inaccessibility-of-board-games/){:target="_blank"}

- [PDF Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html){:target="_blank"}

- [Rulebook.io](https://rulebook.io/){:target="_blank"}