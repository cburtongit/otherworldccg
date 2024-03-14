# Card Components
## Card
- [Card Info](#cardinfo)
    - [Monster Card](#monscardimg)
- [Card Object](#cardobject)
- [Monster Card](#monscard)
    - [Token](#tokencard)
- [Support Card](#suppcard)

## Card Info<a id="cardinfo"></a>
Each card has a series of properties or 'stats' that affect it. These are the properties that are shared between both `Monster` and `Support` cards:
1. Name - The printed name of the card.
2. Alignments - A series of values that denote which series/archetype the cards belong too e.g. `Fire` | `Warrior` | `Magic`
3. RP Value - RP (Resource Points) are paid to play the card.
4. Effect text - This is the box under the artwork that determines what kind of effect/restriction a card has or can simply be a non-gameplay string of lore. Example: `(When this card is destroyed in combat) Draw 1 card.`
5. Card artwork - This a purely aesthetic component that shows what the card looks like.
6. Set ID, Serial Number & Copyright text - Not used in the sim.  

##### Monster Cards
- Monster cards have the <b>SP</b> (Strength Points) property as well, located at the bottom of the card in <i>red</i>. This defines the strength of a monster and is used in combat 
- Here is an example of a <b>Monster</b> card:
![Field zone layout](images/Test-DarkProwler.png)

##### Support Cards
- Support cards function like quick abilities, settings \& arenas or equipments and do not do combat. They can almost always be played on an opponent's turn using their unique field: <b>FastRP</b>, located at the top right opposite regular <b>RP</b>.
- Here is an example of a <b>Monster</b> card:
![Field zone layout](images/Test-Reincarnation.png)

## Card Object<a id="cardobject"></a>
The main 'card' class object will be what Monster & Support cards inherit from.
Cards should possess the following\:
- static int cardID - a numerical identifier unique to each card.
- str cardName - the name of the card as shown at the top.
- str[] alignments - an array of strings that list the alignments of the card. We can check a card is part of an alignment by searching for the string in the array.
- int RP - the RP value required to play it.
- obj cardSprite - an object that houses the image for the card. Most likely using a godot component.
- static obj owner - store the player who owns the card
- obj controller - store the player who is currently controlling the card (some cards have effects that let another player take control of a card)
- some form of script storer that stores the script for a card's effect

Cards will have the following methods\:
- destroy() - send itself to the Grave. will access it's owner.grave obj
- sacrifice(bool isVoided) - sends itself to the Grave (if isVoided is false) or the Void (if true)
- gotoVoid() - sends itself to the void.
