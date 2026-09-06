# BELTLANDS

### Game Design Document v1.0

---

## 1. Title Ideas

**Primary: BELTLANDS** — "Build. Supply. Conquer."

The word does triple duty: conveyor belts, industrial belts of territory, and the belt of land players fight over. Short, ownable, searchable, and it reads well on a thumbnail.

Alternates, by tone:

| Title | Tone | Notes |
|---|---|---|
| SMOKESTACK STATE | Industrial-political | Emphasizes nation-building |
| ORE & ORDER | Punchy, wordplay | Good for a younger audience |
| THE LONG SUPPLY | Strategic, serious | Emphasizes the war layer |
| CRUCIBLE COUNTY | Regional, cozy-industrial | Good if the world is one shared county |
| MAGNATE | Tycoon-forward | Generic but clear |
| HOLDFAST INDUSTRIES | Corporate-military | Good faction-name energy |
| RUSTLINE | Terse, moody | Fits a darker art direction |
| FOUNDRY WARS | Blunt, PvP-forward | Sets expectations toward combat |

Internal codename for development: `BELTLANDS`. Company/faction entities in-game are called **Charters**, which gives you a second brand surface ("Charter Wars", "Charter Season 3") without renaming the game.

---

## 2. One-Paragraph Pitch

**BELTLANDS** is a persistent multiplayer industrial strategy game where you turn a muddy starter plot and a handful of Scrip into a continent-spanning industrial empire. You lay conveyor belts, dig ore, smelt, press, assemble, and ship — but unlike a solo factory game, everything you produce flows into a living player-driven economy where cities have real demand, prices sag when everyone floods the same market, and the fastest route to wealth is usually another player who needs what you make. As you grow, you claim outposts across biomes, string freight lines between them, and discover that your empire is not a fortress but a **network** — and networks can be cut. Warfare in BELTLANDS is not about deleting someone's base; it is about severing their supply, seizing the rich seams they depend on, and forcing them to the negotiating table while their furnaces cool. Your home foundry can never be destroyed, wars are declared with posted bonds and preparation windows, and new players are shielded by law and by design — so the game stays a contest of **industry and logistics**, not a contest of who logged in first.

---

## 3. Core Gameplay Loop

BELTLANDS runs four nested loops. Each one feeds the next, and each has a satisfying completion point so a player can always stop at a clean beat.

**The 30-second loop — Fix the flow.**
Look at your factory. Something is starved, something is backed up. Place a belt, add a second smelter, split a line, run a power cable. Watch throughput tick up in the readout. This is the tactile core.

**The 15-minute loop — Fill the contract.**
Take a contract from a city or a player. It demands a rate (e.g. 20 Steel Plate/min for 40 minutes) rather than a lump sum. Retool a section of your factory to hit the rate, hold it, collect the payout and reputation. Contracts are the metronome of a session.

**The multi-session loop — Unlock and expand.**
Spend Scrip and Research Data on the tech tree. Unlock a better machine, see it visibly replace the old one, redesign a wing of your factory around it. Bank enough for a Deed, survey a new region, plant an outpost, run a freight line home.

**The seasonal loop — Compete for the map.**
Join or found a Charter. Supply cities to raise your Influence. Contest Rich Seams in neutral land. Declare, fight, and settle wars over the strategic sites that make your production cheaper. Season ends, standings are recorded, the map partially resets while your tech and cosmetics persist.

**Why it works:** the short loop is fiddly and instantly rewarding, the medium loop gives clear goals with an end, the long loop gives identity ("I'm the steel guy"), and the seasonal loop gives the whole server a shared story with a scheduled ending — which is also the primary anti-snowball device.

---

## 4. First 30 Minutes of Gameplay

The onboarding never uses a modal tutorial wall. It uses a single NPC, **Foreman Vess**, who gives one job at a time and shuts up once you're competent.

**0:00–0:03 — Arrival.**
You spawn in the **Starter Vale**, a permanently protected valley. You own a 24×24 plot, §2,500 Scrip, a hand-crank generator, and one Prospector's Pick. Vess says: "There's ironstone in that outcrop. Dig it."
You click the outcrop and manually mine. Ore appears in your pockets. It is slow and slightly boring — intentionally, for about 45 seconds.

**0:03–0:06 — First automation.**
Vess: "Never do that twice." You place a **Hand Drill (§200)** on the outcrop. It produces 6 Ironstone/min into its internal buffer. You place a **Crate** next to it and one belt segment between them. The first time ore moves down a belt on its own, the game plays a small chime and the camera nudges in. This is the hook moment and it must land inside six minutes.

**0:06–0:11 — First conversion and first money.**
You unlock the **Bloom Smelter (§350)**: 12 Ironstone + 6 Coal → 6 Iron Ingot/min. You get free starter Coal from a surface seam. You build a **Loading Dock (§150)**, belt ingots into it, and the dock auto-sells to the Vale market at §1.20/ingot. Money starts ticking in real time. Vess: "Now you're a business."

**0:11–0:17 — The first bottleneck, taught deliberately.**
You add a second smelter. It doesn't run. The **Power Readout** in the corner turns amber: demand exceeds supply. You build a **Coal Boiler (§400)** and route a power pole. Lights come on. Lesson delivered: *power is a resource with a chain, not a checkbox.*

**0:17–0:23 — First contract.**
The city of **Kettleford** posts a starter contract: 6 Iron Ingot/min for 10 minutes → §900 + 40 Reputation. You accept, watch the fulfillment bar hold steady, and get paid a visible premium over raw market selling. Lesson delivered: *contracts beat spot-selling.*

**0:23–0:27 — First tech.**
The contract awards your first **Research Data**. You open the tech tree, which is presented as a wall map with six colored branches, and unlock **Powered Drills** — 3x faster, needs power. You replace the hand drill. The model visibly changes from a wooden frame to a steel rig. Lesson delivered: *tech visibly changes the world, not just a number.*

**0:27–0:30 — The horizon.**
Vess opens the **World Map** for the first time. You see the whole continent: eight sectors, other players' territories glowing with their Charter colors, a live ticker of what cities are paying, and a locked marker on a **Rich Seam** two regions north. Vess: "Everything past the Vale is up for grabs. You'll want a Deed. Come back when you've got §25,000."

At minute 30, the player has: a working automated line, income, a contract completed, one tech unlocked, and a named long-term goal.

---

## 5. Factory-Building System

**Grid and freedom.** Factories are built on a 1m tile grid with free rotation in 90° steps. There is no forced layout, no pre-set slots, no "buy the next dropper" rail. Two players with identical tech can build wildly different factories, and the game rewards good design with real throughput differences of 2–3x.

**The five design pressures.** Good factory design in BELTLANDS is the intersection of:

1. **Throughput** — belts have a units/min cap (Tier 1: 15/min, Tier 2: 45/min, Tier 3: 120/min, Tier 4 tube: 400/min). Exceeding it backs the line up.
2. **Power** — every machine draws kW. The grid browns out if demand exceeds supply, dropping *all* machines to partial speed rather than shutting the factory off, so failure is visible but not catastrophic.
3. **Space** — plots are finite. Expanding your plot costs Scrip and eventually requires adjacent land nobody else has claimed.
4. **Haze** — smokestacks emit Haze, which accumulates locally. High Haze reduces worker output and drops nearby land value. Filters, electric processes, and green power mitigate it. This gives a real reason to eventually move dirty industry to remote outposts.
5. **Labor** — machines need staffed shifts. Workers need Housing, wages, and reasonable commute distance from their bunkhouse.

**Ratio play, made legible.** Hover any machine and a **Flow Lens** overlay renders the whole factory as a flow graph with per-line rates, coloring starved lines blue and backed-up lines red. Newer players fix problems visually; veterans use the numeric panel and plan exact ratios. This single tool is the difference between "confusing" and "deep."

**Blueprints.** Select a region, save it as a Blueprint with its full recipe configuration. Blueprints can be stamped down for the cost of materials, shared by code, sold on the market, and posted publicly. This creates a whole social meta-layer (people become famous for their "Vess-Standard 4:3 Steel Block") and dramatically softens the late-game tedium of rebuilding.

**Why it's fun.** The factory is a machine the player authored. Every improvement is legible — you *see* the belt stop backing up. It's the same satisfaction as tidying a desk, except the desk pays you.

---

## 6. Building and Component List

All costs in Scrip (§). Tiers map to tech progression.

### Extraction
| Building | Tier | Cost | Function |
|---|---|---|---|
| Hand Drill | 1 | 200 | 6 ore/min, unpowered |
| Powered Drill | 2 | 900 | 18 ore/min, 15 kW |
| Deep Bore | 3 | 6,500 | 60 ore/min, reaches Deep Veins, 90 kW |
| Strip Excavator | 4 | 28,000 | 180 ore/min, heavy Haze, 300 kW |
| Water Intake | 1 | 300 | Pumps water from rivers/lakes |
| Oil Derrick | 3 | 9,000 | Crude oil from seeps |
| Deep Sea Rig | 5 | 120,000 | Offshore oil, coastal outposts only |
| Quarry Cutter | 2 | 1,400 | Limestone, sand, granite |
| Timber Yard | 1 | 450 | Logs from forest tiles |

### Smelting and Refining
| Building | Tier | Cost | Function |
|---|---|---|---|
| Bloom Smelter | 1 | 350 | Ore + coal → ingots, slow |
| Blast Furnace | 2 | 2,200 | High-rate ingots, needs coke |
| Arc Furnace | 3 | 11,000 | Electric, no Haze, alloy-capable |
| Coke Oven | 2 | 800 | Coal → coke + coal gas |
| Kiln | 2 | 700 | Limestone → lime; sand → glass |
| Refinery Tower | 3 | 14,000 | Crude → fuel, lubricant, naphtha |
| Cracker | 4 | 32,000 | Naphtha → plastic pellet, synth rubber |
| Electrolysis Hall | 4 | 40,000 | Bauxite → aluminum; water → hydrogen |
| Alloy Crucible | 5 | 90,000 | Superalloy, exotic composites |

### Manufacturing
| Building | Tier | Cost | Function |
|---|---|---|---|
| Workbench | 1 | 250 | Manual crafting, 1 recipe |
| Press | 2 | 1,100 | Ingot → plate, sheet |
| Lathe | 2 | 1,300 | Ingot → rod, gear, pipe |
| Wire Mill | 2 | 1,200 | Copper → wire, cable |
| Assembler Mk1 | 2 | 2,800 | 2-input recipes |
| Assembler Mk2 | 3 | 12,000 | 4-input recipes, 2x rate |
| Assembler Mk3 | 4 | 45,000 | 6-input, modular slots |
| Circuit Works | 3 | 16,000 | Boards, processors |
| Chem Vat | 3 | 10,000 | Acids, propellant, fertilizer |
| Vehicle Hall | 4 | 60,000 | Trucks, rail stock, hulls |
| Arms Plant | 4 | 55,000 | Ammunition, weapon kits, armor |
| Aerospace Bay | 5 | 200,000 | Aircraft, satellite parts, drones |
| Nanofab | 5 | 350,000 | Autonomy cores, guidance systems |

### Power
| Building | Tier | Cost | Output |
|---|---|---|---|
| Hand Crank | 0 | 0 | 2 kW, requires a worker |
| Coal Boiler | 1 | 400 | 40 kW, Haze |
| Steam Turbine Hall | 2 | 3,500 | 200 kW, needs water + coal |
| Gas Turbine | 3 | 15,000 | 500 kW, burns fuel, low Haze |
| Hydro Dam | 3 | 45,000 | 800 kW, river tiles only |
| Wind Array | 3 | 9,000 | 90 kW avg, variable by biome |
| Solar Field | 4 | 20,000 | 150 kW, daytime only, no Haze |
| Fission Plant | 5 | 250,000 | 4,000 kW, needs fuel rods + coolant |
| Fusion Core | 6 | 900,000 | 15,000 kW, endgame |
| Capacitor Bank | 2 | 2,000 | Buffers grid, prevents brownouts |
| Substation | 2 | 1,500 | Extends grid range, reduces line loss |

### Logistics (Intra-base)
| Component | Tier | Cost | Rate |
|---|---|---|---|
| Belt Mk1–4 | 1–4 | 8–90/seg | 15 / 45 / 120 / 400 per min |
| Splitter / Merger | 1 | 60 | Even, ratio, or priority modes |
| Filter Gate | 2 | 180 | Routes by item type |
| Underground Belt | 2 | 140/seg | Crossings |
| Pipe Mk1–3 | 2–4 | 20–150/seg | Fluids and gases |
| Pump / Valve | 2 | 250 | Pressure, one-way flow |
| Crate / Silo / Vault | 1–4 | 100–9,000 | 200 / 5k / 50k unit storage |
| Fluid Tank | 2 | 900 | 10k units |
| Loading Dock | 1 | 150 | Sells to market, receives contracts |
| Freight Terminal | 3 | 20,000 | Connects base to inter-base network |
| Drone Port | 4 | 35,000 | Short-range point-to-point autohaul |
| Sorter Arm | 3 | 2,400 | Machine-to-machine, no belt needed |

### Support and Administration
| Building | Tier | Cost | Function |
|---|---|---|---|
| Bunkhouse | 1 | 600 | Houses 8 workers |
| Canteen | 2 | 2,500 | +15% worker output radius |
| Maintenance Shed | 2 | 1,800 | Reduces machine wear cost 30% |
| Research Lab | 2 | 5,000 | Converts inputs → Research Data |
| Advanced Lab | 4 | 38,000 | Higher-tier data, needs processors |
| Charter Hall | 3 | 25,000 | HQ for company features, share ledger |
| Market Office | 3 | 12,000 | Post/accept player contracts remotely |
| Survey Office | 3 | 8,000 | Reveals seam quality in adjacent regions |
| Signal Tower | 4 | 18,000 | Intel radius, detects incoming freight |
| Filter Stack | 3 | 6,000 | Cuts local Haze 50% |

### Defense
| Building | Tier | Cost | Function |
|---|---|---|---|
| Perimeter Fence | 2 | 40/seg | Slows infantry, marks boundary |
| Watch Post | 2 | 3,000 | Spots raiders, extends vision |
| Auto-Turret | 3 | 9,000 | Consumes ammunition, engages units |
| Flak Battery | 4 | 22,000 | Anti-air and anti-drone |
| Bunker Line | 4 | 15,000 | Garrison position, cover for defenders |
| Shield Pylon | 5 | 80,000 | Timed damage nullification field |
| Depot Vault | 3 | 14,000 | War-protected storage, cannot be looted |

---

## 7. Resource System

Resources are split into four classes, and the distinction matters mechanically.

**Raw (extracted).** Ironstone, Copperstone, Coal, Limestone, Sand, Granite, Timber, Water, Bauxite, Nitre, Crude Oil, Quartz.

**Strategic (region-locked).** Found only in specific biomes or at Rich Seams. These are the reason territory matters: **Cindrite** (heat-stable mineral, needed for high-tier furnaces and superalloy), **Voltite** (crystal, needed for advanced circuits and shields), **Heavy Sand** (uranium precursor), **Sulfur Brine** (propellant and explosives). No player can be self-sufficient in all four. This is the single most important economic design decision in the game — it forces trade, alliances, and wars without any artificial nudging.

**Intermediate (manufactured).** Ingots, plates, gears, wire, coke, lime, glass, concrete, boards, motors, hydraulics, fuel, plastic, rubber, ammunition.

**Abstract (non-physical).** Scrip (§, currency), Research Data (tech), Reputation (per-city standing), Influence (territory control), Labor (workforce pool), Power (kW), Haze (pollution).

**Node quality and depletion.** Every deposit has a **grade** (Poor / Standard / Rich / Prime) and a **volume**. Grade multiplies extraction rate; volume depletes over months of real time, and depleted nodes drop to a permanent 20% trickle rather than dying, so a player is never stranded on a dead plot. Deep Veins sit under standard nodes and require Tier 3 boring tech to reach — this makes tech an alternative to conquest for solving a resource shortage, which is critical for peaceful players.

---

## 8. Production Chains

Chains are short and readable at the start (2 steps) and branch aggressively later (6–9 steps). Sample rates are per minute at Tier 2 machines.

**The spine — iron to weapons:**

```
Ironstone --[Smelter]--> Iron Ingot --[Press]--> Iron Plate
                                    \-[Lathe]--> Iron Gear

Iron Ingot + Coke + Lime --[Blast Furnace]--> Steel
Steel --[Press]--> Steel Plate --\
Steel --[Lathe]--> Steel Rod ----- [Assembler] --> Machine Frame
Copper --[Wire Mill]--> Wire -----/

Machine Frame + Motor + Hydraulics --[Vehicle Hall]--> Utility Truck
Steel Plate + Propellant + Brass Case --[Arms Plant]--> Ammunition
Machine Frame + Armor Plate + Motor + Ammunition --[Arms Plant]--> Armored Vehicle
```

**The electronics branch:**

```
Sand --[Kiln]--> Glass
Quartz --[Chem Vat]--> Silicon Wafer
Copper --[Wire Mill]--> Wire
Wafer + Wire + Plastic --[Circuit Works]--> Circuit Board
Circuit Board + Voltite + Gold Contact --[Circuit Works]--> Processor
Processor + Optics + Superalloy --[Nanofab]--> Autonomy Core
```

**The chemical branch:**

```
Crude Oil --[Refinery]--> Fuel + Lubricant + Naphtha
Naphtha --[Cracker]--> Plastic Pellet + Synth Rubber
Nitre + Sulfur Brine --[Chem Vat]--> Propellant
Limestone + Clay --[Kiln]--> Cement --[Mixer]--> Concrete
```

**Full example chain (endgame, 9 steps):**
Ironstone → Iron → Steel → Steel Plate → Machine Frame → Motor → Chassis → Armored Vehicle → *Field Deployment*.
Every step has a market price, so a player can profitably enter or exit the chain at any point. **This is the core economic freedom of the game:** you can be an ore seller, an ingot seller, a component seller, or a vehicle seller, and all four are viable businesses.

---

## 9. Economy

**Currency.** Scrip (§). Earned, never purchasable with real money.

**Four ways to sell, each with a different risk/reward profile:**

1. **Spot market (Loading Dock).** Instant, always available, lowest price. The safety net.
2. **City contracts.** Rate-based orders with a duration. Pay 1.4–2.2x spot. Failing one costs Reputation. The main income source.
3. **Player contracts.** Posted by other players through Market Offices. Best prices for intermediate goods, since manufacturing players would rather buy your plates than mine their own ore.
4. **Strategic supply.** Controlling and supplying a city with what it lacks generates Influence in addition to Scrip — the bridge between economy and territory.

**Demand saturation (the anti-snowball economic engine).** Each city has demand curves per item. Selling into a market pushes its price down along that curve; prices recover over hours. Crucially, saturation is weighted **per seller**: your tenth thousand units of iron plate sells for far less than a newcomer's first hundred. A dominant player cannot simply scale one product forever; they must diversify, move to higher-tier goods, or open new markets in distant cities. Newer players always have a profitable niche in the goods big players have saturated.

**Costs that scale with you:**
- **Maintenance** — every machine accrues wear, paid in Scrip and spare parts. Larger factories carry real fixed costs.
- **Wages** — workers are paid per shift; higher tiers need skilled labor at higher rates.
- **Overhead** — each base beyond the first adds an administrative cost that grows superlinearly unless offset by Logistics and Administration tech.
- **Freight** — inter-base shipping burns fuel and time.
- **Insurance** — optional premium that pays out repair costs after war damage.

The result is that a sprawling empire with poor design can be *less* profitable than a tight, well-run two-base operation. Efficiency beats size, which is exactly the pressure the genre usually lacks.

**Economic change over time.** Every season introduces drift: city populations grow and change what they consume; a new technology unlocks a good the market has never seen (early adopters make fortunes); a Rich Seam is discovered, collapsing the price of a strategic resource; a **Trade Blockade** during a war chokes supply and spikes prices region-wide. The market is a story, not a table.

---

## 10. Upgrade and Technology Tree

**Currency of progress:** Research Data, produced by Labs consuming physical goods. Early data costs iron gears; late data costs processors and Voltite. Research is therefore always a *factory problem*, never a grinding problem.

**Structure:** six branches on a shared wall map, roughly 180 nodes. Every player can eventually unlock everything, but **branch specialization** gives escalating discounts and unique capstones, so nobody gets everywhere fast, and cross-player trade in tech-gated goods stays valuable.

### Branch A — Metallurgy and Industry (red)
Bloom → Blast → Arc → Induction. Alloying, casting, high-pressure forming, superalloy. Capstone: **Continuous Cast** (all smelting +40% rate, -25% power).

### Branch B — Power and Energy (yellow)
Boilers → turbines → grid management → renewables → fission → fusion. Includes Capacitor logic, load balancing, and line-loss reduction. Capstone: **Grid Sovereignty** (share power between adjacent bases; sell surplus power to cities as a product).

### Branch C — Automation and Logistics (blue)
Belt tiers, sorters, filters, drones, rail, autoloaders, remote-configuration, and **Blueprint Stamping** (build entire blueprints in one action if materials are staged). Capstone: **Autonomy Network** (self-balancing factory that auto-adjusts recipe ratios).

### Branch D — Commerce and Administration (green)
Contract slots, market intel, price forecasting, extra base Deeds, overhead reduction, insurance, banking, share issuance. Capstone: **Exchange Charter** (found a player-run commodity exchange other players trade through, earning you a fee).

### Branch E — Military and Defense (orange)
Turrets, ammunition types, armor, vehicles, artillery, aircraft, electronic warfare, fortification. Capstone: **Combined Arms Doctrine** (multi-unit-type stacks gain a large coordination bonus).

### Branch F — Frontier Science (violet)
Chemistry, electronics, robotics, optics, nuclear, orbital. Unlocks the endgame **Orbital Program**. Capstone: **Uplink Array** (satellite intel over the whole map; global logistics jumps).

**Visible upgrades.** Every tier change alters models, sounds, and animation. A Tier 4 factory does not look like a Tier 1 factory with bigger numbers — it looks like a different civilization. Belts get faster and hum louder; smelters go from open flame to sealed arc; drills go from wood to armored rigs.

---

## 11. Multiple-Base System

**Your first base is special.** It is your **Foundry Seat**: permanently protected, never destructible, never capturable. It is your bed, your bank, and your guarantee that no war can erase you. Everything you build beyond it is a calculated exposure.

**Unlocking bases.** Each additional base requires a **Deed**, gated by three things at once so it can never be rushed with money alone:
1. Charter Level (earned through total contract fulfillment and Reputation),
2. a Deed purchase (§25,000 for the second, roughly doubling each time),
3. an Administration tech node on Branch D.

Practical cap: 3 bases by mid-game, 6 by late-game, 8 with the full Administration line and a Charter Hall.

**Base archetypes.** A base's value comes from what its region offers:

| Archetype | Placed in | Provides |
|---|---|---|
| Mining Outpost | Ore-rich highlands | Cheap raw feed |
| Industrial Works | Flat, high-labor regions near cities | Bulk manufacturing |
| Refinery Base | Oil fields, coastal | Fuel, plastics, chemicals |
| Research Campus | Low-Haze, high-amenity regions | Research Data at a bonus rate |
| Trading Port | Coastal / river junctions | Cheaper freight, market access, tariffs |
| Military Base | Chokepoints, borders | Unit staging, supply projection |
| Colony | Frontier / hazardous biomes | Strategic resources, high risk |

**How bases communicate.** Bases are not magically linked. They connect through the **Freight Network**: physical routes you build and maintain on the world map. Every route has capacity, transit time, fuel cost, and a security rating. A base with no route is an isolated island that must sell locally.

Bases share: your tech, your Scrip, your Charter, and your contract slots.
Bases do **not** share: inventory, power (until Grid Sovereignty), or labor.

**Powerful but expensive.** Each base adds Overhead, needs its own power and workforce, and creates a new front to defend. The design goal is that a third base should feel like a *decision*, not an inevitability. Many strong players deliberately run two bases and out-earn six-base sprawlers.

---

## 12. Logistics System

Logistics is the connective tissue and the primary war target. It's split into two layers.

**Intra-base (belts and pipes).** Covered in the factory system. Local, physical, always safe.

**Inter-base (the Freight Network).** You build routes between your Freight Terminals across real map terrain. Terrain matters: mountains slow roads, rivers need bridges, coasts enable ships.

| Mode | Unlock | Capacity | Speed | Cost | Notes |
|---|---|---|---|---|---|
| Truck Convoy | Tier 2 | Low | Medium | Cheap | Flexible, needs roads, easy to raid |
| Rail Line | Tier 3 | Very high | Fast | High capital | Requires laid track; the workhorse |
| Cargo Ship | Tier 3 | Extreme | Slow | Medium | Coastal/river only, immune to land raids |
| Pipeline | Tier 3 | High (fluids) | Continuous | Medium | Fluids only, vulnerable at pump stations |
| Cargo Aircraft | Tier 4 | Low | Very fast | Very high | Ignores terrain, vulnerable to flak |
| Drone Corridor | Tier 4 | Medium | Fast | High | Short range, fully automated |
| Orbital Drop | Tier 6 | Medium | Instant | Extreme | Endgame, cannot be interdicted |

**Route management.** Each route is configured with a manifest ("send up to 60 Steel/min from Ridgehold to Kettleford Works, maintain 2,000 buffer"). The UI shows the network as a live schematic with flow-rate edges — the same Flow Lens language as inside a factory, so learning one teaches the other.

**Interdiction.** During a declared war, routes crossing contested territory can be **raided**, which halts flow and captures a portion of the cargo. Routes have a security rating raised by escorts, armored rolling stock, and friendly territory. This is what makes war strategic rather than destructive: you are trying to *strangle*, not *smash*.

**Why it's fun.** The moment a player realizes their empire is a graph — with capacities, bottlenecks, and cut points — the whole game reframes. Defending a rail junction feels meaningful in a way that defending a wall never does.

---

## 13. Multiplayer System

**Shape of a server.** Each world is a persistent shard hosting 60–100 concurrent players out of a registered population of roughly 400–800, running a full season (6–10 weeks). The world simulates continuously; players' factories keep producing while offline, up to storage capacity.

**Why interact with other players?** Because the design makes isolation strictly inferior:

- **Strategic resource asymmetry.** No region has all four strategic resources. Tier 4+ production requires goods you cannot mine.
- **Demand saturation.** Your own selling depresses your prices; selling *to a player* who converts your goods into something else avoids the penalty entirely.
- **Specialization discounts.** Branch specialization makes you far better at one thing and mediocre at others; buying from a specialist beats doing it yourself.
- **Contract chains.** City mega-contracts require volumes and item variety no solo player can produce, and pay enormously. They are effectively multiplayer raids for the economy.
- **Territory.** Influence contests are multi-player by nature.

**Player-facing multiplayer features:** direct trade with escrow, standing buy/sell orders, player contracts, shared build permissions per plot, alliances, Charters (companies), diplomacy states, espionage, and war.

**Presence.** You can physically visit another player's base (if permitted), walk their factory floor, and copy ideas. Factory tourism is a genuine social feature — and it drives the blueprint economy.

---

## 14. Factions and Companies (Charters)

**Founding a Charter** costs §100,000 and a Charter Hall. It creates a persistent legal entity with a name, crest, color, and a public **Ledger**.

**Structure.**
- **Governor** — founder; sets policy, declares war, issues shares.
- **Directors** — can accept contracts, spend the treasury within limits, manage diplomacy.
- **Members** — contribute production, draw from shared stock, get protection.
- **Contractors** — non-members with a supply agreement; get pay and partial war protection.

**Shares and payouts.** A Charter issues shares. Members holding shares draw a proportional dividend from the treasury each cycle. This is the most important social mechanic in the game: it turns "join a group" into "own a piece of a business," which motivates long-term participation from smaller players who could never be top of the leaderboard alone.

**Charter functions.**
- **Shared stockpile** with per-role withdrawal limits and full audit log (anti-theft by design).
- **Joint contracts** — accept city mega-contracts that members fulfill together, auto-splitting payouts by contribution.
- **Territory claims** — Influence pools at the Charter level.
- **Collective research** — members can donate Research Data to unlock Charter-wide bonuses (e.g. -10% freight cost across all member routes).
- **War powers** — only Charters can declare full wars; solo players can only engage in the lighter Raid tier.

**Diplomacy states:** Neutral, Trade Pact (tariff-free), Alliance (mutual defense, shared vision), Rivalry (cheaper war declaration), War, Truce (enforced non-aggression with a timer), Vassalage (a smaller Charter pays tribute for protection — and can revolt).

---

## 15. Trading System

**Direct trade.** Face-to-face window with escrow. Both sides confirm; the server executes atomically. No trade scams are mechanically possible.

**Order book.** Every city hosts an exchange where players post limit buy/sell orders on any item. Orders are visible, prices are public, and history charts are available for 7 days. Reading the order book is a genuine skill.

**Contracts between players.** Rate-based agreements: "deliver 40 Circuit Board/min for 3 days at §22/unit." Backed by a collateral deposit from both sides. If the supplier fails, the buyer takes the collateral. This creates real, enforceable industrial relationships — and reputational consequences for flaking, since fulfillment history is public on your profile.

**Futures (late game, Branch D).** Agree now to deliver later at a fixed price. Lets manufacturers lock input costs and lets miners guarantee demand before expanding. This is the single deepest economic system in the game and it is entirely optional.

**Tariffs and ports.** Charters that own a Trading Port can set a tariff on freight transiting their territory. Others can pay it, route around it (longer, costlier), or go to war over it. Trade routes therefore create real geopolitics.

**Blueprint market.** Sell factory designs for Scrip. Designs are rated and reviewed. Top designers become server celebrities.

---

## 16. Warfare System

**Design axiom: war changes who controls production; it never deletes production.** Nothing a player built is permanently destroyed by another player. Ever. Damage is a *state* (Damaged → Offline), repairable with materials and time. This one rule is what makes an open-PvP industrial game survivable.

### Conflict tiers

**Tier 1 — Sabotage (individual, low stakes).** Espionage agents can temporarily disable a single building, steal a cargo shipment, or copy intel. No permanent loss, cheap to counter with Signal Towers and guards. Available to solo players.

**Tier 2 — Raid (small scale).** A short, focused strike on a *specific* outpost or freight route. Declared 2 hours in advance. Duration: 30 minutes. Objective: capture cargo or temporarily seize a resource node's output. Cannot target Foundry Seats. Cannot be launched at players more than one bracket below you.

**Tier 3 — War (Charter vs Charter).** The full system.

### The war lifecycle

1. **Casus Belli.** You need a reason the system recognizes: a tariff dispute, a contested claim, a broken contract, a rivalry, or a Seam claim. This prevents random aggression and gives wars a narrative.
2. **Declaration and War Bond.** The aggressor posts a bond in Scrip and materials, scaled to the Industrial Weight gap. If the aggressor fails to hit their objectives, the entire bond transfers to the defender. Attacking down is financially ruinous unless you win decisively and fast.
3. **Muster (24–48h).** No combat. Both sides build defenses, stage units, secure routes, call allies. This window is non-negotiable and exists so no player is ever attacked while asleep and unprepared.
4. **Campaign (3–5 days, with daily Combat Windows).** Combat is only possible during announced windows (e.g. two 3-hour blocks per day, chosen by each side and overlapping) so nobody loses because of their time zone. Outside windows, both sides rebuild and reposition.
5. **Objectives.** Wars are won on points, not annihilation: capture Field Objectives (junctions, seams, depots), interdict freight tonnage, destroy military infrastructure, hold territory at window's end.
6. **Resolution.** At campaign end, points decide the outcome. The winner takes from a menu: territory claim transfer, a tariff concession, reparations from the treasury, forced access to a seam, or a trade agreement on their terms. **The loser always keeps their factories, their tech, and their Foundry Seat.**
7. **Peace and Truce.** A settled war creates an enforced truce (7 days minimum) between the parties. Either side may sue for peace mid-war; accepting early surrender gives the winner a reduced reward and ends the fighting immediately, which is a genuinely attractive option for both sides.

### What combat actually looks like

Units are **stacks** commanded on the world map with light real-time tactical resolution at contact points. You order a mechanized column from your military base to a rail junction; it consumes fuel and ammunition en route; when it meets defenders or turrets, a short real-time engagement plays out on the terrain, and players present can take direct control of a vehicle to fight hands-on. If nobody is present, it auto-resolves with defenders favored.

**Supply is everything.** Units in the field consume ammunition and fuel delivered by your own freight network. An army beyond its supply range loses effectiveness fast. Cutting a rail line can win a battle without firing a shot. This is the mechanic that ties warfare directly back to factory building — you win wars by having designed a better logistics network months earlier.

---

## 17. Military Units

All units are **manufactured**, not bought — every unit is the endpoint of a production chain, and every unit lost is factory output that has to be rebuilt. Losing an army hurts your industry, which naturally throttles endless warmongering.

| Unit | Built from | Role |
|---|---|---|
| Militia Squad | Small Arms + Rations | Cheap garrison, holds points |
| Line Infantry | Small Arms + Armor Vest + Ammunition | Core capture unit |
| Engineer Team | Toolkit + Explosive | Repairs, demolition, route sabotage |
| Scout Car | Chassis + Motor | Vision, fast objective grabs |
| Utility Truck | Chassis + Motor + Frame | Field supply carrier — the unsung MVP |
| Armored Car | Chassis + Armor Plate + Autocannon | Anti-infantry, raiding |
| Battle Tank | Heavy Chassis + Composite Armor + Main Gun | Frontline breakthrough |
| Artillery Piece | Heavy Frame + Barrel + Propellant | Sieges turrets from range, needs spotting |
| SPAA Vehicle | Chassis + Radar + Flak Gun | Anti-air umbrella |
| Attack Drone | Autonomy Core + Airframe + Munition | Precision strikes on infrastructure |
| Transport Plane | Airframe + Turbine | Rapid unit redeployment |
| Gunship | Airframe + Turbine + Munitions | Strong, expensive, dies to flak |
| Saboteur Agent | Recruited, needs Reputation | Espionage layer |
| Siege Crawler | Superalloy + Fusion Cell + Heavy Armor | Endgame; slow, immense, huge supply draw |

**Counter web (deliberately readable):** infantry holds ground, armor breaks infantry, artillery breaks fortifications, aircraft breaks artillery, flak breaks aircraft, engineers break supply lines, and supply lines break everything. No single unit type wins; the Combined Arms capstone rewards mixed stacks.

---

## 18. Territory System

The world is divided into **Regions** (roughly 120 across the map), each containing several **Sites**: resource nodes, city outskirts, junctions, or buildable plots.

**Control is earned, not conquered.** A Region's controller is whoever holds the most **Influence** there, and Influence comes from:
- supplying the region's city or industry with goods it demands (the largest source),
- owning and operating bases and infrastructure in the region,
- holding Field Objectives at the end of a war campaign,
- Charter-level investment in local development.

**This means a purely economic player can take and hold territory without ever building an army** — by simply out-supplying rivals. Warfare is one lever among several, and often the more expensive one.

**Control benefits:** reduced local freight cost, first claim on new plots and seams, tariff-setting on transiting freight, priority on the region's contracts, and a share of the region's tax revenue.

**Decay.** Influence decays if you stop supplying. Territory must be *maintained*, so a snowballing empire eventually stretches past what it can service — a natural, non-punitive ceiling.

---

## 19. World and Map Design

One continent, eight sectors, ringed by ocean, with a persistent day/night cycle and seasons that affect renewables and river flow.

**The Starter Vale (center-south).** Permanently PvP-free. Rich enough to learn on, deliberately poor in strategic resources so ambition eventually pulls players outward. Plots here are never lost, and a player can always return.

**Kettleford Basin (temperate plains).** The economic heart. Three cities, huge demand, flat easy building, high labor availability, mediocre ore. The place to be a manufacturer.

**The Ridgeback (mountains, north).** Highest-grade ore and coal, plus most known **Cindrite**. Brutal terrain, expensive rail, few workers. The classic mining frontier, and the most-contested land on the map.

**Sallow Fen (wetlands, east).** Oil seeps, sulfur brine, cheap land, heavy Haze penalties already baked in. Refinery country. Ugly, profitable, and slightly hostile.

**The Glasslands (desert, southwest).** Quartz, heavy sand, extreme solar output, no water. Electronics and power specialists thrive; everything else struggles.

**Verdant Shelf (forest, west).** Timber, clean water, lowest Haze, best research output modifier. Where campuses and green-power builds go.

**The Cinderwaste (volcanic, far north).** Dangerous. Ash storms damage unprotected machines, Haze is naturally high — but the only deposits of **Voltite** at scale. Endgame territory.

**The Reach (archipelago and coast).** Deep-sea oil, fishing, ports. Naval freight dominance, and the only sea route bypassing Ridgeback tariffs. Strategic chokepoint: **the Narrows**, a single strait every coastal shipping lane passes through.

**Neutral cities** (nine of them) are never player-owned but can be player-*influenced*. They post contracts, host exchanges, and provide the demand that drives the entire economy.

**Chokepoints** are explicitly designed and named: the Narrows, Kettle Pass, the Long Bridge, Ashgate. Controlling one is a legitimate business model.

---

## 20. PvP Balancing

- **Industrial Weight (IW)** is a public rating from throughput, assets, tech tier, and military stock. You may declare war only within your bracket or upward. Punching up is cheap; punching down is expensive and heavily bonded.
- **Defender's advantage.** Defenders get terrain, turrets, shorter supply lines, and auto-resolve favoring. Attacking is *supposed* to be hard.
- **Attrition is real.** Every unit destroyed is materials gone. A winning aggressor still pays a real industrial bill.
- **War fatigue.** Consecutive wars raise your bond costs and lower your workforce morale. Serial aggressors throttle themselves.
- **One war at a time** per Charter below the top bracket.
- **Combat windows** ensure nobody is beaten while asleep.
- **Loot caps.** Raids can capture at most a fixed percentage of a shipment or a depot's contents per window, and Depot Vaults are entirely immune.
- **Reparations flow downward.** A large Charter defeating a small one collects far less than the reverse, scaled by IW ratio.

---

## 21. New-Player Protection

1. **Starter Vale immunity.** Permanent, not timed. You cannot be attacked there, ever, at any point in your career.
2. **Grace Charter (first 14 days of play).** New accounts cannot be raided or warred outside the Vale, and get a small production bonus.
3. **Bracket lock.** Players in the bottom two IW brackets cannot be targeted by the top two.
4. **Inviolable Foundry Seat.** Your first base can never be captured or destroyed by anyone.
5. **Reconstruction Grant.** After losing a war or raid, the city grants free repair materials and a temporary 20% production bonus for 48 hours. Losing is a setback with a built-in comeback.
6. **Nothing is deleted.** Buildings go offline, not away.
7. **Mentor bounty.** Established players earn Reputation and Scrip for onboarding new players who reach milestones — turning veterans into recruiters rather than predators.
8. **Catch-up tech discount.** Research nodes get cheaper as more of the server unlocks them, so joining in week 6 of a season is viable.

---

## 22. Progression: Beginner to Endgame

**Hours 0–2 — The Apprentice.** One plot, one chain, first contract, first tech. Goal: automate iron.

**Hours 2–10 — The Operator.** Multi-stage production, power grid management, first Tier 2 machines, steady contract income. Goal: §25,000 and a Deed.

**Hours 10–40 — The Industrialist.** Second base, first freight route, first serious specialization choice, joining or founding a Charter. Goal: consistent Tier 3 component output.

**Hours 40–120 — The Magnate.** Three to five bases, rail network, strategic-resource dependence forces real diplomacy, first raids and wars, Influence contests over a home region. Goal: control a region.

**Hours 120–300 — The Power.** Tier 4–5 production, military-industrial capability, Charter leadership, tariff politics, mega-contracts, futures trading. Goal: shape a sector of the map.

**Hours 300+ — The Endgame.** Orbital Program, fusion power, autonomy networks, server-scale projects, seasonal championship.

At every stage the player has: a short-term goal (fix the line), a medium-term goal (fill the contract, unlock the node), and a long-term goal (the next base, the next region, the next war).

---

## 23. Endgame Activities

- **The Orbital Program.** A massive multi-stage project requiring goods from every branch. Completing it unlocks Orbital Drop logistics and permanent map-wide intel. Realistically a Charter-scale effort, not a solo one.
- **Mega-contracts.** Server-wide city demands ("Kettleford needs 200,000 units of Concrete and 4,000 Machine Frames in 5 days") with enormous payouts and a public leaderboard of contributors.
- **The Exchange.** Founding and operating a player-run commodity exchange, earning fees on other players' trades.
- **Territory championship.** End-of-season scoring on Influence, output, and war record. Winners get permanent cosmetic monuments visible on all future maps and a titled entry in server history.
- **Grand Projects.** Charter-built world modifiers — a canal through the Ridgeback, a bridge across the Narrows, a continental rail trunk — that permanently alter the map for everyone and stay standing across seasons.
- **Mentorship and design.** Publishing blueprints, running a training Charter, being the person everyone buys Voltite from.

---

## 24. World Events

Events arrive on a rhythm — small ones weekly, big ones monthly — and are always *opportunities as well as problems*.

- **Ore Rush.** A new Rich Seam is revealed in neutral territory. Land grab, tension, likely war.
- **Market Crash.** A commodity's price collapses for 72 hours. Specialists suffer; diversified players buy cheap.
- **Ash Storm (Cinderwaste).** Damages exposed machines region-wide; drives up demand for spare parts everywhere.
- **Strike Season.** Wages rise server-wide for a week; automation-heavy builds win.
- **City Boom.** A city's population spikes, tripling demand for construction goods.
- **Freight Embargo.** A city closes a route; everyone reroutes; chokepoint owners profit.
- **Derelict Convoy.** A neutral cargo train appears at a random junction; first Charter to reach and secure it takes the cargo. Fast, PvP-flavored, low-stakes.
- **Rogue Automatons.** PvE threat: malfunctioning machines attack outposts in a region. Purely cooperative — even enemies often team up. Excellent tension-release valve after a war.
- **Founder's Season Finale.** The last week of a season: doubled contract payouts, all truces expire, final territory scoring.

---

## 25. Missions and Contracts

**City contracts.** The backbone. Tiered Bronze → Iron → Steel → Platinum by Reputation with that city. Rate-based, timed, with a visible fulfillment bar.

**Standing orders.** Low-value, always-available, unlimited. The safety net that guarantees income for a player who just wants to build quietly.

**Rush contracts.** Short windows, high pay, steep failure penalty. The gambler's option.

**Chain contracts.** Multi-stage story missions that teach a system while paying well: "Kettleford wants a rail spur" walks a player through their first rail line and gives them the track for free.

**Charter contracts.** Internal jobs a Governor posts to members, paid from the treasury. Turns a big Charter into a functioning employer for small players.

**Bounties.** Posted against a player who broke a contract or an aggressor in an unpopular war. Pays out for raiding them. Player-driven justice with a paper trail.

**Milestones.** Persistent personal achievements ("first 1,000 Steel/min", "supply four cities simultaneously") awarding cosmetics and titles.

---

## 26. Player-to-Player Interactions

Trade, escrow, contracts, futures, alliances, tariffs, joint ventures, shared build permissions, factory tourism, blueprint sales, mentorship, espionage, war, vassalage, and peace negotiation.

Two specific social systems worth calling out:

**Reputation is public and permanent within a season.** Contract fulfillment rate, war record, and bounty history are on every player's profile. Trust is a real, visible asset — and a real, losable one. The consequence is that most players behave well because it is *profitable* to be reliable.

**Vassalage.** A smaller Charter can accept protection from a larger one in exchange for tribute and preferential supply. This gives large powers something to *do* with weaker neighbors other than crushing them, and gives small Charters a survival path that isn't "quit." Vassals can accumulate independence points and revolt, which produces some of the best stories the game can generate.

---

## 27. Monetization Without Pay-to-Win

**Hard rule: no purchasable Scrip, resources, research, time skips, production boosts, extra bases, military power, or contract slots.** Nothing purchasable may alter production rate, combat outcome, or market position.

**What is sold:**
- **Cosmetics.** Building skins (art-deco works, brutalist works, rust-punk works), smokestack smoke colors, belt liveries, worker uniforms, vehicle paint, Charter crests and banners, HQ interior decoration, personal avatar gear, victory monuments.
- **Charter identity packs.** Custom crest editor, animated banners, territory flag styles.
- **Season Pass (cosmetic-only).** Two tracks, free and premium, both earned through *playing* — the premium track only adds cosmetic rewards to the same progress. Never sells power, never expires unfairly (unfinished passes convert to currency toward the next).
- **Quality-of-life that isn't power.** Extra blueprint *storage slots* (not stamping ability), additional factory camera bookmarks, extra loadout presets, name change tokens, expanded market watchlists, colorblind and UI theme packs (base accessibility is always free).
- **Private worlds.** Rent a friends-only server with adjustable rules for building-only or PvE play. This is likely the single largest revenue line and it sells *access to a different experience*, not an advantage in the main one.
- **Founder support tiers.** Purely vanity, plus a supporter badge and early access to cosmetic drops.

**Why this works commercially.** In a game where your factory is a personal creation you show off to other players, cosmetics are unusually high-value — people pay to make their build *look* like their reputation. Factory tourism, blueprint fame, and public Charter crests all create constant, organic cosmetic demand without touching the balance of the game.

---

## 28. Anti-Griefing Systems

Layered so that no single failure compromises the whole:

1. **Nothing is permanently destroyed.** Damage is a repairable state.
2. **Foundry Seats are inviolable.**
3. **Starter Vale is permanently safe.**
4. **IW brackets** prevent downward aggression.
5. **War bonds** make failed aggression financially catastrophic.
6. **Muster windows and combat windows** eliminate offline snipes.
7. **Casus belli requirement** stops motiveless attacks.
8. **Loot caps and protected vaults** cap the maximum bad day.
9. **Reconstruction Grants** guarantee recovery.
10. **War fatigue** throttles serial aggressors.
11. **Truce enforcement** prevents re-declaration harassment.
12. **Public reputation and bounties** create social consequences.
13. **Permission systems** — nobody can build on, modify, or enter your plot without explicit rights, and permissions are per-player, per-action, and revocable instantly.
14. **Chat and name filtering**, plus block, mute, and report with server-side evidence logs.
15. **Trade escrow everywhere** — scamming is mechanically impossible.

---

## 29. Anti-Exploit and Anti-Cheat

- **Server-authoritative simulation.** The client renders and requests; it never computes production, money, combat resolution, or inventory. Any client-side value is treated as a suggestion.
- **Recipe and rate validation.** Production is recomputed server-side per tick from the authoritative machine graph; a client claiming impossible output is simply ignored and flagged.
- **Rate limiting on every action** — placement, trade, contract acceptance — with burst detection.
- **Movement and physics validation** for on-foot and vehicle play: speed, distance, and collision sanity checks against server state.
- **Economic anomaly detection.** Statistical monitoring for wash trading, real-money-trade patterns, and alt-account resource funneling (many low-activity accounts feeding one). Flagged clusters go to review, not auto-ban.
- **Duplication defense.** All item movement is transactional; inventory operations are atomic with server-side idempotency keys, so replayed or interleaved packets cannot duplicate goods.
- **Blueprint sanitization.** Blueprints are data, validated against the schema and tech gates on import; they can never carry arbitrary payloads or bypass unlock requirements.
- **Snapshot and rollback.** Rolling world snapshots let a specific exploit's effects be reverted surgically without wiping legitimate progress.
- **Obfuscated but never trusted client.** Assume it will be reverse-engineered; design so that it does not matter.
- **Public audit trails** for Charter treasuries and trades, which turns the community into an additional detection layer.

---

## 30. Example UI Layout

**Overworld / factory view (main screen)**

```
+--------------------------------------------------------------+
| SCRIP §148,320   POWER 412/520kW   HAZE 31%   LABOR 44/60     |  <- Vitals bar (always visible)
+--------------------------------------------------------------+
|                                                              |
|                                                        [MAP] |  <- Minimap, top right
|                 [ 3D FACTORY VIEWPORT ]                [ ^ ] |
|                                                              |
|                                                  +---------+ |
|                                                  | ACTIVE  | |  <- Contract tracker,
|                                                  | Steel   | |     collapsible
|                                                  | 18/20pm | |
|                                                  | 04:12   | |
|                                                  +---------+ |
+--------------------------------------------------------------+
| [BUILD] [FLOW LENS] [POWER] [LOGISTICS] [RESEARCH] [MARKET]   |  <- Primary toolbar
| [CHARTER] [MAP] [WAR]                                         |
+--------------------------------------------------------------+
```

- **Build menu** opens as a horizontal category strip (Extract / Smelt / Make / Power / Move / Store / Support / Defend) with card-based items showing cost, power draw, and rate. Search bar included from day one.
- **Flow Lens** is a toggle, not a menu: the world recolors, rate labels appear on every belt, and problem points pulse.
- **Market** opens a split view: order book left, price history chart right, your open contracts bottom.
- **World Map** is a separate full-screen mode with layer toggles: territory, resources, freight routes, war fronts, prices.
- **Mobile/touch layout** collapses the toolbar into a radial build wheel and moves vitals to a single tap-expandable pill. Every core action must be reachable in two taps.
- **Notifications** stack bottom-left and are strictly categorized: Production (amber), Economy (green), Diplomacy (blue), War (red). War notifications never auto-dismiss.

---

## 31. Example Factory Progression

**Stage 1 — "The Iron Shack" (0–2h).**
2 hand drills → 1 belt → 2 bloom smelters → loading dock. 12 Iron Ingot/min. Powered by one coal boiler. Total footprint: 8×10 tiles. Income: ~§900/hour.

**Stage 2 — "The Plate Works" (2–10h).**
Powered drills feeding a blast furnace line; coke oven added; two presses making Iron Plate. Steam turbine hall replaces boilers. A splitter sends half the ingots to sale and half to plate. 40 Plate/min. Footprint: 24×24, the full starter plot. Income: ~§6,000/hour.

**Stage 3 — "The Steel Block" (10–40h).**
Second base on the Ridgeback pushes 120 ore/min home by truck convoy. Home base converts entirely to steel: blast furnace bank of 6, lime kiln, dedicated coke row, press and lathe halls, first Assembler Mk1 making Machine Frames. Rail line replaces trucks. 60 Machine Frame/min. Income: ~§40,000/hour.

**Stage 4 — "Kettleford Heavy" (40–120h).**
Four bases: Ridgeback (ore), Sallow Fen (fuel and plastics), Verdant Shelf (research), Kettleford (assembly). Rail trunk with three spurs. Arc furnaces, Assembler Mk2 banks, a Circuit Works fed by Glasslands quartz bought from a rival's Charter. Producing Motors, Hydraulics, and Circuit Boards for sale to other players' vehicle lines. Income: ~§300,000/hour.

**Stage 5 — "The Combine" (120h+).**
Seven bases, fission power, drone corridors, Autonomy Network auto-balancing the whole complex. Arms Plant running on the side keeps a standing mechanized brigade fed. Contributing 15% of the server's Orbital Program. The factory is now less a build and more an institution — and it started as two hand drills and a belt.

---

## 32. Example War Scenario

**The Ashgate War — Ridgehold Combine vs. Fen Consolidated.**

*Background.* Ridgehold Combine (5 players, IW 4,200) controls the Ridgeback's Cindrite seams. Fen Consolidated (7 players, IW 3,900) refines all the fuel in Sallow Fen. Ridgehold's rail trunk crosses Ashgate Pass, in a region where Fen holds a slim Influence lead — and Fen has just imposed a 12% tariff on Ridgehold's ore trains.

*Declaration.* Ridgehold declares with casus belli "Tariff Coercion." Bond posted: §420,000 plus 5,000 Steel. Objectives: seize Ashgate Junction, hold two Field Objectives, and interdict 40,000 tonnage of Fen freight.

*Muster (36h).* Fen digs in: auto-turrets on the junction approaches, a bunker line at the pass, ammunition stockpiled in a Depot Vault. They also quietly reroute 60% of their fuel exports to slow cargo ships through the Reach, accepting worse margins to remove the target. Ridgehold masses two tank companies, an artillery battery, and — critically — twelve utility trucks, having learned that supply wins.

*Day 1.* Ridgehold pushes Ashgate. Fen turrets shred the first armored probe. Ridgehold's artillery, spotted by a scout car, silences two turret nests. Ridgehold takes the junction at the window's close. Cost: 9 units, roughly §200,000 of production.

*Day 2.* Fen counterattacks the *supply road*, not the junction — engineers demolish a bridge on Ridgehold's rail spur. Ridgehold's forward units go unsupplied and fight at 55% effectiveness. Fen retakes one Field Objective. The war's momentum reverses without a single factory being touched.

*Day 3.* Ridgehold rebuilds the bridge under fire, escorts a truck convoy through, and holds. Meanwhile a neutral Charter, sensing opportunity, sells Fen anti-tank munitions at triple price. The war is now making a third party rich, which is exactly as intended.

*Resolution.* Ridgehold hits 2 of 3 objectives: partial victory. They take a permanent tariff exemption through Ashgate and a §180,000 reparation — but not the territory. Their bond returns minus a penalty. Fen keeps every building, every worker, and every research node. Both sides enter a 7-day truce.

*Aftermath.* Fen's rerouted sea shipping turns out to be cheaper than they expected and becomes permanent, which weakens Ridgehold's leverage for the next war. Fuel prices spiked 30% during the campaign and made a small solo refiner in the Fen wealthy enough to buy their third Deed. Nobody was wiped out; the map changed; everyone has a story.

---

## 33. Example Economy Scenario

**The Circuit Board Squeeze, Week 4.**

Kettleford's Chain Contract line begins demanding Circuit Boards for a City Boom event: 3,000/day across three cities. Boards need Silicon Wafers (quartz, Glasslands), Wire (copper, common), and Plastic (naphtha, Sallow Fen). No single region has all three.

*Day 1.* Board prices jump from §14 to §31. Every player with a Circuit Works retools. Quartz demand triples.

*Day 2.* **Glasslands Mining Co.** — three players with a quartz monopoly — raises wafer prices 60%. Buyers grumble but pay. GMC's Influence in the Glasslands surges from the volume.

*Day 3.* A mid-sized manufacturer, **Vessel Works**, does the math and realizes it is cheaper to *build a quartz outpost* than to keep buying. They spend §90,000 on a Deed and a Glasslands claim. This is the correct systemic response to a monopoly: vertical integration is always available.

*Day 4.* Demand saturation kicks in for the top three board sellers; their per-unit revenue falls 35% while smaller sellers still get near-peak prices. Small producers make their best week of the season.

*Day 5.* A Market Crash event hits plastics. Board input costs collapse. Margins explode for anyone with stockpiled naphtha. Two players who had signed **futures** at week-2 prices lose money on the deal — and learn what futures are for.

*Day 7.* The Boom ends. Board prices settle at §19, permanently higher than before because more players now have Tier 3 electronics tech and more downstream demand exists. GMC ends the week with a fortune, a resented reputation, and a new competitor in Vessel Works who will undercut them in week 6.

Nobody was told what to do. Every decision was economic. The market moved because players moved it.

---

## 34. Server and Player-Count Recommendations

- **World shard:** 60–100 concurrent players; 400–800 registered per world. Below 50 the economy is too thin for trade to matter; above ~120 the map becomes crowded and simulation cost rises steeply.
- **Season length:** 8 weeks. Long enough for a full arc, short enough that a losing position is never permanent.
- **Persistence:** worlds simulate continuously. Offline players keep producing at full rate until storage fills — no login-pressure mechanic, ever.
- **Tick model:** production resolves on a 1 Hz authoritative economic tick; combat and movement run at 10–20 Hz only within active engagement zones; everything else is event-driven. This keeps a 100-player industrial world affordable.
- **Interest management:** clients only receive detailed state for their current region plus summary state for owned assets elsewhere.
- **Modes:** Public worlds (full ruleset), Peaceful worlds (no war tier, economy and territory only — expect this to be very popular), Private worlds (friends, rented, adjustable rules), and Sandbox (single-player creative, no economy, excellent for blueprint design).
- **Cross-world persistence:** account level, cosmetics, blueprints, and season history carry over; Scrip, factories, and territory do not.

---

## 35. Making It Addictive Without Being Predatory

The goal is a game people *return to*, not one they *can't leave*. The distinction is enforced by design rules:

**Use these:**
- **Clean stopping points.** Every loop completes. A player can always finish a contract and log off feeling done.
- **Offline production at full rate.** Progress never punishes absence.
- **Legible improvement.** The Flow Lens makes every optimization visible and immediate — this is the honest version of a dopamine loop.
- **Multiple simultaneous goal horizons** so there is always a next thing, but never an anxious thing.
- **Social obligation of the good kind.** Charter contracts and supply relationships bring people back because other people are counting on them — but contracts have generous windows and members can cover for each other.
- **Scheduled, finite seasons.** A clear end reduces the "I can never stop or I'll fall behind" trap.
- **Craft and expression.** Blueprints, factory tourism, and cosmetics make the game about making something you're proud of.

**Never use these:**
- Energy systems, lives, or timers that gate play.
- Paid time-skips or resource packs.
- Loot boxes or randomized paid rewards of any kind.
- Daily login streaks that punish a missed day.
- Decay or theft that only happens while offline.
- FOMO-driven limited-time paid bundles with countdowns.
- Push notifications engineered around loss ("Your factory is idle!"). Notifications are opt-in and informational only.
- Anything that makes a 6-hour-a-day player mechanically undefeatable by a 1-hour-a-day player. Demand saturation, overhead scaling, and Influence decay all exist partly to enforce this.

**Session health features:** an optional play-time reminder, a "session summary" screen that celebrates what you accomplished and encourages logging off satisfied, and no leaderboard that ranks raw hours played.

---

## 36. How the Systems Connect

A quick sanity map, because a design is only good if the parts need each other:

- **Factory → Economy:** what you build determines what you can sell.
- **Economy → Tech:** money and goods buy Research Data, which is itself a factory product.
- **Tech → Factory:** unlocks visibly change what you can build and how it looks.
- **Factory → Bases:** space and resource limits force expansion outward.
- **Bases → Logistics:** separated bases are useless without routes.
- **Logistics → Warfare:** routes are the thing wars attack, and armies run on the same freight network.
- **Warfare → Factory:** units are manufactured goods; losing a war costs production, never buildings.
- **Territory → Economy:** control cuts freight costs and sets tariffs, feeding back into margins.
- **Economy → Multiplayer:** strategic-resource asymmetry and demand saturation make trade mandatory.
- **Multiplayer → Charters → Warfare → Territory → Economy → Factory.** The loop closes.

Remove any one system and at least two others lose their point. That is the test this design was built to pass.

---

## 37. MVP

### An honest technical note first

The full design above describes a persistent, server-authoritative MMO. That is not achievable as a single-file browser artifact with PeerJS — P2P networking has no authoritative host, no persistence, and no defense against a modified client, which are exactly the three things the economy and war systems depend on. Anyone claiming otherwise is describing a game that will be broken within a week of release.

So the MVP splits the design honestly into two phases: **what is fully buildable now in your usual single-file stack**, and **what genuinely requires a backend**, flagged as such rather than faked.

### MVP scope — "BELTLANDS: Kettleford" (single-file HTML, Three.js r128, PeerJS, WebAudio)

**In scope, fully working:**

1. **Isometric-ish 3D factory grid**, single plot, 32×32 tiles, orbit/pan/zoom camera.
2. **12 buildings:** Hand Drill, Powered Drill, Bloom Smelter, Blast Furnace, Coke Oven, Press, Lathe, Assembler Mk1, Coal Boiler, Steam Turbine, Crate, Loading Dock.
3. **Belts:** three tiers with real item-on-belt movement, splitters, mergers, filter gates. Item movement is the visual soul of the game — it must be actually simulated and rendered, not abstracted.
4. **Power grid:** generation, draw, poles with range, brownout scaling.
5. **Production chains:** Ironstone/Copperstone/Coal/Limestone → Ingots → Plate/Gear/Wire → Machine Frame. Four raw, nine intermediate, one Tier-3 good. Enough for real ratio puzzles.
6. **Economy v1:** spot market with per-item demand saturation and recovery, plus city contracts with rate-based fulfillment.
7. **Tech tree v1:** ~35 nodes across three branches (Metallurgy, Power, Automation), driven by Research Data from a Lab.
8. **Flow Lens overlay** — non-negotiable, it is what makes the game legible.
9. **Blueprint copy/paste/stamp** within the session, plus export/import as a code string.
10. **Second base (one only)** on a simple world map, with a Truck Convoy route between them. This proves the logistics layer without needing the full map.
11. **Save system:** localStorage plus export/import of a save string.
12. **PeerJS co-op:** 2–4 players, host-authoritative, sharing one plot with per-player build permissions. Host is the simulation authority. This is genuinely fun and is the correct multiplayer scope for a P2P build.
13. **WebAudio:** synthesized belt hum, smelter roar, machine placement clicks, contract-complete chime. Layered ambience scaled by factory throughput — a factory that sounds busy is enormously satisfying.
14. **Dark terminal-industrial presentation:** monospace UI, bone/amber/rust palette, no emoji, readouts styled like plant control panels.

**Deliberately out of MVP scope:** warfare, Charters, territory, the full 8-region map, futures, espionage, more than two bases, persistent economy across sessions and players.

**MVP success test:** a new player reaches automated iron in under 6 minutes, hits their first bottleneck by 12, and can play 90 minutes without running out of clear goals. If ratio-solving is fun with 12 buildings, it will be fun with 60. If it is not, no amount of warfare will rescue it.

### Roadmap

**Phase 1 — Foundation (MVP above).** Prove the 30-second loop. Ship single-file, offline-capable, with PeerJS co-op.

**Phase 2 — Depth.** Expand to 30+ buildings, fluids and pipes, the full six-branch tech tree, workers and Haze, Tier 3 chains (electronics and chemicals), rail as a second freight mode, and three bases. Still single-file, still local. This is where the game becomes genuinely deep for solo play, and it is a complete, shippable product on its own — a very strong offline factory game.

**Phase 3 — Real multiplayer backend.** The unavoidable step. A lightweight authoritative server (Node + WebSocket, one process per world, 1 Hz economic tick, Postgres or SQLite persistence) holding all production, inventory, and market state. Client becomes a renderer. This unlocks: shared persistent economy, the order book, player contracts, Reputation, and 20–40 concurrent players per world. Everything in the design that matters socially depends on this phase and nothing before it.

**Phase 4 — World and territory.** Full eight-sector map, Regions and Influence, neutral cities with real demand curves, strategic resources, chokepoints and tariffs, Charters with shared treasuries and share dividends, alliances and diplomacy states.

**Phase 5 — Conflict.** Sabotage, then Raids, then full Wars: war bonds, muster windows, combat windows, Field Objectives, supply-limited unit stacks, interdiction, peace terms. Ship the anti-grief systems *before* the first combat feature, not after — the protections must exist on day one of PvP or the community forms bad habits you can never undo.

**Phase 6 — Live game.** Seasons, world events, mega-contracts, the Orbital Program, Grand Projects, blueprint marketplace, cosmetics and season pass, Peaceful and Private worlds, mobile-friendly touch layout.

**Phase 7 — Longevity.** Player-run exchanges, futures, vassalage, cross-season history and monuments, spectator and replay tools for war campaigns, community tournaments.

The sequencing principle throughout: **never ship a conflict system before the economy it is supposed to be fighting over is genuinely worth fighting for.** A war over a boring economy is just griefing with extra steps.
