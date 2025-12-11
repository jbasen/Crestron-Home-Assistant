# Crestron-Home-Assistant
Driver to integrate a Home Assistant (HA) system with a Crestron system so the devices 
and services connected to the HA system can be leveraged in the Crestron system.

This driver is designed to allow a Crestron programmer to leverage HA as a gateway to 
the off-the-shelf smart home devices and services that can be integrated with HA 
without having to become an expert in HA.  No knowlege of YAML is required.  The 
code is designed to work with individual entities in HA.  For example, a power 
monitoring smart plug could have a switch entity for controlling the plug and a
sensor entity for providing the measured power consumed by the device plugged 
into the smart plug.  This paradigm provides both power and flexibility in 
working with smart home devices and services integrated with HA.

IMPORTANT NOTE: This driver only works with a Crestron 4-Series processor.

This module suite is released as shareware.  It is free for a developer to 
use on their own personal Crestron system or for a dealer to use in their 
showroom demo system.  However, if it is used on customer systems, where a 
dealer or programer will profit from it, then I ask for a single payment 
of $150 from the dealer or programmer.  

What you get is 

1) My thanks
2) Permission for the dealer or programmer to use the module on as many 
client projects as they want
3) A copy of the C# source code for the module (only a binary executable 
is included with the example program)
4) Good Karma

Payment information is in the help for the modules

Information for Using the modules is included in the module help.
You will need:
1) The IP address of your HA system.  It should be a static IP or have a DHCP reservation
so it doesn't change
2) An HA access token.  To create a long lived token go to http://homeassistant:8123/profile/security,
click on the security tab, scroll down to Long-lived access tokens, create a token, copy
it to the clipboard, and paste it into the parameter field of the comm manager module in
SimplWindows.
3) HA entity IDs for the devices/services integrated with your HA system.  These can be found at
Developer Tools->States in the HA web interface or HA app. This will be entered into the parameter
fields of the Crestron modules.

If you have a problem and want to open an issue.  Please do the following:
1) On the comm manager module set the Startup_Debug_Msg_Output parameter to "Console".
This will send debugging information to the Toolbox console.
2) Enter the entity ID of of the device/service you are having problems with in the parameter
field Startup_Debug_Entity_ID.  This will limit the messages displayed to just those for this
device/service.  This will greatly help in being able to just see relevant debugging messages
for the device/service you are having problmes with if you have setup other modules to control
other devices you have connected to your HA system.
4) You will need to use both toolbox debugger and open a text console window in toolbox.  The code
will generate a good deal of debugging messages.  These should be visible in the debugger but
unfortunately it has a bad habit of losing messages. However, the text console window is very good
at capturing all the messages.
5) Perform the necessary actions using SimplDebugger to duplicate the problem you are having
6) Please then copy what has been displayed in the text console window and paste it into the GitHub
issue (please copy and paste the actual text. Don't send a screenshot)
The above will make it much easier for me to help you.

NOTE: I would like to add support for smart humidifiers, water heaters, and sirens that are connected
to HA.  However, I don't personally have any of these devices to test with.  If you have one, or
more, of these devices and don't mind spending some time working with me and testing code, please
let me know.  You can send me an email at the address in the module help. Thanks

Releases:

v1.42 - Fixed bug in Sonos module where pausing one player would pause all players in a system

v1.41 - Fixed bug in climate module that made it impossible to set HVAC modes for a subset of
        thermostats

v1.4 - Added support for lights that are only on/off, brightness adjust, or color temp adjustable

v1.3 - Fixed an JSON parsing exception when a Meross thermostat passed the current humidity as a 
double and not as an integer

v1.2 - Added support for triggering HA scenes

v1.1 - 
1. Added support for fans that don't support presets and whose speed can only be set by a %
2. Misc. internal code improvements

v1.01 - 	
1. Changed processor type in demo program to make it easier to load to any 4-series processor
2. Reduced signal traffic on feedback signals from modules - Alarm Control Panel, Analog Sensor, 
   Climate, Cover, Enum Sensor, Fan, Input Number Helper, Lawn Mower, Light, Select, Sonos, and Vacuum
3. Fixed multiple issues with the Climate module.  One fix required changing temperatures from temperatures 
   in tenths of degrees to temperatures in degrees.  One, un-needed output was also removed from the module.  
   Also added missing support for swing mode and swing horizontal modes.
4. Minor other bug fixes

v1 - Initial Release - NOTE - For some reason the .lpz file in the zip file was triggering Windows
Defender to report that there was a virus.  I have removed the lpz file from the zip to eliminate 
this false report.
