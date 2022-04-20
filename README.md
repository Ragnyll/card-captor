# Card-Captor
A framework for playing networked card games.

Card-Captor is a framework loosely based off an [ECS](https://en.wikipedia.org/wiki/Entity_component_system) for the delta events that make up a card game.
 It utilizes TCP as the communication protocol for sending these events around to the clients involved in the game.

## Current State
Currently Card-Captor is in it's early development stages.
 All components are either hypothetical or in their initial development.
 The planned order of development is `NGS` -> `Client-Core` -> `RE2` -> `Anything else`.

## Components
Card-Captor utilizes a multiple components for handling the different responsibilities of the game.
- NGS: The network game server used for sending messages between clients and RE2.
- RE2: The rules executor engine.
 The crate defines traits all card games must implement in order to be evaluated in the RE2 Service.
 The RE2 service validates rules for the associated card game and sends them back to NGS to communicate to the clients
- Client-Core: The code required to communicate with NGS using individual entity deltas.
- Hallway: A database to map clients to the room with their desired opponent across potentially many NGS Instances. ('Pie In The Sky' idea)

## Contributing:
If the feature or bug applies to a specific component, log the issue to the correct submodule.
 If the issue concerns standing up the ecosystem or architecture level logic than log it to the `card-captor` repo.
