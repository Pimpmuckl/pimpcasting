# pimpcasting
Hey folks, 

figured I should at least give rough directions when open sourcing my config. So here it goes, got way too big but there's a lot to talk about, I promise it's #worth.

Introduction and Prep

Before just casually copying this config in your Dota 2 config folder, please make sure that you save the current values for the console variables (convars) which are over ridden by my config. Example:

dota_camera_speed 3000 
is way too slow to play the game with it but really perfect to obs/cast with. So what I would suggest is the following:

Take a look into my pimpcasting.cfg and take note which commands you want to change for playing the game
Save all of these commands in a "playing.cfg", I'll attach my playing.cfg at the end of this post to give you a rough idea
Import my "pimpcasting.cfg" which you use for casting and adjust it to your liking
Adjust your autoexec.cfg and add binds to execute each playing or casting config it could look like this:
//autoexec.cfg example
con_enable 1

bind "F12" "exec playing.cfg"
bind "F11" "exec pimpcasting.cfg"

exec playing.cfg //Change this to pimpcasting.cfg if you mainly cast

echo "autoexec loaded"
If you want to use these binds, make sure to disable the Steam Overlay camera feature as it uses F12 as well. 

So let's do this: Go to

Steam\steamapps\common\dota 2 beta\game\dota\cfg
and adjust the autoexec.cfg, put your playing.cfg in there and paste my pimpcasting.cfg as well. Now open the game and adjust the keybinds in the spectator section:

binds

These are the settings I HEAVILY recommend. The camera movement can be done via WASD, Creep Score is then rebound to F. This way your left hand never needs to move on the keyboard. Huge benefit in usability.

Observing, using the config and the assisted camera

Firstly there is a cool feature made by Valve which is called "Assisted Camera". This is a bit like the directed camera in DotaTV (which doesn't exist when casting from a lobby btw) and follows heroes around without you having to always control it.

Now load into a random game in DotaTV, after you're done loading and after the draft is done, press F11 (or whichever other button you bound the pimpcasting.cfg to". Click on a lane and move to a hero, and press Mouse4 (dota_toggle_assisted_camera_operator). Just leave your mouse and keyboard, don't do anything, you can see how your camera follows the heroes.

To adjust the camera when assisted cam is on, use WASD, middle mouse button doesn't work when it's on.

This feature is absolutely amazing to help you a bit, however I would heavily recommend to NOT use it in teamfights as you as caster/obs will want to have full control over it, and the assisted camera doesn't give you 100% power over what it does. Same goes for framing some laning stage/jungle ganks. 

I made these high quality flow chart as rough idea:

                              Is there a teamfight?
                              /                   \
                             /                     \
                            /                       \
                          No                        Yes
                          |                            \
            Is a lot happening regardless?              \
                /                       \          Turn assisted cam off
               /                         \            Use Mouse 3 drag
              /                           \
             No                           Yes 
             |                             |
   Keep assisted cam on           Turn assisted cam off
     Adjust with WASD                Use Mouse 3 drag



          Do you use WASD to move the camera without using assisted cam?
              /                                            \
             /                                              \
            /                                                \
           No                                                Yes
            |                                                 |
          Correct!                                   Don't. It looks like shit

Smooth drag via Mouse 3 still yields by far the most precise Camera, but it's fine to not use it a lot and abuse assisted camera, especially when casting.

Tips and Tricks

Do you want to click on the minimap AND don't have assisted camera on?

Hold SHIFT until the movement completes, it makes the transition smooth. If there's impending action, don't.

Are you using this config on a LAN setting?

Remove the // characters before "dota_silent_roshan 1". It shuts up roshan and smoke.

Do you want to quickly check if you are lagging on the server?

Press F10, it will toggle the netgraph in the top right. Don't forget to disable it again.

The zoom out per mousewheel-notch is not good!

Adjust these settings:

dota_camera_broadcaster_mousewheel_direction_multiplier 0.0075 
dota_camera_mousewheel_direction_multiplier 0.0075 
I like these personally, but try a couple different ones.

I can't move the camera any more via edge move!?

Don't. Do. It.

Minimap icon sizes are weird.

Adjust these settings:

dota_minimap_hero_size 700
dota_minimap_rune_size 500
Minimap icons get smaller and bigger and I don't like it.

Adjust these settings to disable it or make things larger/smaller.

dota_minimap_hero_scalar 1
dota_minimap_hero_scalar_distance 6
dota_minimap_hero_scalar_minimum 700


FAQ

Will update with your questions here.

Done!

Enjoy your 9k mmr TTours. 

Questions: Via Email or Twitter. 