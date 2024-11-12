1.26 DayZ Chernarus Fresh Spawn Location Choice Mod  For PC & Console, Changelog & Terms Of Use

Using the new restricted area method, players can can choose where they want to go, after an initial spawn on Skalisky Island.

The system is modular, so Server Owners can choose to have options for coastal, airfield, castle & or military base spawns.

I have included the DayZ Editor PC DayZ Mod File so you can play around with the files. ( CHERN-AIRF-FT-OBJECTS.dze CHERN-COAST-FT-OBJECTS.dze CHERN-MILITARY-FT-OBJECTS.dze chern-ft-castle-objects.dze ).

Limited Testing on PC Chernarus Local Server & Xbox Remote Server Version 1.26 NOV 2024.

Thanks to @King_Alobar_& JinieJ for the idea!

Created by @scalespeeder. Please report bugs & errors to scalespeeder@gmail.com with screenshots.

TERMS OF USE
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS
OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN
AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH
THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Using these modded xml & json files could break the functioning of your DAYZ server, requiring a reinstall that would wipe
all player progress.

Using these modded xml & json  files neccessitates increased regular restarts to prevent server crashing.

It is suggested you thoroughly test your server after applying these files to ensure proper
functioning of your server.

Please note that if the server is full & a log-on queue is in effect, the player will be at the back of that queue.

INSTRUCTIONS

Download these files from my Github or Mega. On github click on the green "Code" button & "download zip". On Mega click on the green "download" button & "download as a zip file".
Save the files in their own folder somewhere easily accesible on your PC.

-----

It's best to download files & edit locally on your PC if you can.

Check all edits with an online XML validator: https://www.xmlvalidation.com/ & for JSON: https://jsonformatter.curiousconcept.com/

STOP YOUR SERVER

-----

Ensure your DayZ Server has activated the cfggameplay.json. For console users on Nitrado Servers, go to "General Settings" on your server and tick "Enable cfggameplay.json" & save.

On PC Servers add or edit the following line to your serverDZ.cfg:

enableCfgGameplayFile = 1;

(On some PC servers, including Nitrado, the serverDZ.cfg is "hidden", so you need to enable "expert mode" in settings,
then go to "expert settings", which is the serverDZ.cfg. Stop the server before making changes this way.)

-----

On console, go to your Nitrado dashboard, then to your server, then to the file-browser, then to the "custom" folder, and upload

chern-coast-ft-objects.json
with
teleport-coast-corner.json
teleport-coast-e.json
teleport-coast-ese.json
teleport-coast-ne.json
teleport-coast-nne.json
teleport-coast-s.json
teleport-coast-se.json
teleport-coast-sw.json

and or

CHERN-AIRF-FT-OBJECTS.json
with
teleport-airfield-balota.json
teleport-airfield-NEAF.json
teleport-airfield-NWAF.json

and or

chern-ft-castle-objects.json
with
teleport-castle-krona.json
teleport-castle-devils.json
teleport-castle-gnomo.json
teleport-castle-black-mountain.json
teleport-castle-rog.json

and or

CHERN-MILITARY-FT-OBJECTS.json
with
teleport-military-tisy.json
teleport-military-kamensk.json
teleport-military-zeleno.json

On PC, create a custom folder inside your mission file, (eg mpmissions\dayzOffline.chernarusplus\custom )then repeat the above uploads.

The  various Objects files are for the fast-travel props on the map.

The teleport json files tell the server where the fast travel points are, and where the player should teleport to.

-----

Next, upload the cfgplayerspawnpoints.xml to your mission folder (eg mpmissions\dayzOffline.chernarusplus ), replacing the original one (change the name of the orginal to cfgplayerspawnpointsBAK.xml first, so you can revert when necessary.)

The cfgplayerspawnpoints file makes sure that all fresh spawns start on Skalisky Island, off the South East Coast of Chernarus.

-----

Next, open your cfggameplay.json file and after

"wetnessWeightModifiers": [1.0, 1.0, 1.33, 1.66, 2.0] add a comma to the end, so it looks like this:

"wetnessWeightModifiers": [1.0, 1.0, 1.33, 1.66, 2.0],

Next we're going to add the relevant teleport file references, depending on which fast travel points you want activated & which files you've uploaded.

for ALL of the fast travel points: 

"playerRestrictedAreaFiles": ["custom/teleport-coast-sw.json","custom/teleport-coast-s.json","custom/teleport-coast-se.json","custom/teleport-coast-corner.json","custom/teleport-coast-ese.json","custom/teleport-coast-e.json","custom/teleport-coast-ne.json","custom/teleport-coast-nne.json",
		"custom/teleport-airfield-balota.json","custom/teleport-airfield-NEAF.json","custom/teleport-airfield-NWAF.json","custom/teleport-castle-krona.json","custom/teleport-castle-devils.json","custom/teleport-castle-gnomo.json","custom/teleport-castle-black-mountain.json","custom/teleport-castle-rog.json",
		"custom/teleport-military-tisy.json","custom/teleport-military-kamensk.json","custom/teleport-military-zeleno.json"]

for just the COASTAL fast travel points:

"playerRestrictedAreaFiles": ["custom/teleport-coast-sw.json","custom/teleport-coast-s.json","custom/teleport-coast-se.json","custom/teleport-coast-corner.json","custom/teleport-coast-ese.json","custom/teleport-coast-e.json","custom/teleport-coast-ne.json","custom/teleport-coast-nne.json"]

for just the AIRFIELD fast travel points:

"playerRestrictedAreaFiles": ["custom/teleport-airfield-balota.json","custom/teleport-airfield-NEAF.json","custom/teleport-airfield-NWAF.json"]

for just the CASTLE fast travel points:

"playerRestrictedAreaFiles": ["custom/teleport-castle-krona.json","custom/teleport-castle-devils.json","custom/teleport-castle-gnomo.json","custom/teleport-castle-black-mountain.json","custom/teleport-castle-rog.json"]

for just the MILITARY fast travel points: 

"playerRestrictedAreaFiles": ["custom/teleport-military-tisy.json","custom/teleport-military-kamensk.json","custom/teleport-military-zeleno.json"]

Or you can customise the fast travel points to your taste and server needs.

We are actually taking advantage of the code designed for the Sakhal Military Bunker, which on Sakhal is used to make sure you don't get stuck in
the bunker if the doors close - the server teleports you to a safe location when you log off & on. We can use this to create our fast travel teleport system.

-----

Next in the cfggameplay.json file look for the "objectSpawnersArr" line.

This is where you choose which fast travel "props" you want on Skalisky to match up with the teleport files.

Edit it to look like this to have all of the props:

	"objectSpawnersArr": ["custom/chern-coast-ft-objects.json","custom/CHERN-AIRF-FT-OBJECTS.json","custom/chern-ft-castle-objects.json","custom/CHERN-MILITARY-FT-OBJECTS.json"],
	
Like this for just coast: 

"objectSpawnersArr": ["custom/chern-coast-ft-objects.json"],

or customise it however you want to match the teleport files you've chosen
	
remember to save and re-upload if you need to.
 	
-----


If you'd like to make the logging off & on process faster for your players, so they can teleport quicker, open your globals.xml file, find the login / logoff timers and edit them
to look like this:

 <var name="TimeLogin" type="0" value="5"/>
 <var name="TimeLogout" type="0" value="5"/>
 
remember to save and re-upload if you need to.
 
-----

Now you can just re-start your server and the fast travel fresh spawn selection mod system will be in place.

Please share the supplied images to show your players where each spawn-choice will take them, 

and you can also direct them towards this instructional video:

https://youtu.be/kJifAGw19OI

Thanks, Rob.
