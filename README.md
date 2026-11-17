# Survivor Crafting Anywhere

**Version 1.0.2** · Ultimate ASI Loader plugin · Download: [survivor-crafting-anywhere-1.0.2.zip](survivor-crafting-anywhere-1.0.2.zip)
(or from [Releases](https://github.com/MicDrop7/Enshrouded-Survivor-Crafting-Anywhere/releases/tag/v1.0.2)) ·
Older: [1.0.0](survivor-crafting-anywhere-1.0.0.zip)

## What's new in 1.0.2

- Works when another mod or mod loader (for example Kiln) has already hooked the same game functions. Before, F5
  could do nothing and the log said "NOT fully ready".
- The log is now written next to the ini in the `Scripts` folder, and the last 5 runs are kept. The old
  `survivor-crafting-anywhere.log` in the game folder is no longer used and can be deleted.

## What it does

Press **F5** in any of your bases to open a rescued survivor's crafting menu: the Blacksmith, Carpenter, Alchemist,
Hunter, Farmer, Collector, Bard, Fisher, Ancient Researcher and so on. You no longer need to travel to their base, or
move them and give them a bed at every base.

It is the game's own crafting menu. The tabs along the top become your survivors. Switch between them with **Q / E**
or by clicking a tab. **Esc** closes the menu, and **V** still opens your own crafting as normal. The menu opens on
the last survivor you used.

### Inside or outside a base

By default the menu only opens while you are inside a base (any base, not just the survivor's). To use it anywhere
in the world, set `allowOutsideBase=true` in `SurvivorCraftingAnywhere.ini`. Outside a base, materials come from your
backpack only.

### How crafting works

- The craft is made by the survivor at their own base, so the crafting stations they need (Forge, Smelter, ...) must
  be at **their** base. The game shows which stations are needed and whether they are found.
- Materials come from your backpack and from the chests of the base you are standing in, the same as at your own
  crafting.
- Only survivors that are rescued and assigned to a base are listed. Assistants (Rochelle Anders, Aunt Braelyn, ...)
  are not listed separately: their recipes are under their survivor's tab. The Barber is not listed, because the
  Barber changes appearance and does not craft.

## Requirements

**Ultimate ASI Loader** by ThirteenAG (x64): <https://github.com/ThirteenAG/Ultimate-ASI-Loader/releases>

Put its dll (`dinput8.dll`, or `winmm.dll`) next to `enshrouded.exe`. Many mods use it, so you may already have it:
check for a `Scripts` folder next to `enshrouded.exe` with other `.asi` files in it.

## Installation

1. Extract the zip into the game folder, the one with `enshrouded.exe`, so that you have:
   ```
   ...\steamapps\common\Enshrouded\Scripts\SurvivorCraftingAnywhere.asi
   ...\steamapps\common\Enshrouded\Scripts\SurvivorCraftingAnywhere.ini
   ```
2. Start the game and join or start your world.
3. Go to one of your bases and press **F5**.

Only you need it. The server or host does not need the mod (tested on a dedicated server).

### Change the key

Open `Scripts\SurvivorCraftingAnywhere.ini` with Notepad and change the line `menuKey=F5`, for example to
`menuKey=F8`, `menuKey=Insert`, `menuKey=Num7` or `menuKey=Ctrl+K`. The full list of key names is in the file. Pick a
key the game does not already use. Restart the game after a change.

## Settings (`SurvivorCraftingAnywhere.ini`)

| Setting | Meaning |
|---|---|
| `enabled` | `true` / `false` |
| `menuKey` | key that opens / closes the menu (default `F5`) |
| `allowOutsideBase` | `true` = the menu also opens outside bases (default `false`) |
| `diagnostics` | `true` = write survivors, tab switches and crafts to the log |
| `dumpKey` | troubleshooting: key that writes the survivor list to the log |

## Check it worked

If F5 does nothing, open `Scripts\survivor-crafting-anywhere.log` (next to the ini; the last 5 runs are kept as
`.1.log` to `.5.log`). The first lines should end with
`ready (menu key F5, ...)`.

- "NOT fully ready" or "ERROR" lines mean a game update changed something and the mod needs updating.
- Survivors appear a few seconds after you join a world. Until then F5 does nothing and the log says so.
- Outside a base, F5 does nothing unless `allowOutsideBase=true` (the log says so too).

## Compatibility

Works alongside Creative Mode and Smart Workshop, and is built to work with other mods that hook the same game
functions (such as mods loaded through Kiln). Another mod that also changes the main menu's top tabs may conflict.

## Uninstalling

Delete these from the `Scripts` folder:

- `SurvivorCraftingAnywhere.asi`
- `SurvivorCraftingAnywhere.ini`
- `SurvivorCraftingAnywhere-last.txt` (remembers the last survivor)
- `survivor-crafting-anywhere*.log` (logs)

The mod changes nothing in your world or character save.

## Credits

Ultimate ASI Loader by ThirteenAG: required, not included.

---

More Enshrouded mods by MicDrop7: [Enshrouded-Game-Mods](https://github.com/MicDrop7/Enshrouded-Game-Mods).
