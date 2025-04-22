---
title: "Magic Deck: Ritual of Change"
date: 2025-04-21
tags: ["mtg"]
---

{{% scryfall %}}

I brewed a Historic deck recently that I call *Ritual of Change*. It's a lot of fun to play, and it's taken me to Platinum in Best-of-1 Ranked! In this post, I'll share the decklist and some notes on building/playing the deck.

# The Decklist

```
Creatures (32)
4 Birds of Paradise
4 Burning‑Tree Emissary
2 Charming Prince
4 Fear of Change
4 Prosperous Innkeeper
2 Abhorrent Oculus
4 Extraction Specialist
4 Renegade Rallier
4 Skyclave Apparition

Enchantments (4)
4 Birthing Ritual

Instants (4)
4 Collected Company

Lands (20)
1 Boseiju, Who Endures
2 Botanical Sanctum
2 Breeding Pool
4 Brushland
1 Forest
1 Island
1 Mana Confluence
1 Plains
1 Prismatic Vista
1 Razorverge Thicket
3 Temple Garden
2 Yavimaya Coast
```

# The Design

This deck is originally based on a Pioneer deck by my friend [Josh](https://www.twitch.tv/okothief_of_crowns), but it's gone through several iterations from that starting point. Since I'm playing Historic rather than Pioneer, I have access to a couple of key cards that pushed the deck in a different direction (and gave the deck its name): [[Birthing Ritual]] and [[Fear of Change]].

![[Birthing Ritual]]
Remember [[Birthing Pod]]? It's cheaper and more permissive now, at the cost of only seeing seven cards.

![[Fear of Change]]
For those of you unfamiliar with Arena-only mechanics, the "random creature card" is drawn from Arena's card pool, not just from the deck. That randomness is part of what makes the deck so much fun to play. With [[Fear of Change]], no two games are the same, and I get to play with cards that would be uncompetitive or illegal in the mainboard. It also serves a functional role: by cycling through random creatures, I can dig for {{% /scryfall %}}{{< sidenote "what I need" >}}In one particularly dramatic instance, I was staring down lethal combat damage from Mono-green Elves next turn, when I hit a Platinum Angel my opponent had no way to remove.{{< /sidenote >}}{{% scryfall %}} in a given matchup.

I inherit [[Collected Company]], [[Abhorrent Oculus]], [[Extraction Specialist]], and [[Prosperous Innkeeper]] from Josh's deck, but I dropped [[Warden of the Grove]], [[Tribute to the World Tree]], and [[Tyvar, the Pummeler]], favoring a more toolbox-oriented approach over pure go-wide aggression. In the next section, I'll talk about how that toolbox functions.

The lands are a bit of a hodgepodge, based on what's in my Arena collection; more on that later. The guiding principle is that every land should be able to tap for {G} on turn 1, except for a single basic [[Island]] and [[Plains]] to fetch with [[Prismatic Vista]].

# The Gameplan

The high-level plan of *Ritual of Change* is to get creatures on the board with [[Birthing Ritual]], and to a lesser extent [[Collected Company]]. Apart from [[Collected Company]], the curve tops out at 3, so [[Collected Company]] can hit every creature, and a 2-drop is always a sufficient sacrifice for [[Birthing Ritual]]. Since [[Birthing Ritual]] is such a key piece, the deck wants to get it on the board with a creature to sacrifice as soon as possible. To that end, I include several cheap creatures that provide mana to cast [[Birthing Ritual]], and then act as sacrifice fodder once it's on the field.

Once [[Birthing Ritual]] is in play, it's time to start churning creatures, most of which have ETB effects so that they can serve their purpose without needing to stick around. The creatures with ETB effects are divided into 2-drops and 3-drops. In an ideal scenario, the 2-drops get sacrificed to [[Birthing Ritual]], and the 3-drops get exiled to [[Fear of Change]], but both can serve either purpose in order to flexibly respond to game conditions. 

**Creatures without ETB effects:**
- **[[Birds of Paradise]]** accelerates the gameplan and provides mana consistency, and can be used as fodder later if needed.
- **[[Abhorrent Oculus]]** is simply a huge threat. [[Birthing Ritual]] and [[Collected Company]] both dodge its additional cost, and it can single-handedly run away with a game if unanswered, holding back an aggressive deck or making huge attacks against a slower one. In a pinch, the manifests can also be used as fodder for [[Fear of Change]], although the mana value of zero means they aren't ideal for that.

**2-drops with ETB effects:**
- **[[Fear of Change]]** is the ideal fodder for [[Birthing Ritual]], with triggers both when it enters and when it dies. The random creature card with +2 mana value is mostly used to rapidly scale up to big, impactful creatures, often hitting useful ETB effects along the way, but in a pinch it can also turn a manifest or a [[Birds of Paradise]] into a 2-/3-drop for [[Birthing Ritual]].
- **[[Burning-Tree Emissary]]** can come down on turn 2 and immediately provide mana to cast [[Birthing Ritual]], then be sacrificed for a new creature.
- **[[Prosperous Innkeeper]]** doesn't provide as much mana as [[Burning-Tree Emissary]], needing to be paired with [[Birds of Paradise]] in order to enable a turn-2 [[Birthing Ritual]] that gets a 3-drop. However, the mana can be stored for later, and can fix colors, making it a better ETB later in the game. Also, the life gain as I churn through creatures is very helpful against aggro.
- **[[Charming Prince]]** is mostly good for its ability to blink another creature. As well as re-triggering ETB effects, it can flip a manifested land, [[Birthing Ritual]], or creature with a mana value. Occasionally, the other modes come in handy, to gain life against aggro or dig for what I need after an unfortunate starting hand.

**3-drops with ETB effects:**
- **[[Extraction Specialist]]** serves to resurrect my 2-drops after they've been sacrificed to [[Birthing Ritual]] or put in the graveyard by [[Abhorrent Oculus]]. A common line is to get one into play by sacrificing [[Fear of Change]] to [[Birthing Ritual]], get the [[Fear of Change]] back immediately, and use the [[Fear of Change]] triggers to immediately upgrade to a 7-drop while keeping the [[Fear of Change]] around to do it again next turn. 
- **[[Renegade Rallier]]** has the same role as [[Extraction Specialist]], with the added upside that it can target a [[Birthing Ritual]] or a land. In hand, [[Renegade Rallier]] can be enabled by [[Prismatic Vista]], treasure from [[Prosperous Innkeeper]], the old-fashioned method of losing a creature in combat, or occasionally by [[Charming Prince]]'s blink effect.
- **[[Skyclave Apparition]]** is flexible removal that can answer key threats in most of the matchups I face, and I put enough creatures in play that the token rarely matters.

# Technical Tips

- It's often worth mulliganing down to 5 cards to look for a playable [[Birthing Ritual]].
- Be ready to attack with creatures that are destined to churn into untapped blockers.
- When sacrificing [[Fear of Change]] to get [[Skyclave Apparition]] with [[Birthing Ritual]], order the triggers so that the [[Fear of Change]] trigger exiles the [[Skyclave Apparition]] before the [[Skyclave Apparition]] trigger resolves, so that the opponent doesn't get a token.
- When manifesting dread, it's often a good idea to put 2-mana creatures in the graveyard rather than face-down, to create targets for [[Extraction Specialist]] and [[Renegade Rallier]].
- The optimal timing for [[Collected Company]] is complex. If you need fodder for [[Birthing Ritual]], it can get some before the end step. Otherwise, it's usually best to play after the sacrifice, in case it hits a [[Renegade Rallier]]. Both to enable [[Renegade Rallier]] and because [[Abhorrent Oculus]] triggers on the opponent's upkeep, it's usually not right to play [[Collected Company]] on your opponent's turn, but it can be if you anticipate counter-magic, want to respond to removal (with [[Fear of Change]] or [[Charming Prince]]), or need surprise blockers.

# Future Development

The current decklist is somewhat constrained by my supply of wildcards. There are a few changes I'd try out if I had full access to the card pool, although I can't say for certain whether they'd be improvements before seeing them in action.

**Creature changes:**
- Complete the playset of [[Abhorrent Oculus]]. For this, I'd likely cut 2 [[Renegade Rallier]]s, since they compete to be pulled out of the deck as 3-drops.
- Add [[Fiend Artisan]]. It's another way to tutor creatures out of the deck, including [[Abhorrent Oculus]] without its additional cost. I think I would swap out [[Burning-Tree Emissary]], counting on the strength of [[Fiend Artisan]] to make up for the loss of speed. [[Charming Prince]] could potentially be swapped out instead of the last two, but the increased access to [[Abhorrent Oculus]] makes the blink ability more valuable.

**Land changes:**
- Complete the playset of [[Mana Confluence]]. As well as coming in untapped to provide all three of my colors, it can tap for other colors to activate abilities of random creatures from [[Fear of Change]]. I think I could support the life loss with life gain from [[Prosperous Innkeeper]], but possibly a full playset would be too much.
- Complete the playset of [[Prismatic Vista]], to thin the deck and enable [[Renegade Rallier]]. For this, I'd add 2 [[Forest]]s, for a total of 5 basic lands to fetch.

So with an unlimited supply of wildcards, an idealized decklist might look like:
```
Creatures (32)
4 Birds of Paradise
2 Charming Prince
4 Fear of Change
4 Fiend Artisan
4 Prosperous Innkeeper
4 Abhorrent Oculus
4 Extraction Specialist
2 Renegade Rallier
4 Skyclave Apparition

Enchantments (4)
4 Birthing Ritual

Instants (4)
4 Collected Company

Lands (20)
1 Boseiju, Who Endures
2 Botanical Sanctum
1 Breeding Pool
3 Forest
1 Island
4 Mana Confluence
1 Plains
4 Prismatic Vista
2 Razorverge Thicket
1 Temple Garden
```

{{% /scryfall %}}