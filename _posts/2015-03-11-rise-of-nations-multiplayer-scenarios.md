---
layout: single
title: "Rise of Nations: Multiplayer Custom Scenarios"
excerpt: "How to play Rise of Nations Multiplayer Custom Scenarios, which can be particularly difficult to do."
tags: [rts, Rise of Nations]
category: blog
modified: 2015-03-11
comments: true
---

**Rise of Nations** is an amazing game that still holds no successors even to this day. It's Civilization meets the RTS genre, which puts you in the driver's seat of a nation through the ages. It is immensely fun when competing with others, or cooperating as a double team with a Prime Minister and General. This is a great game for LAN parties.

The core part of Rise of Nations is it's ability to simulate historic battles using custom scenarios. You can download and play tons of pre-made scenarios from [Rise of Nations Heaven](http://ron.heavengames.com/), [single-player](http://ron.heavengames.com/downloads/lister.php?category=single) and [multiplayer](http://ron.heavengames.com/downloads/lister.php?category=multi). Or you can just make your own, [by following these guides.](http://ron.heavengames.com/cgi-bin/forums/display.cgi?action=ct&f=11,18,,10)

Rise of Nations really becomes fun when you play with multiple users in a LAN party: either in a head to head competition, or more interestingly,** a cooperative mode** where two players can share one nation: one person could run the economy of a shared nation (like a chief executive) while the other expands and fights wars (lie a general).

## Converting Single Player into Multiplayer Scenarios

If you have a single-player scenario that is well suited to Multiplayer usage, such as the [Dutch War of Independence](), The Boxer Rebellion, After the Apocalypse, or Mesopotamia, you can convert them for multiplayer usage: 

1. Start Rise of Nations.
2. Choose the Scenario Editor, and open the scenario you want to edit.
3. Select the nation to edit at the top left box.
4. setting two or more nations to "Human" control (instead of computer control) in the Nation tab.

Conversely, you can convert multiplayer scenarios to single player by setting the players back to "Computer" control. This is really the only difference between a single-player and multiplayer scenario. Simple, eh? Well, it's not intuitive, this took a while for me to figure out.

### Installing Custom Scenarios

Make sure to extract the scenario out of any `.zip` files. Rise of Nations can only read folders.

1. **Single-player scenarios** - Place the scenario within a new folder within your Rise of Nations folder, (we'll call it 'SP Scenarios') which will give it the folder path `C:\Program Files\Microsoft Games\Rise of Nations\SP Scenarios`.
  * To play a Single Player scenario: Start up Rise of Nations, go to **Single Player**, click **Play a Scenario**, and navigate to the folder with the scenario in.
2. **Multi-player scenarios** (or a scenario where you can choose which nation you play) - Place the scenario in one of the following folders:
  * Rise of Nations (original): `C:\Program Files\Microsoft Games\Rise of Nations\scenario\custom`
  * Rise of Nations Gold/Thrones and Patriots: `C:\Program Files\Microsoft Games\Rise of Nations\Thrones and Patriots\scenario\custom`
  * To play it in game, go to **Multiplayer**, **Start a Quick Battle** and select the **scenario** option within the rules entry box on the right.
3. **Recorded Games** - These must be put into the **Recorded Games**, which is in `C:\Documents and Settings\Username\My Documents\My Games\Rise of Nations\Recorded Games` (replace Username with your username).
  * A recorded game has a .rcx file extension.

* [Source: Rise of Nations Heaven Forums - Where to put your files once you download them](http://ron.heavengames.com/cgi-bin/forums/display.cgi?action=ct&f=1,5698,,10)

## RoN Extended's Multiplayer doesn't work with Custom Scenarios

After the collapse of Gamespy, hundreds of games were now unable to play online multiplayer matches. Rise of Nations was one of them.

To revive the game, Steam partnered with Skybox Labs to create Rise of Nations: Extended Edition, a fully modernized port for modern computers.

Unfortunately, when playing custom scenarios, RoN Extended always crashes at the "Checking game" prompt, and the game hangs there.

The root of the issue is that RoN Extended does not implement the original scenario transfer system, [which makes it impossible to transmit custom scenario files.]( http://steamcommunity.com/app/287450/discussions/0/620703493329234760/?insideModal=1 )

Because the new developers are unresponsive and unreachable, *the only way to play custom scenarios is to use the original Rise of Nations Gold.* Unfortunately, this means that only LAN parties are viable, now that Gamespy is long gone.
