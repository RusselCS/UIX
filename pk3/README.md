# UIX

UI Extensions for MM8BDM v6b
(now with limited v6a support!)
by Russel

Addon that implements additional UI elements:
- Enhanced TeamInfo.
- Weapon inventory bar.
- SR50 tailwind.
- Enhanced pickup respawn indicators.

Asset Credits:
- SR50 Tailwind graphics adapted from SRB2.

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

FAQs:
- Can you draw ammo on the teaminfo? (more specifically, "can you draw healer ammo on the team display?")
--- No. Or rather, not in a way that keeps this mod as generally applicable as possible.
--- The infrastructure isn't yet there to facilitate something like this. Maybe in the future.
