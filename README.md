# Startpage

Based off of https://github.com/Jaredk3nt/homepage

## Screenshots

- Default
![startpage_d](https://waifupaste.moe/raw/cle.png)

- Darkmode
![startpage_b](https://waifupaste.moe/raw/0N.png)

## Seting it up 

### On Firefox

- Go to "about:preferences#home" (Options in top right menu > home), set "Homepage and new windows" to
Custom URLs and enter "file:///path/to/the/index.html"

- Set "New tabs" to "Blank Page" then go to the installation folder of Firefox,
"C:\Program Files\Mozilla Firefox" is default on Windows, open "defaults" then "pref" and create 
"autoconfig.js" file and paste this in to it
`//Make FF load "autoconfig.cfg"
pref("general.config.filename", "autoconfig.cfg");
pref("general.config.obscure_value", 0);
pref("general.config.sandbox_enabled", false);`
- Go back to the installation folder and crate "autoconfig.cfg" file and paste this in to it
`//Make FF open local file in new tab
var {classes:Cc,interfaces:Ci,utils:Cu} = Components;
var newTabURL = "file:///path/to/the/index.html";
aboutNewTabService = Cc["@mozilla.org/browser/aboutnewtab-service;1"].getService(Ci.nsIAboutNewTabService);
aboutNewTabService.newTabURL = newTabURL;`
