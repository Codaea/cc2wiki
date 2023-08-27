
**Tags:**

# CC2 Lua Functions and Patterns

## Native Functions

These are functions that lua scripts can call to interact with the core C/C++ game process, such as getting the ID or type of the currently controlled vehicle, the angle the current camera is pointing or to issue a production order. Most of these functions are named like `update_*` such as `update_get_camera_heading()`

The functions we know about (because they are in use in the mod dev kit) are recorded [here](https://github.com/cc2modteam/knowledgebase/blob/main/reference/lua/scripts/native_functions.lua) Some of the more commonly used functions and object types are captured below:

### e_active_input = update_get_active_input_type()

```
is_keyboard = update_get_active_input_type() == e_active_input.keyboard
```

Will return the current input mode value as one of `e_active_input`

### string = update_get_loc(e_loc)

```
lang_pause = update_get_loc(e_loc.interaction_pause)
```

Will return the localised string from one of the index values defined in `e_loc`

### Vehicle = update_get_screen_vehicle()

Returns the [Vehicle](https://github.com/cc2modteam/knowledgebase/wiki/Mod-Reference-Lua-Functions#Vehicle) object handle for the vehicle that the screen is attached to.

### update_play_sound(e_audio_effect_type)

```
update_play_sound(e_audio_effect_type.telemetry_2_radar)
```

Will trigger playback of one of the wav clips defined in `e_audio_effect_type`.

Note, this is only provided when you are on-foot. this function is not mapped when you are using an attached vehicle camera.

### update_set_screen_state_exit()

When called, the current screen/camera is exited. Eg, if you are viewing a camera from a vehicle control seat, you are returned to the control screen. If you are on the control screen, you are exited from the screen and remain in the seat.

### Vehicle

Vehicle objects are one of the main ways we can interact with the game engine. They have a number of methods that we can use to find their type, location, speed, health, and loadout configuration etc.

Unfortunately, not all of the scripts are able to access all of the possible vehicle methods. For example, the HUD scripting is unable to read waypoint data from a vehicle.

### ref = v:get()

Appears alot, I am not sure what this does, it may be a form of locking. It seems related to populating the lua object with up-to-date values from the native engine.

The most common pattern is to skip doing something with the vehicle if this returns `nil`. eg:

```
if vehicle:get() == nil or g_is_connected == false then
    update_add_ui_interaction(update_get_loc(e_loc.interaction_cancel), e_game_input.back)
elseif g_is_map_overlay == false then
    update_add_ui_interaction(update_get_loc(e_loc.interaction_exit), e_game_input.back)
end
```

### e_game_object_type = v:get_definition_index()

Returns the [`e_game_object_type`](https://github.com/cc2modteam/knowledgebase/blob/main/reference/lua/scripts/library_enum.lua#:~:text=e_game_object_type) of the vehicle.

### bool = v:get_is_docked()

Returns true if this vehicle is docked.

### bool = v:get_is_visible()

Returns true the vehicle is visible to the current team.

### Position = v:get_position()

Gets the [Position](https://github.com/cc2modteam/knowledgebase/wiki/Mod-Reference-Lua-Functions#Position) object for the vehicle

### int = v:get_waypoint_count()

Get the number of waypoints (does not work in HUD script)

### Waypoint = v:get_waypoint(num)

Get a waypoint (does not work in HUD script)

## Position

Represent a 3d map location.

Note, when obtains from a Vehicle object, x is latitude, y is altitude and z is longitude. Position objects obtained for waypoints on the holomap seem to swap y and z.

### float = p:x()

Gets x as a float

### float = p:z()

Gets y as a float

### float = p:y()

Gets z as a float