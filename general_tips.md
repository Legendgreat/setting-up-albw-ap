# General tips, tricks and guides for ALBW AP

## What is this?

This page is an index of useful tips and tricks, guides and other tools for ALBW randomized with AP. Most of the things here apply to the standalone randomizer as well, and I will specify when it doesn't.

If you came here to troubleshoot your setup, there is a separate guide for that [here](..), this guide is only meant for helping with issues in runs, as well as some links to other guides and tools.

I'm making this guide because a lot of questions get asked very often in the Archipelago Discord, and I feel like a database of general knowledge would be useful for the community.

So, if you are stuck in your run or you wonder if something is or isn't possible, you've come to the right place.

## Links for other guides/tools/apps

##### General links

[Archipelago](https://archipelago.gg)  
[Archipelago Discord](https://discord.gg/8Z65BR2) (You can find the ALBW community under #future-game-design/The Legend of Zelda: A Link Between World)  
[ALBW AP World](https://github.com/randomsalience/albw-archipelago) (made by Caroline or randomsalience)  
[ALBW AP for original 3DS Hardware](https://github.com/LittleCube-hax/albw-ap-plugin) (Made by LittleCube, not as up to date as Caroline's AP World)  
[Standalone ALBW Randomizer](https://github.com/rickfay/z17-randomizer) (RickWithAnH)

##### Trackers

[ALBW AP Tracker](https://github.com/Legendgreat/albw-ap-poptracker) (The only one still being maintained currently for use with Archipelago for auto-tracking, made by me)  
[ALBW Emotracker](https://github.com/rickfay/ALBW-Randomizer-Tracker) (RickWithAnH)

[Crack Tracker](https://firedrox.github.io/albw/?page=portals)

##### Guides

[ALBW trick sheet](https://onedrive.live.com/edit?id=9C1FAD54B68F35F4!3195&resid=9C1FAD54B68F35F4!3195&ithint=file%2Cxlsx&redeem=aHR0cHM6Ly8xZHJ2Lm1zL3gvcyFBdlExajdaVXJSLWNtSHRTVnYyU2hUUTJEZzJ2P2U9T0NST3lo&migratedtospo=true&wdo=2&cid=9c1fad54b68f35f4)  (Repository of ALBW rando tricks/glitches, compiled by Brooty)

## Tips

#### DO NOT TALK TO HINT GHOSTS

In the most recent version of ALBW AP World by randomsalience (v0.1.3), most hint ghosts will have their default text, but some of them will softlock your game. This is due to an update of the standalone randomizer where hint ghosts will give hints about the randomized logic. This only got partially implemented and is currently very buggy. It's recommended to just avoid hint ghosts altogether.

#### Portrait/Pendant locations

Talking to Ravio will reveal the location of all the sage portraits, and Sahasrala in Kakariko Village top right house will reveal the location of all the pendants. Getting all the locations of Portraits can help you plan which dungeons to do based on the items you get. It's a good habit to talk to Ravio right away after starting a new run.

#### Portrait/Pendant requirements

Some checks are locked behind portraits, pendants or other flags. They are as follows:

- Pendant of Courage: This unlocks the Haunted Grove Stump check to the west of Link's House.
- Sage Oren: This lets you get the Queen Oren check in Zora's Domain if you also have Smooth Gem.
- Sage Osfala: This unlocks the last item sold by Ravio.
- Sage Impa: This unlocks the chest in the Throne Room in Hyrule Castle.
- Sage Irene: This lets you run into Irene for the check that normally gives you the bell.
- Sage Rosso: This gets you a couple of checks around Rosso's House to the east of Lost Woods.
- Completing Thieves' Hideout: Regardless of the reward, this unlocks the Thief Girl check north of Swamp Palace.

All other dungeon rewards don't net you a check, besides all Pendants for the Master Sword check, though this is generally not worth going for depending on your settings.

#### Softlock prevention for dungeons

It's recommended to grind 50 rupees at the start to get the scoot fruit from the shop in Kakariko or Lake Hylia. Not only does it give you a check as soon as you get bombs as well (on the north wall of Southern Ruins), but they let you leave dungeons at any time. It can speed up runs if you aren't able to finish a dungeon and have to leave, but more importantly they let you exit a dungeon if you ever get softlocked.

## FAQ

#### Eastern Palace top left blocked switch before Yuga (Normal Logic)

In normal playthroughs, you would lower the barrier around the switch and then hit the switch with an arrow. In randomized logic, you are sometimes expected to hit the switch through the barrier with either bombs or ice rod.

#### How do I get the checks outside of the map in Eastern Palace?

Two of them are along the escape route from the Yuga fight, if you already left the escape route you'll have to go back up to the boss room and start from there. The last one you get from merging in the lobby.

#### Tracker says I should be able to enter Hyrule Castle crack, but I can't cut the curtain

This is a known issue, it is a bug in the randomizer logic. When the curtain got reintroduced in some version of the randomizer, the logic was not updated to account for that. If you have no other checks left, your seed might be unbeatable. That said, Sword, Lamp, Fire Rod, Bombs and Boots are all able to cut the curtains.

#### What are the mirrored settings in Cracksanity, and what does "up crack" and "down crack" mean?

Simply put, any pair of cracks will have the same pair but in the other world. For example, if Link's House crack is paired to Lorule Castle crack, that also means the Vacant House (Link's House in Lorule) is paired to Hyrule Castle crack. L shaped house crack > Hyrule paradox crack would become Sahasrahla house crack > Lorule paradox crack.

Down cracks are simply cracks facing south, and up cracks are cracks facing north. Due to technical limitations, currently it wasn't possible to pair these up, but this is being looked at and might change in a future update.

#### How do I get to the Hinox Cave without flippers?

All you need is Merge. Two screens left of the Hinox Cave, there is a bit of shallow water, if you merge there and then walk right you can reach the other side and get to the cave.

#### Cracks are there in the overworld even though I don't have quake yet

For technical reasons, cracks are placed from the start, but you won't be able to go into them until you get quake. You can safely ignore them, that's not a bug.

#### How do I get the reward for smashing rocks for Rosso?

You have to head out of his house, and smash all the rocks there. As soon as you pick up/smash the last rock, Rosso will come out of his house to invite you back in for the reward.
