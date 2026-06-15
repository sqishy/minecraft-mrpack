# Cobblemon Rally — auto-updating modpack

This repo hosts the [packwiz](https://packwiz.infra.link/) index for the **Cobblemon Rally** modpack.
Players who set it up once get every mod/config update automatically on their next launch — no
re-importing the modpack.

**Pack URL:** `https://sqishy.github.io/minecraft-mrpack/pack.toml`

## Player setup (Prism Launcher, one time)

1. Install the modpack normally once (import the `.mrpack`), or create a **NeoForge 21.1.233 / MC 1.21.1** instance.
2. Download **[packwiz-installer-bootstrap.jar](https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest)**
   and drop it in the instance's `.minecraft` folder (Prism: right-click instance → *Folder*).
3. Prism → right-click instance → **Edit** → **Settings → Custom Commands** → enable, and set
   **Pre-launch command** to:

   ```
   "$INST_JAVA" -jar packwiz-installer-bootstrap.jar -g -s client https://sqishy.github.io/minecraft-mrpack/pack.toml
   ```

That's it. Every time they hit **Play**, packwiz checks this repo and downloads only what changed.

> ⚠️ Everyone needs this — the custom mods register real blocks/content, so a client missing them
> can't join the server.

## Maintainer

The pack is generated from the source `.mrpack` by `gen_packwiz.py` and pushed by the `publishPack`
Gradle task in the Cobblemon GemCraft project (`deployServer` runs it automatically). Don't hand-edit
files here — they're regenerated.
