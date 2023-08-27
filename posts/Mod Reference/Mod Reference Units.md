
**Tags:**

# Game Objects - Units

See [cc2me/savedata/constants.py#L73](https://github.com/cc2modteam/cc2me/blob/master/cc2me/savedata/constants.py#L73)

## Albatross = 8

Classic fixed-wing aircraft. 4 weapon hardpoints, one aircraft turret mount, and no utility points.

## Barge = 16

Carries cargo and fuel from islands to carriers. Can be driven by humans. Does not seem to consume fuel.

## Bear = 6

Tracked vehicle, can mount 100mm guns and 120mm artillery, has 2 utility points.

## Carrier = 0

The player carrier.

14 x ship hardpoints (ship camera, naval gun, naval ciws, cruise missile, torpedoes, flare launcher etc)

8 x ground unit bays 8 x air unit bays 1 x lifeboat bay

The carrier is special in that air and ground units can be embarked/unloaded. It can also re-supply ships with fuel and ammunition.

## Droid = 97

Combat droids deployed by the MULE

Droids actually have 2x high-repeat 30mm guns that seem to deal MUCH more damage than the 40mm gun.

## Jetty = 64

This is actually called "drydock" in the Lua. It is where your main carrier is launched from when you start a new game. It cannot be destroyed and cannot move.

## Lifeboat = 57

The little orange escape pod on the port side of your Carrier. Through scripting you can deploy it but it cannot (yet) be driven around.

## Manta = 10

Fast jet, 4 weapon hardpoints, 1 aircraft camera, 1 AWACS, 2 utility points.

## Mule = 88

Ground support unit, 6 "special" resupply boxes.

The Mule can re-supply fuel, IR missiles and ammunition to ground units (and ships I think - bredroll) but sadly not aircraft.

## Needlefish = 77

Small warship, very fast, has 2 ship hardpoints. Can be mounted with any other normal weapon through save-editing.

## Petrel = 14

Heavy-lift air transport, 4 wing hardpoints, 1 aircraft camera. Can airlift any ground unit (except turrets, droids or virus bots).

Interesting fact, when carried by a Petrel, a ground unit is invulnerable and uses no fuel.

Through save editing, can be made to carry aircraft or needlefish (though not for long).

## Razorbill = 12

Small agile helo, 2 aircraft weapon points, 2 utility points.

## Seal = 2

Standard light ground unit, 1 turret, 2 utility points

## Swordfish = 79

Large warship, 3 naval hardpoints

## Turret = 59

Buildable ground turret, vanilla game will carry IR missile, CIWS, 30mm, 40mm or 15mm gun. Through save edits and/or XML changes they can carry and use other attachments

## VirusBot = 58

The Boston Dynamics robot dog virus bot - see [Spot](https://www.bostondynamics.com/products/spot)

## Walrus = 4

Standard medium ground unit, 1 turret, 2 utility points, more hitpoints than a walrus