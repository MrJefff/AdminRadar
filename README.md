**Admin Radar** draws on your screen the locations of players with their current health and distance from you, among many other entity types listed below. A quick toggle GUI is available to quickly change your filters.

**Player Movement Tracker** (default: disabled) tracks all player movement which can be redrawn on screen by using /radar tracker

## Dependencies
### Optional

- [AdminPanel](https://umod.org/plugins/adminpanel)

## Chat Commands
- **/radar** optional: filter -- Allows you to toggle radar on your self with optional filter
- **/radar online** -- Toggles showing online players boxes only when using the box filter.
- **/radar help** -- Shows a list of commands
- **/radar f** -- Use your previous filters
- **/radar ui** -- Turn quick toggle UI on/off
- **/radar tracker** -- Draw on your screen the movement of nearby players. Must be enabled in the config.
- **/radar vision** -- Toggles showing what players are looking at.
- **/radar ext** -- Toggles showing extended information for players (some attachments are shortened. e.g 4x Zoom Scope = 4x, Simple Handmade Sight = Sight)
- **/radar drops** -- Show all dropped items within 150m, including beartraps and landmines
- **/radar list** -- Show all active radar users

## Radar Filters
**Players, Bradleys and Helicopters are shown by default**
- **Bag** -- Show sleeping bags
- **Box** -- Show storage containers, and supply drops
- **Col** -- Show collectibles
- **Dead** -- Show dead players
- **Loot** -- Show loot containers, dropped loot, trash, and backpacks
- **NPC** -- Show animals, Human NPCs, and Scientists
- **Ore** -- Show resource nodes for stone, metal, sulfur
- **Sleeper** -- Show sleeping players
- **Stash** -- Show stashes
- **TC** -- Show tool cupboards
- **Turret** -- Show turrets

- **All** -- Show all of the filters above.

## Configuration
```json
Settings:

- Default Distance -> 500.0 (meters)
- Default Refresh Time -> 5.0 (seconds)
- Latency Cap In Milliseconds (0 = no cap) -> 1000.0
- Objects Drawn Limit (0 = unlimited) -> 250
- Restrict Access To Steam64 IDs -> not configured (only users in this list will have access if configured, otherwise auth level will be required)
- Restrict Access To Auth Level -> Auth Level 1
- Chat Command -> radar (Alternate command to /radar)

Options:

- Show Barrels And Crate Contents -> false
- Show Airdrop Contents -> false
- Show Stash Contents -> false
- Draw Empty Containers -> true
- Show Resource Amounts -> true

Bradley's:

- Track Bradley APC -> true

Drawing Methods:

- Draw Arrows On Players -> false
- Draw Boxes -> false
- Draw Text -> true

Drawing Distances:

- Animals -> 200 meters
- Sleeping Bags -> 250 meters
- Boxes -> 100 meters
- Collectibles -> 100 meters
- Player Corpses -> 200 meters
- Players -> 500 meters
- Loot Containers -> 150 meters
- Resources (Ore) -> 200 meters
- Stashes -> 200 meters
- Tool Cupboards -> 100 meters
- Turrets -> 100 meters

Group Limit:

- Draw Distant Players With X -> true
- Height Offset [0.0 = disabled] -> 0.0
- Limit -> 4
- Range -> 50.0

Helicopters:

- Track Helicopters -> true
- Show Rotors Health -> false

Player Movement Tracker:

- Enabled -> false
- Update Tracker Every X Seconds -> 1
Positions Expire After X Seconds -> 600
- Max Reporting Distance -> 200 meters
- Draw Time -> 60 seconds
- Overlap Reduction Distance -> 5 meters

Color-Hex Codes:

- Color hex codes must start with # symbol. Any code not starting with # symbol will be considered a colored word: red, orange, white, etc...

GUI:

- Anchor Min > 0.667 0.020
- Anchor Max > 0.810 0.148
```

## Compatibility
**FauxAdmin**
Compatibility for FauxAdmin users. These users MUST have **1)** `fauxadmin.allowed` permission, **2)** `adminradar.allowed` permission, and **3)** the admin flag provided by FauxAdmin.
The permission `adminradar.allowed` by itself will not grant ddraw without the admin flag due to limitations implemented by Facepunch
If using the Restrict Access to Steam64 IDs option then your FauxAdmin user must also be in this list or they will not be allowed to use the radar command.
Dropped item tracker will track dropped items in the world with the exception of items in the config (default exceptions: bottle, planner, rock, torch, can., arrow.)

## API
```csharp
bool isRadar = (bool)(AdminRadar?.Call("IsRadar", player.UserIDString) ?? false);
```

## Credits
- [Reneb](https://oxidemod.org/members/20031/) For the original version of AdminRadar
- [Speedy2M](https://oxidemod.org/members/57653/) For being an amazing Co-Developer and Logo Artist!
- [nivex](https://oxidemod.org/members/62685/) For donating his custom AdminRadar for us to study!
- [Austinv900](https://oxidemod.org/members/31950/) For passing the plugin onto me!
