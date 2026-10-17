# Dino Survival

A first-person survival game that runs in the browser. Explore a world of trees, ponds and rocks, gather
resources, craft tools, trade jobs with villagers, and share the land with dinosaurs that mostly just want to be left alone.

**Play it:** https://keyek302.github.io/DinoSurvival/ (once GitHub Pages is turned on, see below)

> Works with a keyboard and mouse on a computer, and with on-screen touch controls on a phone or tablet. On a phone, play with it turned sideways.

## Controls

| Key | What it does |
| --- | --- |
| Click the screen | Start playing and capture the mouse |
| Mouse | Look around |
| W A S D | Move |
| Shift | Sprint (uses stamina) |
| Space | Jump (uses stamina) |
| C (hold) | Crouch and sneak |
| Left click or F | Punch (uses stamina) |
| E | Pick things up, or talk to a villager |
| Tab | Open and close the backpack and crafting list |
| 1 to 5 | Pick a hotbar slot |
| Right click or Q | Use the selected hotbar item (eat, place a bench) |
| Esc | Release the mouse |

In the backpack: click a slot, then another slot, to move or stack items. Shift-click uses an item. Right-click drops one.

If the mouse can't be captured (some embedded previews block it), the game falls back to click-and-drag to look around, and F to punch.

## Touch controls (phones and tablets)

Tap the start screen to begin. The game goes full screen where the browser allows it.

| Control | What it does |
| --- | --- |
| Hold and drag on the left side | Move (a joystick appears under your thumb) |
| Drag on the right side | Look around |
| Jump | Jump (hold) |
| Punch | Punch (hold to keep punching) |
| Sprint | Switch sprinting on and off |
| Crouch | Switch crouching on and off |
| Act | Pick things up, or talk to a villager |
| Use | Use the selected hotbar item (eat, place a bench) |
| Bag | Open and close the backpack and crafting list |
| Tap a hotbar slot | Choose that item |

In the backpack, tap an item to select it, then tap another slot to move or stack it, or use the **Use** and **Drop 1** buttons.
You can also tap the "Tap: ..." message that appears near the middle of the screen to do what it says.

On touch devices the world is a little smaller (fewer trees, rocks and dinosaurs) so it runs smoothly.
To try the touch layout on a computer, add `?touch` to the address.

## How it works

- **Gather:** punch trees for sticks and rocks for stones. A tree falls to a stump and a rock crumbles away when it runs out.
- **Craft:** make a Crafting Bench from sticks and stones, place it, and use it to craft a Stone Axe, Stone Pickaxe and Berry Tonic. Hold a tool on the hotbar for double yield.
- **Health and stamina:** sprinting, jumping and punching cost stamina. Hard falls hurt. Berries, tonics and dino meat restore you.
- **Dinosaurs:** six species wander the land (long-neck, three-horn, crested runner, raptor, T. rex and more). They never attack. They run when you get close, and you can sneak up by crouching. Hunting them drops meat, and new ones wander in later.
- **Village:** follow the dirt path to a small settlement with a campfire, huts and three villagers. Press E to take on jobs: fetch items or hunt dinosaurs for rewards.

## Run it on your computer

It is a single `index.html` with no build step. Because it loads Three.js from a CDN, you need an internet connection, and it is best served over http rather than opened as a file:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Put it on GitHub Pages

1. Make a new public repository (for example `DinoSurvival`) and upload `index.html` and `README.md`.
2. Go to **Settings**, then **Pages**. Set **Source** to **Deploy from a branch**, pick **main** and **/ (root)**, then **Save**.
3. After a minute or two the game is live at `https://YOURUSERNAME.github.io/REPOSITORY/`.

## Tweaking the game

Everything is in `index.html`. Some handy spots to search for:

- `DINO_COUNT` and `SPECIES`: how many dinosaurs there are, and their size, speed, health and skin.
- `trees.length <` and `rocks.length <`: how many trees and rocks are in the world (`isTouch` picks the lighter numbers on phones).
- `ITEMS` and `RECIPES`: items and what you can craft.
- `QUESTS`: the villagers' jobs and rewards.
- `BOUNDS`: how big the playable world is.

## Credits

Made with [Three.js](https://threejs.org/) (MIT license). Textures and models are drawn in code when the page loads, so there are no image files.
