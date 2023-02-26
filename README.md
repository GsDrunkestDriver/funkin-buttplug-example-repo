# Funkin' Buttplug Example Repo
This repo contains a build of Forever Engine with [buttplug support](https://github.com/GsDrunkestDriver/funkin-buttplug) fully implemented!

See it in action here:
[![See it in action](https://img.youtube.com/vi/HTzAlFNEVOY/default.jpg)](https://www.youtube.com/watch?v=HTzAlFNEVOY)

***

## Dependencies
The dependencies to use buttplug support are the same as the main repo, but I'll copy them here for convenience.

* [ToyWebBridge](https://github.com/kyrahabattoir/ToyWebBridge) - Don't forget to replace start.bat and appsettings.json with the ones in [this repo!](https://github.com/GsDrunkestDriver/funkin-buttplug)
* [Intiface Central](https://intiface.com/central/)

Keep in mind that both of these programs need to be running before you start up your mod!

***

## Useful Locations

### PlayState.hx
This file is where the the calls to generate and send the payload are made. It is also where the calls to stop the vibration are made.
* Line 156 - `public var bpPayload:String = "";` - This string holds the payload that gets sent to the frontend. It is generated on line 1395.
* Line 1395 - `bpPayload = ButtplugUtils.createPayload(Conductor.crochet);` - This line generates the payload using the crochet of the song to determine the length of the vibration.
* Line 1478 - `ButtplugUtils.sendPayload(bpPayload);` - This line sends the payload to the frontend every beatHit().
* Line 1553 - `ButtplugUtils.stop();` - This line stops the vibration when the song ends.

### ButtplugUtils.hx
This file handles all of the buttplug stuff. It is a bit messy, but it works. Check out the main repo for more info!

### Init.hx
This file is where the buttplug server is initialised.
* Line 222 - `ButtplugUtils.set_intensity(100);` - This line sets the intensity of the vibration. It is a value between 0 and 100. 100 is just a placeholder value, and should be changed to whatever you want. Maybe consider making it a setting in the options menu?
* Line 223 - `ButtplugUtils.initialise();` - This line initialises the buttplug server.

***

## Issues
Got a problem? Open an issue and I'll try to help you out! Don't forget to make sure that your issue hasn't already been reported!

***

## Credits


* [GsDrunkestDriver](https://github.com/GsDrunkestDriver) - Main developer of Funkin' Buttplug

* [Funkin' Buttplug Contributors](https://github.com/GsDrunkestDriver/funkin-buttplug/graphs/contributors) - Cool people who helped out with the development of Funkin' Buttplug

* [Forever Engine Team](https://github.com/BeastlyGabi/Forever-Engine-Archive/tree/legacy) - Cool people who made the engine that this mod is based on, check out the full credits on the archived repo!

* [Funkin' Crew](https://github.com/FunkinCrew) - Cool as fuck people who made the OG game!
