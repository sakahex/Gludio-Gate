# Gludio Gate

**Build your own automatic leveling for the Adrenaline bot (Lineage 2 High Five) — for any levels you want.**

Gludio Gate is a leveling script maker: you set up the zones and trips once, for as many levels as you like
(1–20, 1–40, 40–76, all the way up...), and your character levels by itself:
it teleports to town, buys gear, soulshots and potions, walks to the right farm spot for its level,
turns the bot on, and moves on to the next zone when the character levels up.

No scripting needed — everything is set up with clicks, and recorded in game.

Fighting, skills, buffs, potions and pick-up stay in Adrenaline's own settings —
Gludio Gate handles **where to go and what to buy**.

💬 **[Join our Discord](https://discord.gg/PUMUGWgAkY)** for help, news and zone packs.

---

## 🆕 What's new in 1.0.14

A clearer top bar:
- **Coloured dot** — green when the game is connected, red when it isn't. You can see the status at a glance.
- **Short status text** — the long explanation pops up when you hover over it, so nothing gets cut off.
- **Script status in colour:**
  - grey **■ Leveling script off**
  - green **▶ …** while it's running
  - red if the script has gone quiet for more than 2 minutes
- **Discord and GitHub icons** — one click opens our Discord server or GitHub page.
- **License warning** — the license text turns red when 7 days or fewer are left.

---

## ✨ Features

### 🗺️ Leveling trips by level
- **Zones for any levels** — e.g. *Lv 1–5 Starting zone*, *Lv 5–20 Outside Gludio*, *Lv 20–40 Ant Nest*,
  *Lv 40–52 ...* — add as many zones as you need, up to 100.
- **Multi-step trips** — several steps for the same levels (e.g. *buy D-grade armor in Giran* → *farm at Ant Nest*).
  The bot farms at the last step.
- **Automatic zone change** — when the character reaches the next level range, it travels to the next zone on its own.
- **Fight zone per zone** — loads the Adrenaline zone file (`.zmap`) for each farm spot.

### 🚀 Teleports
- **Town teleport** by chat command (e.g. `.gludio`) or by item (e.g. *Scroll of Escape*).
- **Gatekeepers** — picks the teleport buttons for you (e.g. *Gludio Gatekeeper → Ant Nest*).
- Waits until the character is out of combat before teleporting.

### 🛒 Shopping & restocking
- **Buy at any NPC** on the way: weapons, armor, jewelry, soulshots, potions, scrolls.
- **Smart buying** — *buy up to 1000, but only when you have less than 200.*
- **Wear it** — new gear is equipped right after buying.
- **Shopping is skipped** when there is nothing to buy.
- **Automatic restock** — when soulshots or potions run low while farming (*go back at 100*),
  the character leaves, buys more and comes back.

### 🎥 Route recording
- Press **● Record**, walk the way in game, press **Stop** — done. One route per stop and to the farm spot.
- **▶ Test walk** to check a route.
- **Set from my target** — target an NPC in game and add it with one click.

### 📊 Stats per character
A live line for each character:

`Lv 20 34.1% · 64.1k exp/h · next level in 1h 55m · adena 15,230 (+2,230) · deaths 1 · stuck 0 · running 1h 00m`

### 🛡️ Stuck check
No experience for 10 minutes while farming (stuck on a wall, no mobs, bot stopped...)?
The character escapes and does the trip again. Minutes adjustable, can be turned off.

### ✅ Check my setup
One click lists everything that's missing or wrong in your zones — routes not recorded, buttons not picked,
missing fight zone files, levels that overlap or aren't covered, items not found, and more.
Click a zone name to jump straight to it.

### 📦 Zone packs
- **Export** your zones (with routes, stops and shopping lists) to a file.
- **Import** zone packs — add them to your zones or replace the ones for the same levels.

### 👥 Several characters at once
Run the leveling script on several characters from the same folder. Each one gets its own button,
status and stats in the editor.

### 🖥️ Modern, simple editor
- Clean **dark interface**.
- Each zone shows the trip **in order**: teleport → gatekeeper → shops → farm spot.
- Rare settings are tucked away under **More**; hover **(?)** for help.
- Everything **saves by itself**.

### 🔄 Automatic updates
Gludio Gate checks for new versions when it starts. Click **Yes** — it updates itself and restarts in seconds.
Your settings are never overwritten.

---

## 💻 Requirements

- Windows 10 or 11
- Adrenaline bot
- A Lineage 2 **High Five** server
- A license key (see *Activation*)

---

## 📥 Download & install

1. Open **[Releases](../../releases)** (right side of this page) → newest version → download **`GludioGateSetup.exe`**.
2. Run it and select your **Adrenaline folder** (the folder that contains `Scripts`).
3. Gludio Gate is installed into `Adrenaline\Scripts\Leveling\Gludio Gate`, with a desktop and Start menu shortcut.

> Windows may show *"Windows protected your PC"* — click **More info → Run anyway**.
> This happens because the program is new, not because it is harmful.

**Uninstall:** Windows Settings → Apps → Gludio Gate. Your settings file stays, so nothing is lost if you install again.

---

## 🔑 Activation

1. On first start Gludio Gate shows your **machine code** (like `ABCD-EFGH-IJKL-MNOP`) — click **Copy**.
2. Send it to the developer (the person who sent you this link).
3. Paste the **license key** you get and click **Activate**.

After activation, Gludio Gate puts the Adrenaline scripts into its folder.

---

## ▶️ Quick start

1. Log in your character and set up fighting / buffs / potions in **Adrenaline** as usual.
2. In Adrenaline, run **`Scripts\Leveling\Gludio Gate\Leveling_1_40.txt`**.
3. Open **Gludio Gate** — the dot in the top bar turns **green** and shows your character's level.
4. Click **+ Add zone**, set its levels, and build the trip:
   - **Teleport** — chat command or item
   - **+ Add stop** — shops and gatekeepers on the way
   - **Farm spot** — record the route and pick the fight zone
5. Press **✓ Check my setup** — fix anything it lists.
6. Done — the script follows your trips from now on.

**Tip:** got a zone pack? Use **Zone packs → Import zones** and you're ready in seconds.

---

## 🔄 Updates

When a new version is out, Gludio Gate asks *"Version X is out — Update now?"* on start.
Click **Yes** — it updates and restarts. After an update, **restart `Leveling_1_40.txt` in Adrenaline**
so it loads the new script.

You can also check by hand: click the version text in the top bar → **Check for updates**.

---

## 🔐 Your license

- One key works on **one PC**.
- Reinstalled Windows or changed PC? Your machine code changes — send the new one to the developer for a new key.
- Timed keys: the top bar shows when your key ends. To renew, click the version text → **Enter a new key...**

---

## ❓ Problems?

| Message / problem | What to do |
|---|---|
| *This license key is for another PC* | The key was made for another machine code. Send the code shown on **this** PC. |
| *This license expired* | Get a new key from the developer. |
| *Game not connected* | Run `Leveling_1_40.txt` (or `Editor.txt`) in Adrenaline **from the Gludio Gate folder**. |
| Stats line stays empty | Restart `Leveling_1_40.txt` in Adrenaline (needed after an update). |
| Antivirus blocks the program | Add an exception for the Gludio Gate folder, then install again. |
| Something else | Send the developer the red lines from Adrenaline's log, or ask on **[Discord](https://discord.gg/PUMUGWgAkY)**. |

---

## 📌 Good to know

- Class changes are done by hand.
- Gludio Gate only moves the character — fighting is Adrenaline's job, so set up your fight config there.

---

**Licenses and help:** contact the developer who sent you the link to this page, or join our
**[Discord](https://discord.gg/PUMUGWgAkY)**.
