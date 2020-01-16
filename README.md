#  Rift Raider

## A rift raid team go/no go calculator for Summoners War.

I was fascinated by fast rift conquest teams in the game Summoners War, specifically the ones where weak monsters are used to conquer some of the more difficult content in the game.

Some of the emergent effects of (ally) monster skills in the game have interesting side effects, and this is inspired by the Baleygr-Janssen Rift 5 team, commonly called BJR5. Credit to かにちゃんねる for [making the first video about the concept](https://www.youtube.com/watch?v=AI2tQlicMRU) (in Japanese) and an [additional summary video (in English) here](https://www.youtube.com/watch?v=bxpKJXpXtSg).

Essentially, your team consists of six members, moving in this order:

1. A monster with a good attack buff, e.g., [Colleen (Fire Harpu)](https://summonerswar.fandom.com/wiki/Harpu_(Fire)_-_Colleen).
2. A monster with a good defense break, e.g., [Loren (Light Cow Girl)](https://summonerswar.fandom.com/wiki/Cow_Girl_(Light)_-_Loren).
3. [Baleygr (Fire Lightning Emperor)](https://summonerswar.fandom.com/wiki/Lightning_Emperor_(Fire)_-_Baleygr), who is strong AF (default 5*, Fire Lightning Emperor), who nukes the boss. Boss then jumps.
4. [Dagora (Water Warbear)]()https://summonerswar.fandom.com/wiki/Warbear_(Water)_-_Dagora, who is one of the sacrificial monsters, along with Colleen (or other #1 monster) and the leader.
5. [Janssen (Dark Viking)](https://summonerswar.fandom.com/wiki/Viking_(Dark)_-_Janssen), who is generally considered a weak monster (default 2*). However, he has a useful skill: revival, and his revival comes with increasing all allies' attack speed and attack bar for 2 turns, and it scales based on the number of allies revived. It's the last part that makes this work.
6. A monster with a good leader skill who never needs to take a turn, e.g., [Hwa (Fire Rakshasa)](https://summonerswar.fandom.com/wiki/Rakshasa_(Fire)_-_Hwa).

When the raid boss gets to half strength, he jumps, doing a lot of damage. The three cannon fodder must then all die in the same turn to trigger Janssen's third skill enough to buff Baleygr enough to one-shot the boss.

There are spreadsheets. There are graphics. [There are reddit posts](https://www.reddit.com/r/summonerswar/comments/du5zj9/bjr5_supplemental_guide_squishy_baleslorens_and_6/) There's a discord server.

What there hasn't been is a simple app. So here we are.

Please hold, this will take me a few minutes. ;)

## Database Tables

This uses some database tables from [Swarfarm](https://github.com/PeteAndersen/swarfarm) to calculate raid mechanics. There are 101 (!) tables in the default setup of that app, but I've only imported the ones that aren't swarfarm-specific.

### General Info

1. BestiaryBuilding: these are the buildings that affect combat.
2. BestiaryLeaderskill: leader skills.
3. BestiaryMonster: this is the monster definitions (not the instances of the monsters we have).
4. BestiaryMonsterSkills: …and the skills they have, a many-to-many join table.
5. BestiarySkill: the skill list that the many-to-many joins to.
6. BestiarySkillScalingStats: …and how much they bump up with each skillup.
7. BestiarySkillSkillEffect: join table from skills to skill effects.
8. BestiarySkilleffect: the skill effects.
9. BestiarySkilleffectdetail: detail about said effects.
10. BestiaryHomunculousskill: Homunculus has skills.
11. BestiaryHomunculousskillMonster
12. BestiaryHomunculousskillPrerequisite
13. BestiaryHomunculousskillcraftcost

Not needed for this app, but included because I'm likely to use the data model elsewhere and might as well just do the work now:

1. BestiaryCraftmaterial: what you make stuff out of.
2. BestiaryCraftmaterialSource: and where you get said stuff from.
3. BestiaryDungeon: some of the places to get things from (e.g., Giants, essence dungeons).
4. BestiaryFusion: how to fuse one monster.
5. BestiaryFusionIngredients: …and what you need in order to do so.
6. BestiaryGameitem: Crystals, essences, $€.


### Specific to the Player

1. HerdersBuildinginstance:
2. HerdersMonsterinstance:
3. HerdersMonsterpiece: not-yet-assembled summons
4. HerdersRuneinstance:
5. HerdersStorage: how much essence, etc. we have
6. HerdersSummoner: the summoner is the player
7. HerdersTeam: a specific team
8. HerdersTeamRoster: members of that team
9. HerdersTeamgroup: what groups of teams they have, e.g., raid 5 teams

## Tables to figure out

* Guild buffs as there are no guild tables per se.

## data_Log tables

Haven't decided whether or not to add the necessary ones, but I may need to.

# TODO: finish table list.


## Credits
