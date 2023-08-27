
**Tags:**

# Carrier Command 2 Mods

CC2's mod system works by replacing individual files. You cannot enable two mods if they both contain the same file (eg the same lua script, game object mesh, sound or 3d shader etc)

## CC2 Mod Capability

Most mods are concerned with how the various control screens on the carrier work. Some alter the various vehicle HUD camera behaviours.

A not-exhaustive snapshot of some of the things people have managed to mod include:

- Control Screens
    
    - Extra waypoint options
    - Vehicle loadout options/limit (eg, change how hardpoints can be used)
    - Adding extra control screens to the carrier/units
- Vehicle HUD Camera Views
    
    - Show more details about targets in camera views
    - Fuel-remaining timers
    - More target lock options
- Vehicle options
    
    - Add/move unit hardpoints
- Weapon physics
    
    - Naval gunfire spread
    - Missile/Torpedo speeds
- Visuals/Audio
    
    - Skins
    - New 3d models for units
    - New weapon sound effects

## Limitations

Things that we cannot do (yet) that often are requested.

- Change weapon ammo capacity
- Change weapon damage
- Change unit hitpoints/fuel capacity
- Create new units
- Land aircraft on islands / barges / needlefish

Not all screen scripts have access to the same native functions, eg:

|script|enter vehicles|play sounds|
|---|---|---|
|screen_vehicle_control.lua|yes|no|
|screen_radar.lua|no|yes|
|screen_weapons_anti_air.lua|no|yes|
|vehicle_hud.lua|no/sorta|no|