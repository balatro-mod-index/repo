## Installation
All files need to be put under a subfolder in Mods/ folder. Like Mods/BetmmaMods/(Betmma_Vouchers, Betmma_Jokers, lovely, ...).

Directly under Mods/ is incorrect: Mods/(Betmma_Vouchers, Betmma_Jokers, lovely, ...)

There will be a hint message in shop if installed incorrectly.
## Discord thread
[Here](https://discord.com/channels/1116389027176787968/1225831216939536394)
## 5 legendary challenges
Adds 5 challenges, each featuring a legendary joker.

## Betmma Jokers
Adds 11 jokers.

## Betmma Vouchers: Adds 58 Vouchers and 24 fusion Vouchers.
Vouchers have rarities. Rarity affects the chance a voucher is added into the random pool. Only vouchers added into the pool can be chosen and appear. For example, if you have redeemed all vouchers but one uncommon, rare or legendary voucher, it still can not appear. Specifically, the chances for uncommon, rare and legendary vouchers to be in the pool are 1/2, 1/4 and 1/20. Vanilla vouchers and vouchers from other mods are considered common.
### Fusion Vouchers
Fusion Vouchers aren't fused by clicking a fusion button. Instead they appear randomly and can be bought regularly only after you have redeemed the required 2 vouchers. (May change in the future)
## Betmma Voucher Pack: Adds 3 Voucher Packs.
- Voucher Pack: redeem 1 of 3 vouchers.
- Uncommon Voucher Pack: redeem 1 of 3 uncommon vouchers.
- Fusion Voucher Pack: redeem 1 of 3 fusion vouchers.

Note that if there aren't enough uncommon or fusion vouchers satisfying their requirements, random normal voucher will fill in.

This structure code is based on [Coupon Book mod](https://github.com/nicholassam6425/balatro-mods/blob/main/balamod/mods/p_coupon_book.lua) which is for Balamod. I ported it into steamodded and added lots of content.

## Better Vouchers This Run UI
Rewrite the Run Info - Vouchers tab to enable it to display dozens of redeemed vouchers.
Cryptid seems to override this tab.

## Betmma Abilities: Adds "Ability" consumable type, 28 abilities and 4 vouchers
Abilities have their unique area. Active abilities can be used infinite times as long as they aren't on cooldown. Passive abilities are like vouchers but can be sold and revert the changes.

## Betmma Spells: Adds 23 "Spell" cards, 1 ability and 2 vouchers
Spell is a new type of card which triggers when certain sequence is completed. The sequence of a spell isn't fixed, instead it's randomly generated when you buy it and after buying it won't change. This is to ensure each suit and rank has the same chance to be used and prevent some suits/ranks become too op. For example before buying Light's sequence displays as "2 different Light suits" and after buying it'll be Heart, Diamond or Diamond, Heart.

How spells trigger: each spell has a count of how much its progress is completed. Take Heart, Diamond as example, upon buying its count is 0, and if you plays a hand of 9H, 8D, 7S, 6H, 5D, when calculating first card, 9H, its count increases as the first element of this sequence is heart and it matches the first card. This also happens for the second card, 8D. After second card is scored, the spell's count reaches 2, meaning its sequence is completed, so you gain +10 Mult and it resets count to 0. Overall this hand triggers the spell 2 times and not 3 (someone may think there are 3 pairs that are 9H-8D, 9H-5D, 6H-5D, and through the analysis above we know 9H-5D is not a pair).

If current card doesn't satisfy current element the progress won't reset. So 9H, 8D, 6H, 7S, 5D still triggers twice as 7S doesn't reset the progress.

The sequence is displayed under the spell after bought, but due to limited space it only display last completed element and next element to complete. e.g. if sequence is 7, 6, 5, then it will display either "7, 6" or "6, 5". The background of completed element is lighter than not completed one.

The element of sequence can be the following: Face cards, Numbered cards, Each suit and Each rank. There is "negative element" which means if the card doesn't match the element the count increases, for example "negative Spade" displays as "not Spade" and Spade icon with red background (normal elements have green background) and increases the count if current scoring card is not Spade.						
To make the system more complex :] and inspired by Doodle God game I set Dark, Light, Fire, Water, Earth and Air to be 6 basic spells, and all other spells should be fused from previous elements. e.g. Dark + Light becomes Shadow. There is a fuse button if you select two spells.						
Currently spells appear in shop and spell pack, and fusion spells only appear if you have fused it during this run.
