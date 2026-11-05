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
- The instrument faces (version 0.2.0, `instruments` in `skin.json`): sky and ground colours, tape and
  box fills, borders and text, and the six colours that carry a meaning on the primary flight display,
  plus type-size multipliers for the tapes, boxes, data bar, and mode annunciations.

### Colour meanings

The engine requires each meaning colour to stay in its hue family, so a skin cannot swap them. The
meanings follow the pilot's guide (flight instruments, section 2.1, and the AFCS status box, 9.1):

| Role | Used for | Value |
|---|---|---|
| cyan | selected heading, selected altitude and their bugs, the baro setting, the standby frequency | `#00d8e0` |
| magenta | flight director command bars, trend vectors, GPS course and bearing, data bar values | `#e040e0` |
| green | active autopilot and flight director modes, the active radio frequency, a valid VOR or localizer | `#3ddc4a` |
| white | scale marks, armed modes, unselected values | `#f5f5f5` |
| yellow | the aircraft symbol, cautions, a flashing disconnect, the Messages label | `#f5d90a` |
| red | failure flags, airspeeds above the never-exceed speed | `#ff3b30` |

### The CAS window, trim and flap indicators, and the FPL page

These need no palette or label entries of their own: they use the roles above, so a skin that
restyles those colours restyles them too, and the same contrast rules apply.

| Element | Roles used |
|---|---|
| CAS window (crew alerting messages) | box fill and border for the window, **red** for warnings (the border turns red while a warning is active), **yellow** for cautions, **white** for advisories; the text size follows the `annunciation_text` multiplier |
| Flap and elevator trim position indicators | box fill and border, **white** for scale marks, pointers, and the DN, UP, and degree labels, **green** for the trim scale's neutral mark |
| FPL page (touch flight-plan editing) | the chrome palette (`bezel_trim`, `key_text`) for rows, selection, and the Activate Leg, Insert Before, Insert After, and Remove buttons; the leg being flown is drawn in the engine's fixed magenta |

The unit's own labels are the engine's, in plain words (Activate Leg, Insert Before, Insert After,
Remove), so the `labels` section has no entry for them.

Text on a tape or box must have at least 4.5:1 contrast against its fill, and a meaning colour at
least 3:1 against the box fill; the engine rejects the whole skin otherwise and shows the built-in one.

## What it does not change

Behaviour, and where things sit. Which page a knob selects, what BACK does on a press or a hold, how
the split screen works, and the position and size of every instrument and box are the engine model's
and are covered by its tests. A skin cannot move a box.

## Using it

Copy this directory into the engine's `skins/` folder beside `packs/`, or set
`FLIGHTCRAFT_SKINS_DIR` to its parent. The Sling 2 pack recommends it by id
(`landscape-touch-efis`), so it is used automatically when installed and the pilot has not chosen
another skin in Settings.

Licence: Apache-2.0 (repository `LICENSE`). Font: SIL OFL 1.1 (`fonts/OFL.txt`).
