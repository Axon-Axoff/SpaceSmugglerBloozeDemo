# Space Smuggler Blooze – Pitch Document

## Logline

**Space Smuggler Blooze** is a story-driven, arcade-style 2D space-smuggler shooter built in **Godot 4.3**, where players take missions from a double–cigar-smoking cosmic Robin Hood, smuggling back banned booze, music, and magic from the grip of a joy-killing galactic tyrant.

---

## Vision

The galaxy once thrummed with thumping basslines, action-packed synth flurries, and enlightened lyrics sung by interstellar superstars. Partyships rocked beneath rainbow nebulae, three-eyed jelly squidsicles melted in alien hands, and space booze flowed from the nectar nexus forests of Zorkonia.

Then **Weener Zood** seized power.

By taxing and hoarding every joyful commodity, Zood replaced the galaxy’s soundtrack with the droning chants of Zoodzack monkbots. Thriving trademarkets decayed into filthy wastelands, and citizens were left with rationed joy and state-approved boredom.

**Space Smuggler Blooze** is about fighting back.

Players step into the role of a space smuggler in the fleet of **Captain Zoney Jones**, a legendary smuggler in his hyper-hot-rodded **S.S. Odd Junky**. Alongside an underground network of musicians, oddballs, and fellow smugglers, the player dodges zoodbots, battles oppressive bosses, and runs illegal cargo to keep hope alive.

The game blends:

- The **tight, skillful gameplay** of classic arcade shooters
- The **character-driven humor and worldbuilding** of modern indie hits
- A **music-centered rebellion** where pirate radio, contraband albums, and illegal joy are weapons against tyranny

---

## Core Gameplay

- **Genre:** 2D horizontal scrolling shooter (arcade / score attack)
- **Mode:** Single-player
- **Core Loop:**
  1. Launch a smuggling run on a hostile route.
  2. Dodge asteroids, debris, and enemy fire.
  3. Destroy zoodbots and collect pickups to increase score and DeZoods (currency).
  4. Reach the end-of-level spaceport or boss fight.
  5. Spend rewards on ships, mods, and items to prepare for harder routes.
  6. Compete for high scores and reputation ranks.

- **Key Mechanics:**
  - Tight ship controls with thruster-based movement.
  - Weapons and items with limited timers and smart usage windows.
  - Score chasing and risk–reward decisions:
	- Hug the danger zone for more pickups and kills.
	- Divert to side objectives or Oddzone portals for big gains.
  - Persistent progression through:
	- Ship ownership and customization
	- Modifications
	- Items and one-off bonuses

---

## Characters & IP Highlights

### Captain Zoney Jones

- **Role:** Protagonist, legendary smuggler.
- **Personality:** Bold, witty, and reckless in exactly the way oppressed galaxies need.
- **Visual:** Double cigars, hot-rod ship, a vibe somewhere between space pirate and outlaw trucker.

### Weener Zood

- **Role:** Tyrannical galactic overlord.
- **Motivation:** Total control over joy, music, and magic.
- **Methods:** Uses Zoodbots, propaganda, and monastic drones to enforce his rule.

### Davebot Claude Van Damlaw

- **Role:** Zood’s right hand and top Zoodbot commander.
- **Significance:** The most powerful Zoodbot in the galaxy; late-game boss and recurring threat.

### Unker Nesticle & The Derky Nerple Band

- **Role:** Legendary space musicians and pirate radio heroes.
- **Function in game:**
  - Provide much of the in-game soundtrack.
  - Spread stories of Zoney’s exploits through illegal broadcasts.
  - Distribute contraband **commodities** across the galaxy:
	- **Intergalactic Freedom Phones** (bass player Wynomite “Wobbles” Drifftbottoms)
	- **Hypnoshades** (sax jammer Gnarbax “Saxsack” Nightshades)
	- **Holo-Tunics** (tuba master Sprockets “Boobtube” Fizzler)
	- **Dream Cream** (clarinet sorcerer Zanzo “The Dongle” Boogiemancer)
	- **Solar Powered Batteries** (keytarist Swimjizz “Juice” The Fluxor)

These characters give the game a **distinct universe** ripe for:

- Spin-off stories
- Music releases
- Cross-media potential (comics, animated shorts, etc.)

---

## What the Demo Shows Today

The current **3-level web demo** (playable in browser) focuses on:

### Core Systems

- **Player ship system** with data-driven configs for 10 ships:
  - Shields, movement, weapons, and modifiers.
- **Collision handling** autoload that manages all hit detection and damage logic.
- **Sky manager** with 4-layer parallax scrolling for immersive space backdrops.
- **HUD** showing:
  - Score, DeZoods, shields
  - Ship & item information
  - Timers and active effects
- **Save manager** with:
  - Session data (score, DeZoods, items, ships)
  - Server-side high-score saving via PHP API + `scores.json`.
- **Level base system** that:
  - Spins up sky, HUD, player, timers
  - Orchestrates spawners for enemies, pickups, and gems
  - Handles radio alerts, game over, and transitions.

### Gameplay Preview

- 3 full levels with:
  - Asteroid and debris hazards
  - Multiple drone types (Buzz Saw, Ultra Buzz Saw, Mini Beetle)
  - Missile launchers and varied threat patterns
  - Pickups and gems that hint at the economy system
  - An early boss encounter framework (e.g. Dung Beetle Bailey)

### Audio

- Original music tracked to the game’s lore.
- Pirate-radio flavor through Unker Nesticle & the Derky Nerple Band.

This build demonstrates:

- Fun, functional core gameplay
- A robust code architecture ready to scale content
- A unique tone and world

---

## Roadmap

The roadmap is split into three phases with increasing scope.

### Phase 1 – From Demo to Polished Vertical Slice

**Goals:**

- Refine Levels 1–3 so they feel like a high-quality “first chapter.”
- Polish core UX and visuals.

**Key Tasks:**

- Improved backstory screen and **Smuggler School** intro:
  - Better backgrounds and character art.
  - Clearer control prompts (keyboard & controller).
  - Ship selection integrated into mission start screens.
- Visual polish:
  - Perspective leaning of the player ship when thrusting.
  - Anticipation glows on enemies before firing.
  - Limb and body movement on beetle enemies and Dung Beetle Bailey.
  - Sharper item icons and pickup art.
- Audio polish:
  - Additional SFX
  - Mix/master tweaks
  - Dynamic layering in boss fights where appropriate.
- Stabilize high-scores:
  - Fully robust remote saving/loading
  - Clear feedback on score submission.

**Deliverable:**  
A browser-playable vertical slice that clearly communicates the game’s identity and quality targets.

---

### Phase 2 – Systems Depth & Content Variety

**Goals:**

- Turn the existing architecture into a **robust content engine**.
- Expand progression, items, and replayability.

**Key Features:**

1. **Oddzone Portals & Oddtapus Mini-Games**
   - Occasionally spawn swirling portals that transport players to a surreal Oddzone.
   - Run short, high-stakes minigames:
	 - Black Jack With Wild Bill Hickok  
	 - The Longer The Better  
	 - Get To The Other Side  
	 - Stop That Rocket  
	 - Plus additional designs.
   - Players stake DeZoods for a chance to win more or gain exclusive items.

2. **Weapon & Item Expansion**
   - **Multiple Guns Bonus:** Triple-shot spreads with timed durations; upgradable/purchasable variants.
   - **Backwards Cannon:** Rear-facing shots with stackable or permanent upgrades.
   - **Damage & Speed Boosts:** Temporary and permanent modifiers that change playstyle and ship builds.

3. **Extended Boss & Planet Structure**
   - At least 4 major planet bosses plus:
	 - Davebot Claude Van Damlaw
	 - Weener Zood
   - Every 3rd level is a planet “capstone” with a boss encounter and unique hazards.

4. **ZUES Propaganda Layer**
   - Foreground scrolling billboards with slogans like:
	 - “Read the news, smugglers always lose”
   - Increases world immersion and comedic commentary.

5. **Backwards Planet (Levels 13–15)**
   - Right-to-left scrolling.
   - Start with maximum score/DeZoods and lose them as enemies slip past.
   - Introduces **Backwards R**:
	 - Reverses movement and button controls until cured or level ends.

6. **Mirror Ship**
   - Oddzone-exclusive permanent upgrade.
   - Creates a mirrored partner ship with its own HP and mod slots.
   - Takes over if the main ship is destroyed, enabling daring late-run gambles.

7. **Zoodbots Bestiary**
   - **16 distinct Zoodbots**:
	 - 8 ground units (Teethbot Nato, Mon Steroid, Ram U Roid, etc.)
	 - 8 air units (Terror Dactroid, Flam U Bot, more)
   - All driven by reusable movement and firing-pattern scripts.

**Deliverable:**  
A mid-scope arcade shooter with strong replayability, distinct “world moments,” and plenty of build variety.

---

### Phase 3 – Full Release & Platform Strategy

**Goals:**

- Ship a fully content-rich, commercial-quality game.
- Leverage the IP and music for cross-media opportunities.

**Key Steps:**

- Expand content to 16 levels across multiple planets and sectors.
- Complete roster of Zoodbots, bosses, and unique routes.
- Deepen Smuggler’s Den / spaceport economy:
  - Long-term ship collections
  - Mods, cosmetics, and perks.
- Platform releases:
  - PC (Steam, itch.io) as primary.
  - Maintain web demo as a free on-ramp.
  - Explore console ports (Switch, Xbox, PlayStation) depending on funding and partners.

**Monetization:**

- **Premium title** (one time purchase, no gimmicks).
- Potential DLC:
  - Level expansion pack
  - Ships, items, weapons expansion pack
- Soundtrack / OST releases featuring in-world artists (Unker Nesticle & The Derky Nerple Band).

---

## Why This Project

- **Unique Tone & IP**  
  SSB stands apart from generic space shooters with:
  - A fully realized, humorous sci-fi universe.
  - Memorable character names and concepts.
  - An in-world band and music-driven rebellion.

- **Solid Technical Foundation**  
  Built in **Godot 4.3** with clear separation of concerns:
  - Autoload singletons for core systems.
  - LevelBase framework to rapidly build new stages.
  - Data-driven configs for ships, enemies, and items.

- **Scalable Content Pipeline**  
  The architecture is designed to make:
  - New Zoodbots
  - New weapons/items
  - New levels and bosses  
  relatively affordable in dev time, which is crucial for a small team.

- **Amlaw Brothers**  
  What is an Amlaw brother? Well, let's just see:
  - An overflowing wellspring of creativity.
  - An Amlaw brother never runs out of ideas.
  - Amlaw brothers have completed many interesting projects in art and music.
  - Amlaw brothers also program and want to expand into video games.
  - Nobody knows how they do it, it's like magic.

---

## What We’re Looking For

**Funding & Partnership To:**

- Hire/contract:
  - 2D artists & animators for characters, ships, and environments.
  - QA and possible secondary programmer to accelerate content implementation.
- Polish & extend the current systems into a market-ready release.
- Support marketing:
  - Trailer production
  - Key art and store page assets
  - Influencer and press outreach.

**Stage:**

- Early, but with a playable 3-level demo.
- Core systems are up and running.
- Extensive design work already done for future content (Zoodbots, bosses, Oddzone games, planets, etc.).

---

## Contact

If you’re interested in investing, publishing, or collaborating:

- **Developer:** David Amlaw (Art, Music, Programming, Concept)
- **GitHub:** https://github.com/Axon-Axoff  
- **Website:** https://davidamlaw.com  

An up to date browser-based demo is available and can be shared privately or publicly depending on the conversation.
