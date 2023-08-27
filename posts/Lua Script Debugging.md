
**Tags:**

# Debugging CC2 Lua scripts

When a script is running (ie, a screen is powered on or you are viewing a vehicle camera) you can insert `print()` statements into the lua to see what is going on. Normally when you run CC2 any output printed this way cannot be seen.

The easiest method to see this output is to use a console application like Git Bash. Other methods such as running CC2 inside a programming IDE also work and allow you to see this output.

## Developer Mode

When CC2 is launched with the extra `-dev` command-line option it will do some extra things that will help mod developers (and some things that wont help). With `-dev`, CC2 will re-load any local Lua script when it changes. This can be useful for rapid debug changes. If however you edit a game object XML file the game can crash when attempting to reload.

## Using Git Bash for Debug output

Install [Git for Windows](https://gitforwindows.org/)

Once installed, open an explorer window and navigate to your Steam Apps folder (eg "C:\Program Files (x86)\Steam\steamapps\common\Carrier Command 2") right-click on the folder and click "Git Bash Here".

You should then see a black text window and a "prompt" output similar to:

```
inb@DOWNSTAIRS MINGW64 /c/Program Files (x86)/Steam/steamapps/common/Carrier Command 2
$

```

If you type `ls` and hit enter, you should see something similar to this:

```
$ ls
carrier_command.exe*     dedicated_server.exe*  openvr_api.dll*  server_config.xml
carrier_command_vr.exe*  mod_dev_kit/           rom_0/           steam_api.dll*
mods/                    saved_games/           steam_appid.txt
```

From here, you should be able to start CC2 in developer mode and see the output of your `print()` statements: by typing `./carrier_command.exe -dev` and hitting enter. eg:

```
$ ./carrier_command.exe -dev
hello commander
```

## Print and Formatting

Lua's `print()` statement will print a string or number, if you want more complex output, you will need to pass it a formatted string using `string.format()`. eg:

```lua
print(string.format("heading = %d", math.floor(heading_degrees)))
```

Will print output like:

```
heading = 74
```

## Catching Errors

Lua can intercept errors and give you feedback by making use of the `pcall()` function to make "protected calls" that won't crash the script.

`pcall()` works by accepting a single "callable" argument, this can be the name of a function or can be an anonymous function. It returns two (or more) return values.

If the function encountered an error, the first return value will be `false` and the second value will be the error (usually as a string). eg:

```lua
status, err = pcall(function()
    print("hello")
    x = 10 / 0
    print(string.format("x = %d", x))
    end)

if not status then
    print(string.format("error - %s", err))
end
```

The above code fragment should print output like:

```
hello
error - scripts/vehicle_hud.lua:232: bad argument #2 to 'format' (number has no integer representation)
```