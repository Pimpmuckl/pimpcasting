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

dota_minimap_hero_size 1100
dota_minimap_rune_size 1000
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

Files



playing.cfg:

dota_camera_accelerate 22
dota_camera_speed 6000
dota_minimap_always_draw_hero_icons 1
dota_minimap_hero_size 1000
dota_minimap_rune_size 1000
fps_max 0
net_graph 1
fog_override 0
dota_minimap_hero_scalar 1
dota_minimap_hero_scalar_distance 20
dota_minimap_hero_scalar_minimum 600
dota_camera_edgemove 1

alias "+camhold" "dota_camera_lock 1"
alias "-camhold" "dota_camera_lock 0"
bind SPACE "+camhold"

bind "MOUSE4" "+voicerecord"

dota_hud_netgraph 1

echo "Executed playing.cfg"
pimpcasting.cfg

//Casting/Obs config file 0.2.1 (2016.04.16) by Jonathan "PimpmuckL" Liebig
//Any questions, please use pimpmuckl [at] gmail [dot] com or https://twitter.com/PimpmuckL
//Please make sure you read the readme.txt first before executing it


//////////////////////////////////////////////////
//             Camera section                   //
//////////////////////////////////////////////////

//Camera speed
dota_camera_accelerate 5
dota_camera_speed 3000

//Stops zooming in again (was cheat protected at one point)
dota_camera_zoom_return_to_default_time 0

//Zoom out distances for each "notch", might want to adjust the "*_direction_multiplier" values
dota_camera_broadcaster_mousewheel_direction_multiplier 0.0075 
dota_camera_broadcaster_mousewheel_frametime_multiplier 3
dota_camera_mousewheel_direction_multiplier 0.0075 
dota_camera_mousewheel_delay_reset_interval 0
dota_camera_mousewheel_start_delay 0.1

//No zoom in
dota_camera_disable_yaw 1

//Disable edge moving, don't ever use it
dota_camera_edgemove 0

//////////////////////////////////////////////////
//             Minimap section                  //
//////////////////////////////////////////////////


//Minimap Icons, adjust these to your liking
dota_minimap_always_draw_hero_icons 0
dota_minimap_hero_size 1100
dota_minimap_rune_size 1000

//Scaling on minimap, adjust this to your liking or set to 0 if you dislike it
dota_minimap_hero_scalar 1
dota_minimap_hero_scalar_distance 6
dota_minimap_hero_scalar_minimum 700

//fps max only needed when running 1pc setup
fps_max 60

//////////////////////////////////////////////////
//             Cosmetic section                 //
//////////////////////////////////////////////////

//Only works in DotaTV for now
sv_cheats 1

//Gets rid of nasty view distance issues when using showcase view (some are cheat protected)
fog_override 1
fog_end 100000
dota_camera_zfar_zoomed_out 10000
dota_camera_hero_inspector_zfar_max 50000
dota_camera_hero_inspector_fog_end_max 100000

//Nicer fight recap w/o tread switching and co
dota_fight_recap_terse 1

//If you want more control over how much is shown in the fight recap, use this, untested
//dota_fight_recap_ability_level 0

//Mutes ping (currently cheat protected)
snd_setmixer ping vol 0.1

//Disables the netgraph in the top right
dota_hud_netgraph 0

//Shuts up roshan, use it when doing a live event. Mutes smoke and roshan sounds.
//dota_silent_roshan 1

//////////////////////////////////////////////////
//            Keybind section                   //
//////////////////////////////////////////////////

//Assist bind holding shift
alias "+assisted" "dota_toggle_assisted_camera_operator"
alias "-assisted" "dota_toggle_assisted_camera_operator"
bind shift "+assisted"

//Assist toggle pressing mouse 4
bind "MOUSE4" "dota_toggle_assisted_camera_operator"
dota_combatlog_file "testcombat.txt"

//Toggle openmic on and off
bind CAPSLOCK "mic_toggle"

//Quick toggle to check for server lag
bind "F10" "custom_toggle_netgraph"

//This is a fix to the issue with foreign keyboards and wrong binds, DON'T use it if you don't have issues
//unbind "Z"
//bind "Z" "stat_dropdown networth"


echo "Executed pimpcasting.cfg"