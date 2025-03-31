# UIX

UI Extensions for MM8BDM v6b
by Russel

Addon that implements additional UI elements:
- Enhanced TeamInfo.
- Weapon inventory bar.
- SR50 tailwind.
- Enhanced pickup respawn indicators.

Asset Credits:
- SR50 Tailwind graphics adapted from SRB2.
- Killfeed skull icon edited from Mega Man 2.

Modder notes:
- Currently only works with v6b.
- Due to the way weapons are implemented in v6b, this mod manually has to support mods to work with the weapon bar.
- The following mods are implemented:
  - Armory of Evil (by Ecl1p5e)
  - Mega Man DOS Reborn weapons (by Trill, et al.)
  - Mega Man Rock Force weapons (by Trill, et al.)
  - Megaman Unlimited Weapons (by JaxOf7)
  - Rockman No Constancy weapons (by Trill, et al.)
  - Touhou Koumakyou Weps (2023) (by Xelt)
  - Ukiweps (by Ukiyama)
  - Allanxweps (by Allanxindustries)
  - Item Asylum (by JumboDS64)
  - MM6 Busters (by Trill, adapted by MegaVile)

Please note that some mods not listed above handle UIX support themselves. MegaVile's packs in particular will ship
with the necessary integrations, so they do not need to be implemented directly by UIX itself.

If your mod is not on this list and you want it to be, raise an issue on github.com/russelcs/uix or ping me on discord.
I typically hang out in the MM8BDM unofficial discord (linked from the forums), TSPG discord, or in the Gondola discord.
My name is Russel, or RusselCS. Please describe me with he/him or they/them pronouns.

v1b changelog:
- Added VileWeps, Encore Weps, and MM6 Busters to the supported mods
- UI elements now update the same tick as their data, as opposed to every 0.2 seconds (Thanks Trill!)
- Added limited support for v6a. SR50 and Teaminfo should function properly!
- Teaminfo now works in coop, survival, and invasion.
- Weapon Inventory now pulls second bar colors from scriptedbars.
- Weapon Inventory now properly positions second bars in horizontal orientation.

v1c changelog:
- Updated support for AllanXWeps and VileWeps
- Redid fix: UI elements now update the same tick as their data, as opposed to every 0.2 seconds (Thanks Trill!)
- Added server toggles for all UI elements

v1ch changelog:
- Added support for Experimental_Weapons and BluemanBlaster
- Fixed a typo in VileWeps support script

v1d changelog:
NOTE: VileWeps and encore-weps-v2ah5.pk3 do not have their own integrations. Versions following should contain them.
- Removed VileWeps and Encore from supported mods (they support themselves now!)
- Renamed "ScuttleRun" to "SR50" in the menus because people complained

v2a changelog:
- Replaced font with the one used in Unholy.
- CVars reset to defaults for all users.
--- There reasons for this are many, but the primary ones are simply 
--- (1) folks needed to turn the whole thing off due to bad performance, and
--- (2) the way some of the cvars were handled was inconsistent across widgets
- TeamInfo:
--- Recoded from the ground up.
--- Removed layer health bars.
--- Reworked the widget to be 4 rows of data: Name, Location, Health, Ammo/Lives.
--- Ammo info outsourced to "UIXDB.acs", which can be replaced by other mods for their specific purposes.
--- Removed the directional compass for ally positions. It was too much information to obtain at a glance.
- Weapon Bar: Recoded from the ground up. CPU footprint reduced by roughly 40%.
--- Widget is now more concisely structured, icons are closer together.
--- Each weapon slot's row/column now caps out at 5 weapons (changeable by player).
--- Weapon order scrolls based on which weapon is selected now.
--- Scroll order on the bar now matches the default scroll order for vanilla weapons. (Mod weapons will need to have their include and ACS order synced).
--- Known issue: Due to an inheritance chain in vanilla, Laser Buster and Arrow Buster have to have an inverse order. It looks weird but only affects a cheat scenario.
--- Removed the automated fetching of bar colors from ScriptBars.
----- Previously this method result in bars being colored incorrectly, but this change keeps the weapon bar from stepping on the toes of any actual bar scripts running.
----- ScriptBars can manually define bar colors by inheriting from NormalBar and SecondBar and filling args in as normal.
- SR50 Tailwind: Few smaller changes
--- Now wooshes in the opposite direction (better matching SRB2)
--- Transparency now matches the SR50 user's transparency
--- Now properly disables if user disables all of UI Extensions

v2b changelog:
- Teaminfo:
--- Bars for ammo and health are now thicker
--- Fixed a possible cache miss with location and weapon name that could cause a string table leak
--- Possibly fixed a bug where player names were sometimes not getting properly squished in certain settings
--- Put down some framework to make maths easier for a future change
--- Now shows Objective icons over allied mugshots
--- Now shows "meta status" icons like typing in chat, speaking in voice, or menuing
--- Now shows dead allies, with an animation whenever they die (only with mugshots enabled)
--- Users can now adjust the separation distance between ally pieces.
--- Users can now choose to have their ally info "wrap" after a given number of allies is shown.
- Weapon Bar:
--- Fixed a bug where second ammo bar would not properly display when orientation was horizontal
--- Fixed a bug where second ammo bar would "stick" to the user's UI when the attached weapon was removed
- Item Respawn Timers:
--- Timers exist for 5s, 10s, 15s, 30s, 40s, 60s, and "Unknown."
--- Timers now "round" to the closest time as opposed to assuming unknown when not found.
--- Now "round" to the closest one.
--- Sprites were renamed to indicate how many segments they have so it's known which counter is being looked at.
- Killfeed Mugshots:
--- Background functionality no longer runs for anyone not involved in the frag exchange.
--- Now displays when coop spying those involved in the frag exchange.
- Several background organization changes
--- In SHRTFUNC.acs, removed use of GetNewUIID. Engine now sets the hudmessage IDs on its own.
--- Added an option to select the "layer" the new UI elements are attached to.
