# Components
---
## Field (Play area)
- [Monster Zones](#mzones)
- [Support Zone](#szone)
- [Deck](#deck)
- [Grave](#grave)
- [Void](#void)\
Each player will have these zones:
![Field zone layout](images/field.png)\
### <a id="mzones"></a>Monster Zone
### <a id="szone">Support Zone
### <a id="deck">Deck
#### Gameplay Purpose:
The deck stores the players cards that they will use in that game. They draw cards at the start of the turn and can sometimes draw additional cards during the course of the game or search the entire deck for a card with specific criteria. Cards may also be returned to the deck also. If a player runs out of cards in the deck they cannot draw at the start of their turn. The deck size is between 45-60 cards, with a maximum of 3 copies of each card allowed.
Decks are private knowledge and can't be looked at by either player unless stated by a card effect.
#### Implementation
The deck object should contain an array of 'card' objects in order of the last shuffle. This is so cards may reveal a certain number of cards from the top/bottom, put cards at the top/bottom in any order due to their effect. Variables should include a 'deck size' that stores the original number of cards in the deck, a 'current deck size' for how many cards are left and an 'is empty' variable for if the deck is empty.
#### Methods & Functions
##### draw(int amount)
Add the top X number of card(s) (first value in the 'cards' array) to the players hand.\
amount = int that determines how many card objects are accessed from the start of the 'cards' array
##### revealTop(int amount)
Access the top X number of card(s) and display them to both players.\
amount = int that determines how many card objects are accessed from the start of the 'cards' array
##### search()
### <a id="grave">Grave
### <a id="mvoid">Void
