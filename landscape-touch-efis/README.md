# landscape-touch-efis

Public skin for FlightCraft's `landscape_touch_efis` display model: a 5:3 touch screen above one row
of physical controls (two dual-concentric knobs, NRST and DIRECT keys, a data-card slot, and MENU and
BACK keys).

Designed to match the layout and workflow of the Garmin G3X Touch 10.6-inch display for training;
not affiliated with or endorsed by Garmin. "Garmin" and "G3X" are trademarks of their owner and are
used here only to say which real unit this skin follows.

## What it changes

- Bezel, trim, key, and knob colours (`skin.json` palette).
- Key labels: NRST, DIRECT, MENU, BACK.
- The chrome font (Noto Sans, SIL OFL 1.1) for key labels, the page bar, SPLIT/FULL, and menus.

## What it does not change

Behaviour. Which page a knob selects, what BACK does on a press or a hold, and how the split screen
works are the engine model's and are covered by its tests. The instrument faces (tapes, attitude,
HSI, map) are drawn by the engine from FAA display conventions in every skin.

## Using it

Copy this directory into the engine's `skins/` folder beside `packs/`, or set
`FLIGHTCRAFT_SKINS_DIR` to its parent. The Sling 2 pack recommends it by id
(`landscape-touch-efis`), so it is used automatically when installed and the pilot has not chosen
another skin in Settings.

Licence: Apache-2.0 (repository `LICENSE`). Font: SIL OFL 1.1 (`fonts/OFL.txt`).
