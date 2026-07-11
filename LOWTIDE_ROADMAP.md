# LOW TIDE — Demo to Steam Roadmap
*Prepared for J. Lall / JLall207 · July 2026 · Companion to the v0.49 demo*

The demo is a finished proof: three-route encounters, a flag-driven town, a hidden
layer with a real payoff. The full game is not "more demo" — it is the demo's
promises kept: the trapdoor, the lighthouse interior, and February.

---

## 1 · Storytelling

**Lock the three-act spine before writing anything else.**
- **Act I — January (the demo, polished).** The three voices, the door, the seam.
- **Act II — The Mechanism.** Inside the lighthouse; under the cannery (the
  trapdoor pays off). The player learns *how* the town is held in January and
  who/what the SIGNAL is maintaining it for. New areas: lighthouse interior
  (vertical map — a first for the engine), the under-cannery, the frozen harbor
  itself at low tide (walk the exposed seabed — the title becomes a place).
- **Act III — February.** The letter's promise. The town gets a choice, and the
  choice is shaped by the player's cumulative route behavior.

**Route architecture scales to endings.** Keep pacifist / violent / weird per
encounter, and derive endings from the *pattern*: mostly-spare, mostly-fight,
all-weird (true ending), plus one hidden ending gated on the full anomaly set.
Build a **consequence matrix** doc now: every flag → every downstream payoff.
The demo already proves the machinery; the doc keeps 10× the content coherent.

**Write a story bible (private).** For each NPC: their secret, their want, and
what each route does to them in Act III. Decide what the SIGNAL *is* — commit
privately even if the game never states it; consistent mystery reads as depth,
improvised mystery reads as noise.

**Discipline that already works — keep it:**
- One meta-channel per act (typed-name, real clock, epoch phone… ration them).
- The unread-story shimmer as universal visual language.
- Maine voice guide: the approved slang list, vocabulary over phonetics.

**Scope target:** 4–6 hr main path, 8–10 hr completionist. ~12–15 maps,
8–10 encounters, 3 boss-tier fights (each one a mechanical twist on the
box, Deltarune-style — puzzles in the arena, not just dodging).

---

## 2 · Code & Tech

**The one decision that gates everything: engine.**
- **Recommended: Godot 4 (2D).** Gamepad support, resolution/scaling, save
  management, Steamworks integration (GodotSteam), controller glyphs,
  localization, and web export — you keep a browser demo from the same project.
  GDScript is easy from your Java/JS base; C# is available if you want resume
  crossover. The current HTML file becomes your **playable design spec** — the
  port is mostly data translation, not redesign.
- **Viable alternative: stay JS.** Wrap in **Tauri or Electron** +
  steamworks.js. You keep your velocity, but you own gamepad support, scaling,
  save migration, and platform quirks by hand. CrossCode shipped this way; it
  is a road, just a lonelier one.
- **Decide with data:** 2-week spike — port ONE room + one battle to Godot.
  If it feels good, commit. Sunk-cost is not a factor; the content survives.

**Porting insurance (do this regardless, now):** extract all content from code
into data files — `maps.json`, `dialogue.json`, `encounters.json`, `flags.md`.
Content/engine separation is what makes any port cheap and any engine optional.

**Systems the full game needs that the demo lacks:**
- Cutscene scripting (NPC walk-to, camera pans, timed beats) beyond dialogue nodes.
- Settings menu: text speed, volume sliders per bus, screen-shake toggle,
  **photosensitivity mode**, key/gamepad remapping, font scale. (Accessibility
  is also a Steam review multiplier.)
- Save versioning + migration (players will carry saves across patches).
- Audio buses (music / sfx / ambience) and a real mixer.
- Juice layer: particles, screen shake, hit-stop — cheap, transformative.
- Steam hooks: achievements, cloud saves, rich presence.

**Testing as identity (SRE brand, resume gold):** formalize the audit scripts
from this project into repo CI — a GitHub Action that validates every portal,
NPC tile, dialogue reference, and flag edge on every commit, plus a headless
golden-path smoke test. Ship the game with a pipeline; write the devlog about it.

---

## 3 · Art & Audio

- **Art fork:** either commit *hard* to the string-grid aesthetic as a style
  (tighter palette ramps, 2–4 frame walk cycles, idle animations, weather —
  falling snow alone is worth a version) or budget a pixel artist
  (~$2–8k or rev-share for a game this size).
- **Highest-impact single art add: dialogue portraits.** Frame them as
  **Polaroids** — period-correct, distinctive, and it dodges the Undertale
  bust comparison entirely.
- **Audio:** the procedural engine is a legitimate identity ("the soundtrack is
  computed live; the SIGNAL is the composer"). For Steam polish, layer composed
  motifs on top — chiptune/ambient commissions run ~$50–150/track; 8–12 tracks
  covers the game. Keep the handshake as the leitmotif everywhere.

---

## 4 · Production & Business

- **Steam page ASAP — this is the #1 lever.** Wishlists accrue from *page
  publish*, not launch. $100 app fee (recoupable). Budget real capsule art;
  the capsule outsells screenshots.
- **Demo funnel:** browser demo (itch.io + your site) → Steam demo →
  **Next Fest** entry (free visibility spike, one shot per title — time it).
- **Legal checklist (recap, not-a-lawyer):** register copyright at/before paid
  publication; Maine LLC before revenue; trademark clearance search — "LOW
  TIDE" is a common phrase, so consider registering/shipping as
  **"LOW TIDE: A Gull Harbor Story"** for distinctiveness; keep AI-assistance
  records for USCO disclosure; PAGERSTORM is more distinctive and cheap to
  protect early.
- **Price/scope reality:** 4–6 hr narrative pixel RPG → **$9.99–14.99** zone.
  Solo, part-time: **12–24 months**. Set a content-lock date and honor it.
- **Marketing that fits you:** devlog on your own site (SEO + portfolio dual
  use); short-form clips of the meta moments — *the phone reading the player's
  real epoch seconds is the viral clip*; the Maine angle (local press loves
  local games); Reddit indie threads; Discord later, playtest circle first.

---

## 5 · Next 90 Days (concrete)

1. **Ship the demo publicly** — itch.io + site, with a feedback link. Tag v0.49.
2. **Engine spike** — one room + one battle in Godot 4; decide by data.
3. **Docs week** — story bible, consequence matrix, Maine voice guide.
4. **Data extraction** — content out of code, into JSON. (Porting insurance.)
5. **Steam prep brief** — capsule art direction, trailer beat sheet, page copy.
6. **Paperwork** — LLC filing + copyright registration queued for first revenue.

*The demo already does the hardest thing a demo can do: it makes a promise a
player wants kept. Everything above is just keeping it.*

— assembled with Claude · the help had help
