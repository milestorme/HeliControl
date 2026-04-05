# 🚁 HeliControl

Heli Control allows tweaking various settings of helicopters on the server.

---

## 📜 Commands

All commands work in both chat and console/RCon

### Chat & Console Commands

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

### Command Notes

- `/strafe` — Tells the heli to strafe player's position  
- `/helidest` — Tells the heli to fly to a player's position  
- `/helispawn` — Add a custom spawn point  
- `/updatehelis` — Apply config changes (plugin reload still required)  
- `/tpheli` — Teleport under heli (`/tpheli ch47` for CH47)  
- `/unlockcrates` — Unlock heli or CH47 crates  

### Console Command

callheli pos x y z

> Note: `/killheli` will only drop loot if:
> `"Misc - Prevent crates from spawning when forcefully killing helicopter"` = false

---

## ⚙️ Configuration

Located in:
`/oxide/config/HeliControl.json`

- Default config matches vanilla Rust
- Plugin does NOT change behavior unless configured
- `-1` values = use Rust defaults

---

## 🔧 Config Options

### Damage
- Global damage multiplier (default 1.0)

### Gibs
- Health (default 500)
- Harvest delay (default 480 seconds)

### Health
- Base heli health (10000)
- Main rotor (750)
- Tail rotor (375)

### Loot
- Max crates (4)
- Unlock timer (-1)
- Custom loot toggle

### Misc
- Shoot while dying (true)
- Speed (25)
- Startup speed/length
- Lifetime (15 minutes)
- Crate drop toggle on forced kill
- Water to extinguish napalm

### Rockets
- Blunt damage (175)
- Explosion damage (100)
- Radius (6)
- Max rockets (12)
- Fire delay (0.2s)

### Spawning
- Auto spawn timers (heli + CH47)
- Static spawning mode
- Allow multiple active spawns
- Disable heli / gibs / napalm
- Disable vanilla spawns
- Max active helicopters
- Custom spawn points

### Turrets
- Accuracy (2)
- Damage (20)
- Range (300)
- Burst timing + fire rate

---

## 🔐 Permissions

Grant:
`oxide.grant group <group> <permission>`

### Core

helicontrol.callheli  
helicontrol.killheli  
helicontrol.killgibs  
helicontrol.killnapalm  
helicontrol.helispawn  
helicontrol.strafe  
helicontrol.update  
helicontrol.destination  
helicontrol.admin  

### Advanced

helicontrol.dropcrates  
helicontrol.ignorelimits  
helicontrol.ignorecooldowns  
helicontrol.callmultiple  
helicontrol.callmultiplech47  

---

## ⏱ Cooldowns & Limits

Permissions:
- helicontrol.limit.X
- helicontrol.cooldown.X

Rules:
- Limits reset daily
- Cooldowns are time-based
- Can be used independently

---

## 📦 Custom Loot

File:
`/oxide/data/HeliControlData.json`

Example:

```json
{
  "HeliInventoryLists": [
    {
      "lootBoxContents": [
        { "name": "rifle.ak", "amount": 1 },
        { "name": "ammo.rifle.hv", "amount": 128 }
      ]
    }
  ]
}
```

---

## 🔫 Weapon Scaling

File:
`/oxide/data/HeliControlWeapons.json`

Example:

```json
{
  "WeaponList": {
    "Assault Rifle": 1.0,
    "Bolt Action Rifle": 1.0
  }
}
```

---

## 🛠 Spawn System

Add:
`/helispawn add name`

Remove:
`/helispawn remove name`

---

## 🧪 Developer API

```csharp
var heli = HeliControl?.Call("callCoordinates", Vector3.Zero);
```

---

## 🧾 Default Config

See full config in plugin — unchanged from vanilla by default.

---

## ⚠️ Notes

- Always validate JSON: https://www.jsonlint.com/
- Plugin does not change vanilla behavior unless configured
- Test changes before using on live server

## Credit

- ***https://umod.org/user/Shady***
