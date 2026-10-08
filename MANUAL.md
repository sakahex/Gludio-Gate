# 📖 Gludio Gate — Step-by-step manual

This guide takes you from a fresh install to a character that levels by itself.
New here? Read the steps **in order** — each one builds on the one before.

> **The one idea to remember:** Adrenaline does the **fighting** (skills, buffs, potions, pick up).
> Gludio Gate decides **where to go and what to buy** — teleport, shops, quests, farm spot — and moves on when the character levels up.

---

## Contents

1. [Before you start](#1-before-you-start)
2. [Install and activate](#2-install-and-activate)
3. [Connect the editor to the game](#3-connect-the-editor-to-the-game)
4. [A tour of the window](#4-a-tour-of-the-window)
5. [Make your first zone](#5-make-your-first-zone)
6. [Build the trip](#6-build-the-trip)
7. [Record routes](#7-record-routes)
8. [Shops](#8-shops)
9. [Quests](#9-quests)
10. [Supplies (potions, soulshots, scrolls)](#10-supplies-potions-soulshots-scrolls)
11. [Check and run](#11-check-and-run)
12. [Settings](#12-settings)
13. [More tools](#13-more-tools)
14. [Tips for a trip that never gets stuck](#14-tips-for-a-trip-that-never-gets-stuck)
15. [Problems and fixes](#15-problems-and-fixes)

---

## 1. Before you start

You need:

- Windows 10 or 11
- **Adrenaline** bot, with a working config for your character (attack, skills, buffs, potions, pick up)
- a Lineage 2 **High Five** server
- a Gludio Gate license key

First make sure your character **fights well in Adrenaline on its own** — stand it in a farm zone and turn the bot on.
Gludio Gate never changes how it fights; it only takes it to the right places.

---

## 2. Install and activate

1. Go to **[Releases](../../releases)** → newest version → download **`GludioGateSetup.exe`**.
2. Run it and pick your **Adrenaline folder** (the one that contains `Scripts`).
   Gludio Gate installs into `Adrenaline\Scripts\Leveling\Gludio Gate`.
3. Start **Gludio Gate** (desktop shortcut).
4. The first time, it shows your **machine code** → click **Copy** → send it to the seller → paste the **license key** you get → **Activate**.

> *"Windows protected your PC"*? Click **More info → Run anyway**.
> One key works on one PC. New PC or Windows reinstall = new machine code = ask for a new key.

After activation the scripts appear next to the program:

| File | What it is |
|---|---|
| `Leveling_1_40.txt` | **the leveling script — the one you run in Adrenaline** |
| `Editor.txt` | connects the editor to the game *without* leveling (for recording routes) |
| `Leveling_1_40.ini` | your zones, shops, routes and settings (saved automatically, never overwritten by updates) |
| `EditorLink.txt`, `SettingsModule.txt`, `PathRecorder.txt` | helpers the scripts need — leave them there |

---

## 3. Connect the editor to the game

The editor talks to the game through a script running in Adrenaline:

1. Log your character in.
2. In Adrenaline, load and start **`Scripts\Leveling\Gludio Gate\Editor.txt`** (only connects) **or** `Leveling_1_40.txt` (connects **and** levels).
3. The top bar of Gludio Gate turns green: **Lv 23 · Target: …** and the character appears in the **Character** row.

Several characters can run at once — each gets its own button in the **Character** row; click one to see its stats.

---

## 4. A tour of the window

**Top bar** — the character's level, its target, what the script is doing right now, and your license.

**Menu row**

| | |
|---|---|
| 📄 **Leveling_1_40 ▾** | the script you're editing: make a new one, open another (also from any folder), rename, delete |
| **Recorder** | advanced route recorder |
| **Game database** | look up items, NPCs, skills and game messages with their ids |
| **Check for updates** | download the newest version |
| ⚙ **Settings** | bot timings, escape scroll, theme, language, folders ([section 12](#12-settings)) |
| **License key… / About** | your key, version and what's new |

**Stats line** — level %, exp/hour, time to next level, adena, deaths, stuck restarts.

**Left side**

- **Zone set** — a separate list of zones for some characters (e.g. one for mages). Most people only use *Main*.
- **Zones** — all your zones, sorted by level. Click one to edit it.
- **▲ Up / ▼ Down** — order of zones that start at the same level.
- **+ Add zone / Delete zone**
- **🧪 Supplies** — one shop for consumables, used at every level ([section 10](#10-supplies-potions-soulshots-scrolls)).
- **✓ Check my setup** — finds anything missing.
- **Zone stats** — exp/hour and deaths per zone, to compare spots.
- **Zone packs** — export / import zones with all their routes.

**Right side** — the selected zone: its name, levels and **the trip**.

Everything saves by itself (top right shows *✓ saved*). Hover any **(?)** for help, click **More ▾** on a card for rarely used options.

---

## 5. Make your first zone

1. Click **+ Add zone → New zone (the next levels)**.
2. Type a **Name** (e.g. *Ant Nest*) and the **Levels**, e.g. **20** to **30**.

**How levels work:** a zone is used **from the first level until the character reaches the second one**.
*20 to 30* = levels 20–29; at level 30 the next zone takes over. (So *5 to 5* would never be used!)

**Several steps for the same levels** — e.g. *shop in Giran*, then *farm at Ant Nest*:
**+ Add zone → Another step for the same levels**. Steps run top to bottom and the bot **farms at the last one**.
The earlier steps are "pass-through" (shopping, gatekeepers…).

> 💡 Zones whose levels overlap but differ (e.g. *Cruma 35–45* and *C-grade shopping 40–45*) are done together;
> a zone without a farm spot (pure shopping) is always done **first**, in town.

---

## 6. Build the trip

The trip is everything the character does to get to its farm spot, **top to bottom**:

```
THE TRIP, IN THIS ORDER                          [+ Add ▾]
 1 TELEPORT   .giran                                    ✕
 2 SHOP       Helvetia                       ▲ ▼        ✕
 3 QUEST      Head for the Hills             ▲ ▼        ✕
 4 GATEKEEPER Bella → Ant Nest               ▲ ▼        ✕
 5 FARM       route + fight zone                        ✕
```

Use **+ Add ▾** to add:

| Choice | What it does |
|---|---|
| **Teleport** | how the trip **starts**: a chat command (`.giran`) or an item (Scroll of Escape). Always first. |
| **Gatekeeper** | talk to an NPC and click its buttons (e.g. *Teleport → Ant Nest*). Its **How** can also be *Chat command* or *Use an item* for a teleport in the middle of the trip. |
| **Shop** | walk to a merchant and buy ([section 8](#8-shops)) |
| **Quest** | a quest done at this point of the trip ([section 9](#9-quests)) |
| **Farm spot** | the route to the spot and the **fight zone** (a `.zmap` from Adrenaline's *Settings* folder). Always last. |

- **▲ ▼** move stops and quests; **✕** removes anything (the teleport too).
- The type label on a card (e.g. **GATEKEEPER ▾**) changes a stop's type.
- **Buttons → Pick…**: talk to the NPC in game, then double-click the buttons in the order you click them.
  The editor clicks them in game too, so you see it work.
- **NPC**: type its name or id, or target it in game and press **◎ Set from my target**.

---

## 7. Record routes

Every stop and the farm spot has a **Route** — the walk from the previous place.

1. Stand where the walk starts (for the first stop: **exactly where the teleport lands — wait a second after landing**).
2. Click **● Record**, walk the way in game, click **■ Stop**.
3. Click **Map** to check or fix it on the real game map:
   drag a dot to move it · click to add a point · right-click a dot to delete · **Draw** to sketch · wheel = zoom · middle-drag = pan.
   The red dot is your character.

**No route needed** — tick it when the NPC stands right where you arrive.

> Map pictures blank? **⚙ Settings → App → Maps folder** and pick Adrenaline's `Maps` folder.

---

## 8. Shops

1. **+ Add → Shop**, set the NPC and its **Route**.
2. **Pick from what <NPC> sells…** — the merchant's full list with grade, type and price. Search, filter, tick items, **Add selected**.
   (Or **+ Add item** and type a name / id.)
3. For each item:
   - **Buy up to** — how many you want to have after shopping.
   - **More ▾**: *when less than* (only buy when you have fewer), *Wear it* (equip after buying), *Go back at* (while farming, go back to buy when you have fewer than this).

Gear is bought once and worn; a shop with nothing to buy is skipped.

---

## 9. Quests

A quest is a list of **steps**, done in order:

| Step | What happens |
|---|---|
| **TALK** | travel to an NPC and click its buttons — accept, deliver, turn in |
| **HUNT** | farm at this zone's farm spot until the character has **N × quest item** |

Typical hunting quest: **Talk** (accept) → **Hunt** 20 claws → **Talk** (turn in).

1. **+ Add → Quest**, type its name.
2. **+ Talk step**: NPC, *Get there* (walk / chat command / item), route, **Pick…** the buttons.
   Quest names in NPC windows show as a number like `[17401]` — that's normal, pick it.
3. **+ Hunt step**: pick the quest item from the quest inventory (have at least one first) and the count.
4. Optional: **quest id** (a quest already taken skips its accept step) and **Repeat when finished**.

- Each character keeps **its own progress** — a restart, death or disconnect continues where it stopped.
- The character **stays in the zone until its quest is done**, even after levelling out of it.
- If a turn-in doesn't take the quest items (wrong buttons), the quest is not counted as done — it retries.

---

## 10. Supplies (potions, soulshots, scrolls)

**🧪 Supplies** (left side) is **one** shop for consumables, used at **every** level:

1. Keep the **Town teleport** (e.g. `.giran`).
2. **+ Add the supplies shop** → NPC (e.g. Helvetia), route, **Pick from what … sells**.
3. Each item:
   - **Buy up to** — e.g. 3000 soulshots.
   - **Go back when less than** — e.g. 300: while farming, below this the character scrolls to town, restocks everything and returns.
   - **Only at levels** — e.g. D-grade soulshots *20 – 40*, C-grade *40 –* (empty = every level).
4. **Sell junk** (same page): items sold at every shop visit, before buying.

---

## 11. Check and run

1. Click **✓ Check my setup** — fix anything it lists (missing routes, buttons, fight zones…). Click a line to jump to it.
2. In Adrenaline start **`Leveling_1_40.txt`** for the character.
3. Watch the top bar: *Lv 23 – step: Giran shopping* → *farming at Ant Nest*.

What the bot does, over and over:

1. picks the zone(s) for its level
2. does the trip: teleport → stops and quests in your order → farm spot
3. turns the bot on and farms
4. goes back when supplies run low, after a death, when stuck, or when a quest's hunt is done
5. moves to the next zone on level up (scrolls to town first)

Class changes are done **by hand**.

---

## 12. Settings

**⚙ Settings → Bot** (saved in the script's ini; defaults are fine for most):

| Setting | Default |
|---|---|
| Stuck check: no exp for X min → escape and redo the trip | on, 10 min |
| A trip went wrong (e.g. gatekeeper didn't teleport): retry after | 30 s |
| Low supplies: finish the fight first, at most | on, 180 s |
| Between two supply runs wait at least | 10 min |
| Before a teleport, wait for the fight to end up to | 60 s |
| Escape scroll | Scroll of Escape (or Adventurer's, or never) |
| Don't use the scroll while in a town / town size | on, 3000 |
| Open the editor when the script starts in Adrenaline | off |

**⚙ Settings → App**: theme, language, Adrenaline folder, Maps folder, check for updates at start.

---

## 13. More tools

- **Several scripts** — 📄 menu → *New script* / *Save as a new script*: e.g. `Mage_1_40.txt` + `.ini`. Load the `.txt` you want in Adrenaline for each character. Copies update automatically with new versions.
- **Zone sets** — the **…** next to *Zone set*: a separate zone list inside one script, chosen per character.
- **Zone packs** — share zones (with routes) as a file: *Zone packs → Export / Import*.
- **Zone stats** — compare exp/hour and deaths of your farm spots.
- **Game database** — find any item / NPC / skill id.

---

## 14. Tips for a trip that never gets stuck

- ✅ **Start every level range with a teleport.** After a death, restock or stuck check the trip restarts from its first step — a teleport makes that a known spot. Later steps of the same levels don't need one.
- ✅ Prefer a **chat command** (`.giran`) for the trip start: same landing spot every time, free. A Scroll of Escape goes to the *nearest* town, which can change.
- ✅ Record each route **from where the previous step really ends**, and wait a second after a teleport before pressing Record.
- ✅ Check zone levels: *from* the first level *until reaching* the second.
- ✅ Run **✓ Check my setup** after every big change.

---

## 15. Problems and fixes

| What you see | What to do |
|---|---|
| **Game not connected** | Start `Leveling_1_40.txt` or `Editor.txt` in Adrenaline (the exe must be in the same folder as the scripts). |
| **trip failed (gatekeeper?), trying again** | The gatekeeper didn't teleport: check its **Buttons** (Pick… again), adena, and that the route ends next to it. |
| **quest step failed** | The quest NPC wasn't found: the step's route must end near it; check the NPC name / id. |
| **could not buy … (adena? wrong Dialog?)** | Not enough adena, or the shop's buttons are wrong (**More → Shop buttons → Pick…**). |
| Character walks into walls after a teleport | The route doesn't start where the teleport lands — re-record it from the landing spot. |
| Uses a scroll and comes back again and again | A supply's *Go back when less than* is higher than *Buy up to*, or the shop can't sell it. |
| Route map shows black squares / nothing | **⚙ Settings → App → Maps folder** → Adrenaline's `Maps`. |
| Something else | Send the red lines and the lines starting with *Quest*, *Shop* or *Gatekeeper* from Adrenaline's log in our Discord. |

💬 **Help, news and zone packs: [our Discord](https://discord.gg/PUMUGWgAkY)**
