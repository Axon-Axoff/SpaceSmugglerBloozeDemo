# Space Smuggler Blooze – Web Demo (3 Levels)

**Space Smuggler Blooze** is a fast-paced, story-driven 2D scrolling arcade space smuggler shooter built in **Godot 4.3**.

You play as a new recruit fresh out of smuggling school taking your first mission from **Captain Zoney Jones**, a double–cigar-smoking cosmic Robin Hood, smuggling back forbidden booze, music, and magic that tyrant **Weener Zood** has stolen from the galaxy. Blast Zoodbots, dodge asteroids, and rack up points and DeZoods while pirate outlaw tunes pump through your space speakers.

This repo hosts the **3-level web demo** and a high-level pitch/roadmap for potential collaborators and investors.

---

## Play the Demo

> **Play in your browser:**  
> https://axon-axoff.github.io/SpaceSmugglerBloozeDemo/

- No install required.
- Runs in modern desktop browsers.
- High scores are saved remotely to a server-side JSON file via a PHP API.

Survive three sectors, blow up everything you see, grab as many dezoods as you can, then go to the last smuggler's den and sign out with score by taking next mission.

---

## Setting & Story (Short Version)

The galaxy once thumped with basslines, synth flurries, and lyrics from superstars like **Unker Nesticle & The Derky Nerple Band**. Partyships rocked, three-eyed jelly squidsicles melted under rainbow nebulae, and space booze flowed freely from the nectar nexus forest moons of Zorkonia.

Then came **Weener Zood** — a tyrannical overlord who taxed and hoarded everything that brought joy. The galaxy’s soundtrack was replaced by Zoodzack monkbots chanting propaganda, and thriving trademarkets decayed into trash-strewn wastelands.

Enter **Captain Zoney Jones** and his hyper-hot-rodded **S.S. Odd Junky**. Zoney and his fellow smugglers slip past Zoodbot patrols, smuggling back contraband booze, banned records, and other wonders to keep hope alive. Every successful run is both a high-score chase and a strike against Zood’s joyless regime.

---

## What’s in This Demo

This is an **early vertical slice** meant to show off core gameplay, tone, and systems.

### Core Gameplay

- **Arcade-style, point-based 2D scrolling shooter**
- Single-player, keyboard or controller
- Focus on:
  - Skillful flying and dodging
  - Target prioritization
  - Route optimization for score, DeZoods, and survival

### Current Content

- **3 Playable Levels**
  - Sector 1–3: Asteroids, drones, missiles, pickups, and an early boss encounter.
  - Distinct spawners for:
	- Asteroids & debris
	- Buzz Saw drones and variants
	- Missiles and launchers
	- Gems and other pickups

- **Player Ships (10 Ships Configured)**
  - Config-driven stats: shields, movement, weapons, and ship-specific modifiers.
  - Ship configs are data-driven for easy expansion.

- **Enemies & Zoodbots**
  - Reusable elements:
	- Asteroids
	- Space debris
	- Enemy missiles
  - Enemy drones:
	- **Buzz Saw Drones**
	- **Ultra Buzz Saw Drones**
	- **Mini Beetle Drones**
	- **Missile Launchers**
  - The full vision includes **16 Zoodbots** (8 ground / 8 air) with unique graphics, weapons, stats, and movement scripts. Several are already designed and partially implemented.

- **Original Music**
  - **8 original songs**, 16 planned for full game (music + lyrics).
  - Demo already features original tracks and pirate-radio-style integration with the world.

---

## Game-Wide Systems (Tech Overview)

Built in **Godot 4.3** with reusable, modular systems:

- **Collision Handler (autoload)**  
  Central universal collision system that:
  - Detects collisions between player, enemies, projectiles, and hazards.
  - Applies damage, triggers hit effects, and handles smart bomb-like events.

- **Game Settings (autoload)**  
  Centralized constants and variables, including:
  - Dev/production toggles
  - Initial session data (score, DeZoods, items, owned ships)
  - Ship config paths and core balancing values

- **Audio Manager (autoload)**  
  Centralized audio routing:
  - Level music
  - Boss music and transitions
  - SFX hooks for collisions, pickups, UI, etc.

- **Player Ship System**  
  - One unified `PlayerShip` script configurable for all 10 ships.
  - Handles movement, thrusters, weapons, damage, shields, and item usage.
  - Tied to data-driven ship configs and session data (mods, items, etc.).

- **Save Manager (autoload)**  
  - Manages session data (score, DeZoods, items, owned ships, progression).
  - Integrates with a **server-side PHP API** (`api_save_scores.php`) to:
	- Save and load high scores from a remote `scores.json`.
	- Keep a centralized scoreboard for the web demo.

- **Sky Manager**  
  - Four-layer parallax background system.
  - Configurable speeds per layer for a sense of depth and motion.
  - Shared across levels for consistency and easy re-theming.

- **Spaceport System**  
  - Script foundation for:
	- Adding ship mods
	- Selling owned ships
	- Buying new ships
  - Tied into DeZoods economy and ship configuration system.

- **HUD System**  
  Displays:
  - Score
  - DeZoods
  - Shield/health
  - Owned ships & active ship
  - Owned items and the currently equipped/activatable item
  - Level time, item timers, and activated item states

- **Options & Gamepad Setup**  
  - Detects controller presence.
  - Allows mapping of core actions (move, fire, use item).
  - Includes music/SFX volume controls.

- **Global Functions (autoload)**  
  - Shared helper functions used across the game.
  - Tasks like applying ship mods, safely looking up the Level core, etc.

- **Level Base System**  
  - A reusable `LevelBase` script that:
	- Spins up the sky manager
	- Spawns the HUD and player ship
	- Starts pickups, gems, and enemy spawners
	- Manages timers and radio alerts
  - Individual levels (e.g. Level 1–3) extend LevelBase or coordinate with it to provide unique spawns and events.

- **High Score System**  
  - Keeps and sorts top scores.
  - Saves and loads from a **server-side JSON file** via PHP.
  - Displays rankings and titles tied to player reputation.

---

## Upcoming Features & Roadmap (High Level)

This demo is intentionally early; many features are planned or partially implemented.

### Level 1–3 Refinements

Planned polish for the first three levels:

- More thorough, entertaining **backstory screen** with improved background art.
- Refinements to:
  - **Smuggler School** intro and name selection.
  - Mission 1–3 pages:
	- Controller-specific prompts
	- Ship selection on mission screen
	- Better backgrounds and UI theming.
- Basic animations:
  - Perspective leaning for player ship when thrusting.
  - Glow indicators before enemies fire.
  - Limb movement for beetle-type enemies and boss (Dung Beetle Bailey).
- Improved item icons and bonus pickups.
- Additional SFX and audio refinements.
- **Oddzone portal** hooks (see below).

### Oddzone Portals

Occasionally, a swirling **Oddzone portal** appears on-screen for a short time. If the player reaches it before it closes, they’re pulled into a bonus dimension run by a one-eyed **Oddtapus** in a top hat and monocle.

- The Oddtapus greets you with unique, quirky lines.
- You can **buy into games of chance** using DeZoods:
  - *Black Jack With Wild Bill Hickok*  
  - *The Longer The Better*  
  - *Get To The Other Side*  
  - *Stop That Rocket*  
  - (Plus additional games in development.)
- The more DeZoods you risk, the higher the potential payout, but each game has a breakeven point and a chance to lose.
- You return to the level where you entered, with:
  - More or fewer DeZoods
  - Possible oddzone-exclusive items.

### Weapon & Item Upgrades

Upcoming:

- **Multiple Guns Bonus**
  - Timed 3-gun spread:
	- Straight forward + 30° up/down.
	- Durations: 15/30/45 seconds.
  - Also obtainable as a purchased, longer-duration item.

- **Backwards Cannon**
  - Fires straight back for 15/30/45 seconds.
  - Collecting another while active can make it **permanent** for that ship.

- **Damage & Speed Boost Items**
  - Items that increase:
	- Weapon damage
	- Projectile speed
  - Various tiers and durations to support build variety.

### Bosses & Planets

- **4 More Planet Bosses + Weener Zood**
  - 3 more major planet bosses.
  - **Davebot Claude Van Damlaw** (Zoodbot Commander and Weener Zood’s right hand).
  - Final fight(s) with **Weener Zood**:
	- Appears on Level 16.
	- If he’s losing, he escapes, unlocking harder versions of Level 16 to see how far skilled players can push.

### ZUES Billboards

- **Zoodbot Unit Enforcement Squad (ZUES)** billboards scroll through the foreground with propaganda messages like:
  > “Read the news, smugglers always lose.”
- Adds flavor, worldbuilding, and visual humor.

### The Backwards Planet (Levels 13–15)

- Special late-game planet where:
  - You fly **right-to-left** instead of left-to-right.
  - You **start** with maximum points/DeZoods and **lose** them for each enemy or object that escapes.
- Includes the infamous **Backwards R**:
  - A negative pickup that **reverses your controls** (up/down & fire/item buttons).
  - Only way to fix it:
	- Hit another Backwards R
	- Or survive to the end of the level.

### Mirror Ship

- Oddzone-exclusive permanent mod:
  - Spawns a **mirror ship** just below your main ship.
  - Has its own HP and can receive bonuses/mods.
  - If your original ship is destroyed, the mirror ship takes over as your main.

### More Zoodbots & Special Events

- **16 total Zoodbots**:
  - 8 ground units (e.g. **Teethbot Nato**, **Mon Steroid** teleporter, **Ram U Roid**).
  - 8 air units (e.g. **Terror Dactroid**, **Flam U Bot**, a dragon-like zoodbot).
- Additional:
  - Rare events
  - Surprise encounters
  - Unique one-off scenarios designed to keep runs feeling fresh and unpredictable.

---

## Status

- **Engine:** Godot 4.3  
- **Platform:** Browser (HTML5/WebAssembly demo), with an eye toward PC and consoles later.
- **Stage:** Early 3-level demo / vertical slice in progress.

This project is actively being developed and expanded. The current demo focuses on demonstrating core gameplay, tone, and technical foundations rather than final polish.

---

## Contact

If you’re interested in:

- Learning more
- Providing feedback
- Discussing funding, collaboration, or publishing

please reach out to:

- **Developer:** David Amlaw (Art, Music, Programming, and Concept) 
- **GitHub:** https://github.com/Axon-Axoff  
- **Website:** https://davidamlaw.com  
