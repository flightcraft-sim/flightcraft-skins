# flightcraft-skins

Display skin packs for the FlightCraft flight simulator. A skin pack changes how an installed
display looks (bezel colours, key and knob faces, short control labels, the chrome font, and the
instrument faces' palette and type sizes). It never changes behaviour or placement: pages, knobs,
menus, failure logic, and where every box and tape sits belong to the engine's display model.

Each skin is a subdirectory with its own `skin.json` manifest, `README.md`, and `ATTRIBUTION.md`.
Each skin names the real unit whose layout and workflow it follows only nominatively, to say what
it is for. None is affiliated with, endorsed by, or sponsored by that unit's manufacturer.

| Directory | Display model | Follows the layout and workflow of |
|---|---|---|
| `landscape-touch-efis/` | `landscape_touch_efis` | the 10.6-inch landscape touch display of a common experimental-aircraft glass system |

## Rules for every skin

- All artwork is drawn for this project. No manufacturer logos, no trademarks in the interface, no
  proprietary fonts, and no traced or copied graphics or icons.
- Geometry, placement, colour meanings, page and menu structure, and knob behaviour follow public
  documentation of the real unit, cited in the skin's `ATTRIBUTION.md`. Labels are short and
  functional (NRST, MENU, BACK).
- Fonts are open-licensed, with their licence text shipped beside them.

## Using a skin

The engine pins this repository and a commit in `bundled-skins.json` and lists the subdirectories to
bundle; `scripts/bundle-skins.py` copies only those into a build's `skins/` folder. For a local
checkout, point `FLIGHTCRAFT_SKINS_DIR` at a folder containing the skin directories. An aircraft
pack may recommend a skin by id; a pilot can pick any installed skin per display in Settings.

Licence: Apache-2.0 for the skins (see `LICENSE`). The bundled fonts keep their own licences.
