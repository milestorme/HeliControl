# 🚁 HeliControl

HeliControl provides full control over Patrol Helicopters and CH47 Chinooks on your Rust server.

This version has been patched for stability, performance, and improved spawn handling, including fixes for CH47 behavior and optimized entity processing.

---

## ✨ Features

- Full control over helicopter & CH47 stats
- Custom spawn timers (heli + CH47)
- Disable vanilla Rust helicopter events
- Improved CH47 stability and spawn logic
- Performance-optimized entity handling
- Custom loot system support
- Cooldown & limit system
- Admin and player command support

---

## ⚠️ Important Behavior Changes (This Version)

- Default Rust heli + CH47 spawns can be fully disabled
- CH47 spawn handling improved to reduce stuck/hover issues
- Safer entity cleanup and tracking
- Optimized OnEntitySpawned performance
- Fixed missing helper methods and compile issues

---

## 📜 Commands

All commands work in chat and console/RCon.

### Core Commands

/callheli
/callch47
/killheli
/killheli forced
/killch47
/killch47 forced
/killgibs
/killnapalm
/strafe
/helidest
/helispawn
/updatehelis
/tpheli
/tpheli ch47
/unlockcrates
/unlockcrates ch47

### Console

callheli pos x y z

---

## ⚙️ Configuration

Location:
/oxide/config/HeliControl.json

### Key Notes

- -1 = use vanilla behavior
- Plugin only modifies behavior when configured
- Default values now reflect a balanced custom setup

---

## 🚁 Spawning System

Disable vanilla events:

"Spawning - Disable Rust's default spawns": true
"Spawning - Disable CH47 default spawns": true

Controlled spawning:

- Helicopter timer: 2–4 hours
- CH47 timer: 2 hours
- Max active patrol helis: 1

✔ Patrol heli + CH47 can run at the same time  
✔ No duplicate vanilla spawns  

---

## 🔧 Default Tweaks (This Version)

- Heli health: 6000
- CH47 health: 4000
- Reduced rocket damage
- Napalm disabled
- Crates unlock after 5 minutes
- Reduced turret damage
- Improved accuracy
- Slower rocket firing

---

## 🔐 Permissions

oxide.grant group <group> <permission>

Core:
helicontrol.callheli
helicontrol.callch47
helicontrol.killheli
helicontrol.killch47
helicontrol.helispawn
helicontrol.strafe
helicontrol.update
helicontrol.destination
helicontrol.admin

Advanced:
helicontrol.ignorecooldowns
helicontrol.ignorelimits
helicontrol.callmultiple
helicontrol.callmultiplech47
helicontrol.dropcrates

---

## ⏱ Cooldowns & Limits

helicontrol.limit.X
helicontrol.cooldown.X

- Limits reset daily
- Cooldowns are time-based

---

## 📦 Custom Loot

/oxide/data/HeliControlData.json

---

## 🔫 Weapon Scaling

/oxide/data/HeliControlWeapons.json

---

## 🛠 Custom Spawn Points

/helispawn add name
/helispawn remove name

---

## 🧪 Developer API

var heli = HeliControl?.Call("callCoordinates", Vector3.Zero);

---

## ⚠️ Notes

- Test on staging before production
- Disable vanilla spawns when using plugin spawning
- Validate configs: https://www.jsonlint.com/

---

## 🧾 Version

1.5.0 (Patched Build)

- Stability improvements
- Performance optimizations
- Spawn system fixes
- CH47 reliability improvements

---

## Credit

- Original plugin by ***Shady***
- Patched version with improvement ***Milestorme*** 
