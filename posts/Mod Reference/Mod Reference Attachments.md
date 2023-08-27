
**Tags:**
# Game Objects - Attachments

See [cc2me/savedata/constants.py#L93](https://github.com/cc2modteam/cc2me/blob/master/cc2me/savedata/constants.py#L93)

## AWACS = 41

Aircraft Radar.

## AirObsCam = 39

## BattleDroids = 100

Mule deployable droid box.

## Bomb0 = 31

## Bomb1 = 32

## Bomb2 = 33

## CIWS = 24

Ground-mounted anti-missile/anti-aircraft defence. Only has 100 shots in it's magazine but is deadly against slow moving aircraft.

When under manual control you can still shoot at ground units with these but they only inflict a very minor amount of damage (a CIWS turret will take nearly 5 minutes of constant fire to kill a Bear)

## ShipCruiseMissile = 28

## ShipCounterMeasure = 76

## ShipFlare = 29

When used by the carrier, consumes regular "flares" from stock to provide illumunation. Unfortunately flares launched this way do not have any impact on incoming heat guided missiles.

## ShipCIWS = 26

CIWS gun for ships, unlike ground CIWS these tend to be mounted on attachments that have movement limits. They can only aim and fire within the allowed arc (see the chassis xml `<attachment>` for carrier and fish)

## ShipCam = 30

This is the observation camera mounted on the carrier. It seems functionally identical to the Observation camera for ground units except it has a physically larger model. With save editing this can be mounted on every other unit and works.

## DriverSeat = 38

Special implicit attachment that all player-drivable units are spawned with in slot 0

## Flares = 43

## FuelTank = 42

Aircraft drop tank. Contains 1000l of fuel.

## Gun100mm = 18

## Gun100mmHeavy = 86

## Gun120mm = 19

## ShipGun160mm = 20

## Gun15mm = 87

Tiny turret, most often seen on 1-shield islands, actually fires 30mm ammo.

Unlike the other turrets you can write lua scripting to equip this on any docked unit regardless of the fact you can't have them in stock. Several mods make use of this to allow these turrets to be equipped on ground units (or the Carrier).

## Gun20mm = 21

Aircraft 20mm gun, very accurate.

## Gun30mm = 17

## Gun40mm = 85

## MissileAA = 36

Single AA missile hardpoint.

## MissileAALauncher = 27

Warship AA missile launcher, sadly only works when mounted on Needlefish, Swordfish or the carrier (and powered on) When mounted on a land turret or ground unit, it never fires.

## MissileIR = 34

## MissileIRLauncher = 25

Re-loadable IR missile launcher (has a magazine for 4 missiles). Often seen on Seals, Walrus and Ground Turrets.

## MissileLaser = 35

Operated similar to the cruise missile except that it is air-launched and has a relatively short range. Deals low damage (2 are required to kill a Seal). The lua scripting hints at different laser codes, which are probably used internally to allow multiple pilots to shoot at different laser targets.

Like the TV missile they trigger automatic flare launchers but are not otherwise impacted by them.

The AI never seems to fire these

## MissileTV = 72

Player controllable guided missile, similar in spirit to the Wire-Guided missile of CC1 or the AGM-65 Maverick missile.

Like other missiles, it triggers flare launchers but is not impacted by them.

The AI never seems to fire these.

## Noisemaker = 73

## ObsCam = 37

## Radar = 81

## Rearm100mm = 93

Resupply box for Mule

## Rearm120mm = 94

Resupply box for Mule

## Rearm20mm = 90

Resupply box for Mule

## Rearm30mm = 91

Resupply box for Mule

## Rearm40mm = 92

Resupply box for Mule

## RearmIR = 96

Resupply box for Mule

## Refuel = 95

Resupply fuel tank for Mule

## RocketPod = 22

Explosive rocket launcher, contains 20 rockets. Lots of fun but can be tricky to aim.

Like missiles, it also triggers flare launchers.

Rockets can sometimes malfunction and veer off target significantly.

CIWS does not seem to try to intercept these, but they may just be too fast.

## SmallCam = 40

## SmokeBomb = 83

## SmokeTrail = 84

## SonicPulse = 82

## Torpedo = 70

## TorpedoCountermesure = 74

## ShipTorpedo = 75

## VirusBot = 23

## Autocannon = 99

The gun used by the combat droid. Very high rate of damage.