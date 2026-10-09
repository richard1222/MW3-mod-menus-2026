# Call of Duty: Modern Warfare 3 — PS3 Mod Menus (2026 Guide)

A definitive, credit-everyone guide to **Modern Warfare 3 (2011, IW5 engine) mod menus on the PlayStation 3** — patch compatibility, CFW/HEN support, install paths, download links, and how they were built.

> ⚠️ **Read-only research.** Links are documented as found; hosts die. Where a link is gone, the status is marked honestly.
> Cheating in public matchmaking will get your account banned. Mod in private matches.

---

## Contents

1. [Quick Summary](#quick-summary)
2. [Title Updates & Patch Compatibility](#title-updates--patch-compatibility)
3. [Title IDs](#title-ids)
4. [Why MW3 PS3 Is SPRX-Dominant (Not patch_mp.ff)](#why-mw3-ps3-is-sprxdominant-not-patch_mpff)
5. [SPRX Mod Menus — Catalog](#sprx-mod-menus--catalog)
6. [RTM / PC-Tool Menus](#rtm--pc-tool-menus)
7. [GSC Menus (Infinity Loader)](#gsc-menus-infinity-loader)
8. [Spec Ops / Campaign Menus](#spec-ops--campaign-menus)
9. [Menu Packs & Loaders](#menu-packs--loaders)
10. [Open-Source Projects](#open-source-projects)
11. [Installation](#installation)
12. [CFW vs HEN vs DEX/CEX](#cfw-vs-hen-vs-dexcex)
13. [How They Were Built](#how-they-were-built)
14. [Unverified Menu Names](#unverified-menu-names)
15. [Sources & Threads](#sources--threads)

---

## Quick Summary

- **Final title update: 1.24** — every menu worth using targets 1.24.
- **MW3 on PS3 is modded with SPRX menus + modded EBOOTs, NOT patch_mp.ff.** MW3's `patch_mp.ff` is RSA-signed and contains no GSC scripts, so the WaW/MW2 patch-swap workflow does not apply.
- **Most SPRX menus require DEX firmware** (they ship with debug EBOOTs). CEX/HEN support is limited.
- **Install pattern:** modded `EBOOT.BIN` → `/dev_hdd0/game/[TITLE_ID]/USRDIR/`, menu `.sprx` → `/dev_hdd0/tmp/`.
- US title ID: **BLUS30838**. EU title IDs: **BLES01428** (confirmed), **BLES01433** (reported).
- Jiggy v4 is a **Black Ops 2** menu — there is no known MW3 version of Jiggy.

---

## Title Updates & Patch Compatibility

| TU | Status | Notes |
|----|--------|-------|
| **1.24** | ✅ **Final** — the one to be on | Every menu below that still matters targets 1.24 |
| 1.23 | ⚠️ Obsolete | Some older SPRX menus were built for it; most were updated |
| 1.22 and earlier | ❌ Historical only | 3.55-era CFG mods existed for patch 1.02 via backup managers |

**1.24 confirmed as final** via:
- MP1st reporting on the final title updates ("title update 24… adjustments to matchmaking")
- `erfg12/PS3-Cheats` netcheat tables built for v1.24
- `setsid/ps3-tools` confirmed working on real hardware (MW3 BLES01428, TU 1.24)

> Unlike WaW/MW2, MW3 menus are **not** patch_mp.ff swaps — the title update only matters for memory offsets inside the SPRX, not for a file you replace. A 1.23 SPRX will usually black-screen or crash on 1.24.

---

## Title IDs

| Region | Title ID | Status |
|--------|----------|--------|
| US | **BLUS30838** | ✅ Confirmed (SerialStation DLC content IDs, RPCS3 threads, multiple NGU/ConsoleCrunch threads) |
| EU | **BLES01428** | ✅ Confirmed (ps3-tools tested on hardware, NGU threads) |
| EU | **BLES01433** | ⚠️ Reported in NGU CFG-mod threads, less documented |
| EU | BLES01443 | ❌ **Unverified** — could not confirm this ID exists for MW3 |

Install paths below use BLUS30838; substitute your region's ID.

---

## Why MW3 PS3 Is SPRX-Dominant (Not patch_mp.ff)

On WaW and MW2, mod menus were `patch_mp.ff` files — unsigned fastfiles full of GSC scripts you could edit, repack, and drop in. MW3 broke that workflow twice:

1. **The PS3 `patch_mp.ff` is RSA-signed.** As BuC-ShoTz documented on NGU: the extracted file is `patch_mp.zone`, and *"there is a rsa signature in the ff, which means the self is going to have to be modded, in order to run a custom patch."* You cannot repack a working custom patch without Sony's RSA key.
2. **The patch contains no GSC scripts anyway.** ("…but there isnt gsc's either, lol" — same thread.)

So the scene moved to **SPRX plugins + modded EBOOT.BIN**: native C/C++ code injected into the running game, paired with a debug (DEX) EBOOT that loads the SPRX from `/dev_hdd0/tmp/`. That is why nearly every entry below is an `.sprx`, and why DEX is the norm.

---

## SPRX Mod Menus — Catalog

Every menu is credited to its creator. "1.24" means built for the final title update.

### Multiplayer SPRX menus

| Menu | Version | Creator | Patch | Notes | Link / Status |
|------|---------|---------|-------|-------|----------------|
| Virtual Energy | v2.3 / v3 | **OLDSCHOOLMODZ** (OLDSCHOOLMODZHD) | 1.24 | DEX required; hosted by KILLSAGAINLeader | [ConsoleCrunch thread](https://consolecrunch.com/threads/mw3-1-24-sprx-menu-virtual-energy-download.20924/) — download via adf.ly (likely dead) |
| Evolution | — | mrcallumx11 (showcase) | 1.24 | All-clients + "unfair aimbot" | [YouTube showcase](https://www.youtube.com/watch?v=IquJY-0utDw) — download link dead (adf.ly) |
| Crystalized | — | **MonstarModz** (recorder/host) | 1.24 | — | [YouTube showcase](https://www.youtube.com/watch?v=vGezuQ7lQug) — no download listed |
| Eternal Engine | — | Virus Mike (showcase) | 1.24 | Works on CFW (Evilnat/D-Rex) **and HEN** — install tutorial needs no PC/USB | YouTube showcase, login-gated details |
| Aftermath | — | **SouthSideModder** | — | Called "BEST MW3 SPRX" by poster KRYPTON | [ConsoleCrunch thread](https://consolecrunch.com/threads/mw3-aftermath-sprx-best-mw3-sprx.18126/) — MediaFire link (status unknown) |
| Black Genesys | — | **Kiwi Modz** | 1.24 | Open with D-Pad Left + L1 | [ConsoleCrunch thread](https://consolecrunch.com/threads/mw3-1-24-mod-menu-black-genesys-by-kiwi-modz.25747/) |
| Prometheus | — | **UnholyTalontsi** | — | Rename SPRX to match your EBOOT (e.g. `MW3.sprx`) | [ConsoleCrunch thread](https://consolecrunch.com/threads/sprx-prometheus-by-unholytalontsi.28216/) |
| Snow Engine | — | — | — | Classic install example: DEX EBOOT + SPRX in `/dev_hdd0/tmp/` | NGU help thread documents the install |
| Arkadia Sprx Menu | — | Arkadia | — | — | In Se7enSins mega collection (login-gated) |
| Chaos_Cheats | — | — | — | — | In Se7enSins mega collection (login-gated) |
| Exodus | V1 | — | — | Freezing issues reported with some EBOOT combos | In Se7enSins mega collection (login-gated) |
| Exorcist | v1 (Host) / v2 (Non-Host) | **HostOnly** | 1.24 | Pre-game lobby + in-game SPRX | In Se7enSins mega collection (login-gated) |
| Fury | v2.3 by Zeam (updated) | Zeam | — | — | In Se7enSins mega collection (login-gated) |
| God Engine | v1.1 BETA | — | — | — | In Se7enSins mega collection (login-gated) |
| MatrixMods_MW3_Azza | — | Azza / MatrixMods | — | — | In Se7enSins mega collection (login-gated) |
| MW3 ArchieG Menu | — | ArchieG | — | — | In Se7enSins mega collection (login-gated) |
| MW3 ASP Engine | — | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 Chocos Modded EBOOT | — | Chocos | — | EBOOT-based, not SPRX | In Se7enSins mega collection (login-gated) |
| MW3 Ethical_Engine | V2 | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 FROST ENGINE | — | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 HwXc | — | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 Infinite SPRX | — | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 Inphnect Pak | — | — | — | — | In Se7enSins mega collection (login-gated) |
| MW3 Liberation | — | — | — | — | In Se7enSins mega collection (login-gated) |
| Eternal MW3 Free | — | — | — | — | In Se7enSins mega collection (login-gated) |
| XkzModding menu | — | **XkzModding** | 1.24 | DEX | YouTube showcase only |
| OStankyModz menu | — | **OStankyModz** | 1.24 | DEX EBOOT + SPRX | NGU black-screen help thread documents install |

> The Se7enSins "Ultimate PS3 Mod Menu, Package & Tools Mega Collection" thread (updated ~Sept 2026) hosts the largest single MW3 SPRX list. It is login-gated:
> https://www.se7ensins.com/forums/threads/release-ultimate-playstation-3-ps3-mod-menu-package-tools-mega-collection.1931291/

---

## RTM / PC-Tool Menus

RTM menus run on a PC and poke the PS3's memory over the network (TMAPI/CCAPI) — no files on the console.

| Menu | Creator | Patch | Requirements | Link / Status |
|------|---------|-------|--------------|----------------|
| Detox V3 (RTM) | AciphMods | 1.24 | **TMAPI only** (very old menu; works on CCAPI but "veryyyyy laggy"; many options freeze the console) | [YouTube showcase](https://www.youtube.com/watch?v=cTOXSTs45rM) — MediaFire link in description |

RTM notes:
- **TMAPI = DEX only.** CCAPI works on CEX CFW but is deprecated/buggy on modern firmware.
- PS3HEN does **not** support CCAPI at all (documented limitation); it does support PS3MAPI via webMAN.

---

## GSC Menus (Infinity Loader)

MW3 GSC scripting exists, but on PS3 it is injected at runtime with the **Infinity Loader** (a paid tool, infinityloader.com) rather than via patch_mp.ff — because of the RSA-signed patch (see above).

| Menu | Creator | Type | Source | Link / Status |
|------|---------|------|--------|----------------|
| IW5-EnCoReV16 | **CabCon** | Multiplayer GSC menu (IW5) | ✅ Open source | https://github.com/mcabcon/IW5-EnCoReV16 |
| MW3 SP GSC Mod Menu | **CF4_99** | Single-player GSC menu | Binary only (12.2 KB) | CabConModding thread 7755 — attachment live at time of research |
| Spec Ops GSC Mod Menu | **P!X** | Spec Ops GSC menu | Binary only (`Obelisk.rar`, 164.2 KB + fix) | [CabConModding thread 7668](https://cabconmodding.com/threads/call-of-duty-modern-warfare-3-spec-ops-gsc-mod-menu-by-p-x-download.7668/) |

CabCon also published **MW3 GSC variable documentation** (data types and meanings, e.g. `level.console` for PS3/Xbox/Wii detection) at cabconmodding.com — useful if you want to write your own: https://cabconmodding.com/tags/mw3-gsc/

> Infinity Loader is "quite expensive" (per CabCon). This is the main reason GSC menus are a footnote on PS3 MW3 — SPRX is free.

---

## Spec Ops / Campaign Menus

| Menu | Creator | Type | Notes | Link / Status |
|------|---------|------|-------|----------------|
| MW3-Invasion | **jordywastaken** | SPRX, modifies the **single-player executable** | ✅ Open source. Server-side menu usable by all players when you're host; local-client menu was on the todo list | https://github.com/jordywastaken/MW3-Invasion |
| PS3-MW3-SpecOps-ModMenu | **GuillaumeMrNiato** | Survival-mode mod menu | ✅ Open source (VS solution) | https://github.com/GuillaumeMrNiato/PS3-MW3-SpecOps-ModMenu |
| Simple SPRX (Special Ops) | **iTzzTrojan** (base: **DevOps**, offsets: **Mango_Knife**) | SPRX, DEX | Self/teammate godmode, unlimited ammo, rapid fire, all perks, visions, Spec Ops recovery (level 50, max kills, waves…), teleports. Open: SELECT. EBOOT.BIN → `/dev_hdd0/game/BLUS30838/USRDIR/`, `SpecialOps.sprx` → `/dev_hdd0/tmp/` | [ConsoleCrunch thread](https://consolecrunch.com/threads/mod-menu-special-ops-sprx-dex.21772/) — Mega download (status unknown) |
| Spec Ops Mod Menu + ESP | **Nexus** (Se7enSins verified seller) | Premium menu | God Mode, No Clip, UFO, unlimited sprint, speed/jump presets, save/load position, unlimited ammo, no recoil, kill-all-enemies, disable AI spawns, gravity/game-speed/FOV, fullbright, **Survival money** ($1k/$10k/$100k), squad controls, full **enemy ESP** (boxes, health bars, names, snaplines, radar, threat warnings). Offline/private use only | [Se7enSins release thread](https://www.se7ensins.com/forums/threads/mw3-spec-ops-mod-menu-cheats-esp-release.1932255/) (login-gated) |
| MW3 Spec Ops SPRX (1.24) | — | SPRX | Simple 1.24 Spec Ops menu | YouTube mirror — download via sh.st (dead) |

---

## Menu Packs & Loaders

| Pack | Creator | Contents | Link / Status |
|------|---------|----------|---------------|
| MW3 SPRX LOADER (2020) | **VENOMz YT** | **23** non-host/host menus + **3** Spec Ops menus, DEX/CFW | [YouTube showcase](https://www.youtube.com/watch?v=Ts5hfvNq1d8) — MediaFire link in description |
| MW3 XMB ModLoader | — | Install-as-PKG modloader: install from XMB, it installs the mod menu, shown working in-game | YouTube showcase only — **no download links provided** |

---

## Open-Source Projects

The only public MW3 PS3 menu sources found:

1. **[jordywastaken/MW3-Invasion](https://github.com/jordywastaken/MW3-Invasion)** — C++, SPRX modifying the SP executable. Server-side (host) menu; updated Aug 2023.
2. **[GuillaumeMrNiato/PS3-MW3-SpecOps-ModMenu](https://github.com/GuillaumeMrNiato/PS3-MW3-SpecOps-ModMenu)** — Survival-mode mod menu, Visual Studio solution.
3. **[mcabcon/IW5-EnCoReV16](https://github.com/mcabcon/IW5-EnCoReV16)** — GSC multiplayer menu source (needs Infinity Loader to inject on PS3).

Related tooling with MW3 relevance:
- **primetime43/CoD-FF-Tools** — the FF editor used for the WaW/MW2 guides. Repo title covers **CoD4, WaW, MW2 only**; one 2025 commit message claims "Supported multiple game versions and platforms (COD4, WAW, MW2, BO1, MW3, BO2)" — MW3 support is **unverified**, and since MW3 PS3 patches are RSA-signed, an FF editor is of limited use for MW3 regardless. https://github.com/primetime43/CoD-FF-Tools
- **FFManager** (online, NGU) — historically edited MW3 fastfiles, but per its author full editing was **Wii-only** for MW3/BO ("you can ONLY edit BO/MW3 on wii"). Not useful for PS3 MW3 patches.
- **OpenAssetTools** (Laupetin/JGalbss fork) — can inspect/unlink IW5 (MW3) fastfiles, used by `k8se10/mw32011ncp` to dump real aim-assist curves from `code_post_gfx.ff`. GSC scripts dump only as compiled `.gscbin` bytecode — no clean GSC recovery.

---

## Installation

### SPRX menus (the standard method)

1. Copy the modded **EBOOT.BIN** (usually a DEX/debug EBOOT shipped with the menu) to:
   `/dev_hdd0/game/BLUS30838/USRDIR/EBOOT.BIN` (back up the original first)
2. Copy the menu **`.sprx`** to `/dev_hdd0/tmp/` — **rename it to whatever the EBOOT expects** (commonly `MW3.sprx`; the release thread will say)
3. Launch the game (via multiMAN or XMB)
4. Open the menu with the combo in the release thread (varies: SELECT, D-Pad Left+L1, L2+R3, D-Pad Up+Square, LB+RB+D-Pad Up…)

Troubleshooting from real threads:
- **Black screen on boot** → wrong-region or CEX EBOOT on a DEX setup, or SPRX name doesn't match what the EBOOT loads. There should be exactly **one** EBOOT.BIN directly under `USRDIR/` — delete/overwrite strays.
- **Menu won't open** → try 720p output; some menus only render at 720p.
- **"Most eboots and SPRX menus require DEX PS3s** as they usually come with Debug Eboots… so make sure you are on DEX or the eboot wont load." (NGU)

### On HEN

SPRX menus built for DEX debug EBOOTs generally **do not work on HEN/CEX**. Options on HEN:
- Menus explicitly marked HEN-compatible (e.g. **Eternal Engine** per Virus Mike's tests: CFW Evilnat/D-Rex **and** PS3HEN 3.3.0)
- RTM poking via **PS3MAPI** (webMAN exposes `/setmem.ps3` / `/patch.ps3` web commands and `/loadprx.ps3` to load an SPRX in-game) — CCAPI is **not** supported on HEN
- GSC injection via Infinity Loader (paid)

### GSC menus

Requires **Infinity Loader** (paid, infinityloader.com) to inject the compiled GSC into the running game. Hold aim + knife to open (P!X Spec Ops menu).

---

## CFW vs HEN vs DEX/CEX

| Setup | SPRX menus | Notes |
|-------|-----------|-------|
| **CFW DEX** (e.g. Rebug D-Rex) | ✅ Best | Debug EBOOTs load; TMAPI works for RTM menus |
| **CFW CEX** (e.g. Evilnat CEX) | ⚠️ Partial | Only menus with CEX-compatible EBOOTs; CCAPI RTM is deprecated |
| **PS3HEN (CEX)** | ⚠️ Limited | No CCAPI; needs HEN-compatible menus (Eternal Engine confirmed); PS3MAPI via webMAN works |

DEX vs CEX is the single biggest compatibility gate — bigger than CFW vs HEN. **When a thread says "DEX required," it means it.**

---

## How They Were Built

- **SPRX menus** are native PPC C/C++ plugins built with the PS3 SDK (the MW2 scene's Zircon/SPRX bases are the template; e.g. EternalModz's open-source `Atlantic-MW2-SPRX` documents the PS3 4.75 SDK + Visual Studio build flow — the same pattern MW3 SPRX menus follow). They hook the game's functions and draw their own UI; offsets are per-title-update, which is why 1.24 builds are separate artifacts.
- **GSC menus** are script mods in Infinity Ward's GSC language (IW5 variant of the IW4 GSC from MW2). Documented at CabConModding; open example: `mcabcon/IW5-EnCoReV16`.
- **EBOOT mods** are patched debug executables that load the SPRX and often bypass signature checks.
- **RTM tools** are PC programs (C#/C++) that write to the PS3's RAM over TMAPI (DEX) or CCAPI (CEX CFW).
- There is **no MW3 equivalent of the WaW/MW2 patch_mp.ff GSC workflow** — RSA signing killed it.

---

## Unverified Menu Names

The following names were supplied as leads but **could not be verified as MW3 PS3 releases** in any public source (forums, GitHub, YouTube, Archive.org). They may be Xbox 360 menus, menus for other CoD titles, or misremembered names. They are listed here so nobody wastes time hunting ghosts:

Echelon · Destruction v4/v5 · Envy v3/v4 · Swaqqin v1/v2 · Apocalypse v2 · Fatality v2 · Reborn v2 · Extinct v3 · Venom v3 · Toxic v4 · Chaos v5 · Paradox v2 · Oblivion v2 · xC4 · xKiller · xLithium · xModz

Notes:
- **Jiggy v4** is by JiggyWitIt and is a **Black Ops 2** menu — no MW3 version is known (same correction as in the MW2 guide).
- **BLES01443** as an EU title ID is likewise unverified (confirmed EU IDs: BLES01428, BLES01433).
- If you have a working link for any of these on MW3 PS3, it belongs in the catalog above.

---

## Sources & Threads

- MP1st — MW3 title update 24 coverage (1.24 = final TU)
- NGU — "MW3 patch_mp.zone" by BuC-ShoTz (RSA signature finding); ".sprx mod menu file help" (install paths); "MW3 Black Screen after inserting a modded EBOOT plus SPRX menu" (DEX requirement); "mw3 mod menus?" ("Just use an sprx or an rtm menu")
- ConsoleCrunch — Virtual Energy, Aftermath, Black Genesys (Kiwi Modz), Simple SPRX Spec Ops (iTzzTrojan), Prometheus (UnholyTalontsi) threads
- Se7enSins — Ultimate PS3 Mod Menu/Package/Tools Mega Collection (MW3 section); Nexus Spec Ops + ESP release
- CabConModding — IW5-EnCoReV16 preview, P!X Spec Ops GSC menu, CF4_99 SP GSC menu, MW3 GSC variable docs
- GitHub — jordywastaken/MW3-Invasion, GuillaumeMrNiato/PS3-MW3-SpecOps-ModMenu, mcabcon/IW5-EnCoReV16, primetime43/CoD-FF-Tools, primetime43/cod-research, ate47/atian-cod-tools, k8se10/mw32011ncp, aldostools/webMAN-MOD
- ConsoleMods Wiki — PS3HEN install/limitations (no CCAPI); webMAN web commands (`/loadprx.ps3`, `/setmem.ps3`)
- YouTube — AciphMods (Detox V3 RTM), VENOMz YT (SPRX Loader 2020), Virus Mike (Eternal Engine), MonstarModz (Crystalized), mrcallumx11 (Evolution), KILLSAGAINLeader (Virtual Energy v2.3)

---

*Research compiled 2026-10-09. Link rot is aggressive in this scene — if a link is dead, the thread URL is still the right place to ask.*
