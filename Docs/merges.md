# Arsenal merges, round 2 (proposed 261019)

The fork defines 128 research projects across every supported mod (Ferny_Arsenal tab, VFE Tribals' Basics tab and VFE Pirates' tab). This round proposes 23 further merges: 7 that need no decision beyond a yes (part A) and 16 that each move something one step earlier, touch Medieval Overhaul, or mix prerequisites from different mods (part B). Approving every row would take the fork from 128 to 101 definitions (part A alone: 121).

Rules applied (Docs/RimWorld/ProgressionLESS.md in Projects): one era and one tab per group; cost of the most expensive member; strictest bench; prerequisites every member shares, otherwise the survivor's, with each member's other prerequisites moved onto its own items; `MayRequire` = mods every member needs, `MayRequireAnyOf` = the rest. The first member listed keeps its defName.

Each member keeps its patches in the load folder it already uses; only the project definition moves into `Common/Defs/MergedResearch.xml`. No item changes load folder, so the combination tables only list the mods that decide whether the merged project and each member's items exist.

**Genesis view not filled in.** Steam (api.steampowered.com, steamcommunity.com) is blocked from the cloud session, so the Genesis pack (collection 3798004429) couldn't be read. The "Unlocks" column is the full run. Run the Genesis check locally before applying, or allow those hosts for the session.

Status column: blank = waiting for review; write yes or no.

## A. Clear merges (no member needs another, no Medieval Overhaul content)

| # | Merged project | Members (era, cost) | Cost, bench | Prerequisites | Exists when | Unlocks (full run) | Notes | OK? |
|---|---|---|---|---|---|---|---|---|
| A1 | artillery and mortar shells | `Ferny_Artillery` artillery (Industrial, 700), `Ferny_SmokeShell` mortar shells (Industrial, 400) | 700, none | Mortars (shared) | always | field gun, VFE Security artillery, handheld mortar; smoke, incendiary, tar and tox shells | Smoke and incendiary shells keep their launcher prerequisites on the items. | |
| A2 | shotguns | `Ferny_PumpShotgun` shotguns (Industrial, 500), `Ferny_MakeshiftShotgun` makeshift shotgun (Industrial, 250) | 500, none | Gunsmithing | always | pump, double-barreled, repeating, auto and rubber shotguns, shotgun turrets, charge shotgun; makeshift shotgun | `VWE_MakeshiftWeapons` moves onto the makeshift shotgun's recipe. The makeshift shotgun now also waits for Gunsmithing, like the makeshift SMG, rifle and LMG already do. | |
| A3 | heavy gun turrets | `Ferny_MinigunTurret` multi-barrel turrets (Industrial, 900), `Ferny_DoubleAutocannonTurret` double autocannon turret (Industrial, 1000) | 1000, hi-tech bench | Heavy turrets (shared) | VFE Security | minigun turret, anti-air turret, minigun complex, double autocannon turret | `MultibarrelWeapons` moves onto the three minigun buildings. | |
| A4 | military melee weapons | `Ferny_CombatKnife` (Industrial, 250), `Ferny_ArcWrench` arc wrench (Industrial, 300) | 300, none | Knife | VE Weapons, Geist or Half Foot | combat knife, shovel, baton, high-frequency blade, arc wrench | `Machining` moves onto the arc wrench recipe. | |
| A5 | heavy warcasket sets | `Ferny_HazardWarcaskets` (Industrial, 1200), `Ferny_ShockWarcaskets` shock warcaskets (Industrial, 1200) | 1200, hi-tech bench | Warcasket sets | VFE Pirates | hazard, barrage and shock warcaskets (body, helmet, shoulders) | VFE Pirates tab. `VFEP_SpecialisedWarcaskets` moves onto the shock parts, which now also wait for warcasket sets. | |
| A6 | spacer warcasket weapons | `Ferny_WarcasketSunburnCannon` (Spacer, 1600), `Ferny_WarcasketEltexGreatsword` (Spacer, 1200) | 1600, hi-tech bench | Spacer warcasket weaponry | VFE Pirates and (Eventide or Eltex Weaponry) | sunburn cannon, eltex greatsword | `EW_EltexWeaponry` and `VFEP_WarcasketWeaponry` move onto the greatsword, which now also waits for spacer warcasket weaponry. | |
| A7 | longrifles | `Ferny_LaserpulseLongrifle` (Spacer, 2400), `Ferny_PrecisionLongrifle` (Spacer, 1200) | 2400, hi-tech bench | Charged shot, Precision rifling | Venators | laserpulse longrifle (also needs Spacer Arsenal), precision longrifle | `Ferny_SniperRifle` moves onto the precision longrifle recipe, which now also waits for charged shot. | |

Combinations for part A (each row: the deciding mods, then what exists):

- A1: none. The merged project always exists; each item is there when its mod is.
- A2: VWE Makeshift on: merged project with the makeshift shotgun. Off: merged project without it.
- A3: VFE Security on: merged project. Off: neither member existed before, nothing changes.
- A4: any of VE Weapons, Geist, Half Foot on: merged project with that mod's items. None: nothing, as before.
- A5: VFE Pirates on: merged project. Off: nothing, as before.
- A6: VFE Pirates and Eventide: sunburn cannon. VFE Pirates and Eltex Weaponry: greatsword. Both: both. VFE Pirates alone: nothing (the project carries `MayRequireAnyOf`).
- A7: Venators alone: precision longrifle. Venators and Spacer Arsenal: both.

## B. Needs your call

Rows marked "earlier" contain a member that needed another member, so merging moves it one step earlier. The middle step disappears; everything still waits for its era and its other prerequisites.

| # | Merged project | Members (era, cost) | Cost | What changes | Exists when | OK? |
|---|---|---|---|---|---|---|
| B1 | bolt-action and hunting rifles | `Ferny_BoltActionRifle` (Ind, 500), `Ferny_LeverActionRifle` hunting rifles (Ind, 400) | 500 | Earlier: hunting rifles no longer wait for the bolt-action rifle. | always | |
| B2 | grenades | `Ferny_FragGrenades` (Ind, 400), `Ferny_SmokeGrenades` smoke and tear gas grenades (Ind, 300) | 400 | Earlier: smoke, tear gas and stun grenades no longer wait for frag grenades. | always | |
| B3 | launchers and flamethrowers | `Ferny_SmokeLauncher` (Ind, 400), `Ferny_IncendiaryLauncher` (Ind, 500), `Ferny_TearGasLauncher` (Ind, 400, VWE Non-Lethal), `Ferny_Flamethrower` (Ind, 500, VE Weapons) | 500 | Earlier, two steps for the flamethrower (smoke, then incendiary launcher). Saves 3. Tear gas launcher keeps the smoke grenades prerequisite on its item. | always | |
| B4 | rocket launchers | `Ferny_RocketLauncher` (Ind, 700), `Ferny_TripleRocketLauncher` heavy rocket launchers (Ind, 1200), `Ferny_SwarmMissileLauncher` (Ind, 1000, VWE Heavy Weapons) | 1200 | Earlier: triple and doomsday launchers and the swarm launcher no longer wait for the rocket launcher. Saves 2. Prerequisites include `VWE_HeavyWeapons`, which Combat Extended removes (already handled by RemovedResearchPrerequisites.xml). | VE Weapons | |
| B5 | PDWs and bullpups | `Ferny_PDW` (Ind, 900), `Ferny_BullpupDMR` (Ind, 1100) | 1100 | Earlier: bullpup DMR. | VWE Quickdraw | |
| B6 | grenade launchers | `Ferny_GrenadeLauncher` (Ind, 600), `Ferny_GasGrenadeLaunchers` (Ind, 800, Biological Warfare) | 800 | Earlier: the seven gas grenade launchers. | Vanilla Arsenal, VE Weapons or Biological Warfare | |
| B7 | gun turrets | `Ferny_ArmoredTurret` (Ind, 800), `Ferny_LargeCaliberShotgunTurret` improved shotgun turrets (Ind, 1000) | 1000 | Earlier: Ancient Mining Industry's large and improved shotgun turrets. Raises gun turrets from 800 to 1000 and adds the hi-tech bench for all ten gun turrets. | any member mod | |
| B8 | anti-materiel rifles | `Ferny_UraniumSlugRifle` (Ind, 1600, VWE Heavy Weapons), `Ferny_AntiMaterielRifle` (Ind, 1000, VE Weapons) | 1600 | Not a dependency, but no shared prerequisite: uranium slug keeps `SniperTurret`, and the AMR recipe gets `VWE_HeavyWeapons` and `PrecisionRifling`. The AMR then also waits for `SniperTurret`, from another mod. | VE Weapons or VWE Heavy Weapons | |
| B9 | black powder guns | `Ferny_Cannon` (Med, 500), `Ferny_Arquebus` matchlock guns (Med, 600), `Ferny_Flintlock` (Med, 500) | 600 | Earlier: matchlocks no longer wait for cannon (through `VFEM2_Matchlocks`), flintlock no longer waits for matchlocks. Saves 2. The cannon patch that rewrites `VFEM2_Matchlocks`' prerequisites needs a hand fix. | VFE Medieval 2 | |
| B10 | maces | `Ferny_Mace` (Med, 150), `Ferny_HeavyMace` (Med, 150) | 150 | Earlier: heavy maces. The warhammer's Heavy Maces/Maces load folders would collapse into one. Medieval Overhaul: both folders are off with it, and MO's own maces keep ferny's tiers. | always | |
| B11 | swords | `Ferny_Gladius` (Med, 150), `Ferny_Longsword` swords (Med, 250) | 250 | Earlier: swords. **Medieval Overhaul effect:** MO's fencing and noble swords move one step earlier. | always | |
| B12 | axes | `Ferny_Hatchet` (Neo, 150), `Ferny_Axe` (Neo, 100) | 150 | Earlier: axes. **Medieval Overhaul effect:** MO's hatchet, woodcutter's axe and Roxmont war axe move one step earlier. | always | |
| B13 | knives and smithed blades | `Ferny_Knife` (Neo, 100), `Ferny_Spear` smithed blades (Neo, 150) | 150 | Earlier: spear, ikwa, cleaver, fungal staff, pike and halberd no longer wait for knife (Smithing stays on them). **Medieval Overhaul effect:** MO's butcher cleaver. Gladius and combat knife would then point at the merged project. | always | |
| B14 | charge lances | `Ferny_ChargeLance` (Spa, 1500), `Ferny_CoilLance` lance rifles (Spa, 2200) | 2200 | Earlier: coil lance and charge lance rifle. Raises the vanilla charge lance from 1500 to 2200. | always | |
| B15 | plasma weapons | `Ferny_PlasmaBlaster` (Spa, 1600), `Ferny_NeutronStreamer` (Spa, 2200) | 2200 | Earlier: neutron streamer. | Spacer Arsenal | |
| B16 | beam weapons | `Ferny_BeamRepeater` (Spa, 1800), `Ferny_GraserCannonComplex` (Spa, 2200) | 2200 | Earlier: graser cannon complex (`HeavyTurrets` stays on it). | Odyssey and Biotech | |

## Not proposed

- Flamebow: waiting on ferny (Open items in the playbook).
- Tier pairs built in round 1 (charge pistols then charge SMGs; ion, impact, gauss, laser, salvaged laser and pulse pairs; swords then great swords; the mace and axe ladders). Merging those collapses deliberate stages within an era.
- Medieval Overhaul's own mace projects (two-handed maces, military maces, heavy military maces, two-handed flanged mace): kept on ferny's tiers.
- Singletons with no same-era theme partner: searchlight, ammunition logistics, compound bow, bear trap, molotov cocktails, fire bombs, string instruments, platform, ARC rifle, charge bow, twin minigun backpack, spacer IEDs, rawhide rack, trench.

## Applied

- **261021, Bret's request:** tribal ranged weapons (`Ferny_Sling`) folded into VFE Tribals' `VFET_Bow`, relabelled "ranged weapons". Both cost-and-prerequisite checks hold: bow costs 70 (sling 15) and both needed only `VFET_Weapons`, so nothing unlocks sooner. Slings (VWE Tribal, Roo's Minotaur) and throwing shards now need ranged weapons. Every folder that pointed at `Ferny_Sling` loads only with VFE Tribals, so `VFET_Bow` always exists there. Megafauna bows now need only ranged weapons (they needed both). No Medieval Overhaul content involved. Relabel and description are two load-time operations on `VFET_Bow` by defName. 128 -> 127 definitions.
