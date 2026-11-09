# Proposed technical approach

This is a design direction, not a description of implemented components. Confirm Kodi APIs and the installed version before finalising it.

## Component boundaries

| Component | Responsibility |
|---|---|
| Kodi player and library | Decode/play media and expose playback, resume and library information. |
| Skin | Present programme choices, selection focus and simple playback/error views. |
| Small add-on, if required | Resolve a programme to an episode, coordinate playback and handle application-specific state. |
| Keymaps | Map real remote events to predictable actions in each window. |
| Helper configuration | Manage programmes, sources, recovery and intentional progress changes. |

Do not put episode-selection rules into duplicated skin expressions. Keep those rules separate from Kodi calls so they can be tested without a running GUI. Avoid introducing an external server or database unless a demonstrated requirement justifies it.

## Playback and state

Prefer Kodi's own resume information to competing bookmark stores. Inspect its actual persistence and completion behaviour before deciding what additional state is necessary. A small application store may track the last active episode for each programme, but ownership of each field must be documented.

Use stable programme identifiers and a defined episode-order rule. Never rely on a database row ID remaining identical after a library rebuild, a USB drive letter remaining unchanged, or lexicographic filenames putting episode 10 after episode 9.

The playback flow should separate choosing a candidate, confirming the file is available, requesting playback and observing playback outcome. A failed request is not successful viewing. Handle rapid repeated requests without starting overlapping operations.

If additional persistence is required, give it a schema version, validate it on load and use atomic replacement where supported. Preserve recoverable state on failure. Define what survives ordinary restart versus abrupt power loss; do not promise zero progress loss without testing it.

Keep existing originals and progress when rebuilding a library or deploying a new version. Changes to watched status, reset operations and migrations need deliberate handling and recovery.

## Skin strategy and licences

First assess how much the stock OSMC skin can achieve through configuration. A custom skin must have its own add-on ID so upstream updates cannot overwrite it.

Inspect the licence before copying any upstream skin code or assets. The inspected [OSMC skin Omega source](https://github.com/osmc/skin.osmc/tree/omega) uses CC BY-NC-SA 3.0; it cannot simply be relabelled as this project's MIT code. If adopted, retain its licence and attribution in a clearly identified component. Alternatively, implement an original skin and track the provenance of every asset.

The first implementation decision should record the chosen base and resulting licensing arrangement before importing source.

## Windows to OSMC

- Use an isolated Windows Kodi portable installation for development.
- Match the actual target's Kodi major version; prefer the same patch release when practical.
- Package the skin and any add-on with explicit versions and dependencies.
- Install target-appropriate dependencies; do not transfer platform-specific binaries.
- Transfer selected configuration and keymaps, then select and validate the USB source on OSMC.
- Rebuild the library using local metadata and artwork. Preserve progress through an explicitly tested migration if needed.

[Kodi's backup documentation](https://kodi.wiki/view/Backup) advises against restoring a whole data folder across operating systems. Use [special paths](https://kodi.wiki/view/Special_protocol) for Kodi-owned resources, and configure external media paths on the target. Check filename case on Linux.

## Remote and device operation

Test actual RF/IR/CEC events rather than assuming keyboard events are equivalent. Window-specific keymaps can override global mappings. OSMC's default Home and held-button behaviour must be reviewed and replaced where necessary; see its [remote guide](https://osmc.tv/wiki/general/osmc-remote---long-press-keymap-guide/).

TV input, power and volume are part of the delivered experience. A skin cannot suppress the television's own menus. Document the supported setup and its limits.

## Development sequence

1. Establish an isolated Kodi baseline and record versions.
2. Display a few original sample programme cards with remote-only navigation.
3. Prove local playback and per-programme resume using a tiny fixture library.
4. Implement and test completion/next-episode rules and failure handling.
5. Package the components and transfer them to Vero V.
6. Validate offline operation and recovery on the actual television.
7. Observe use, simplify where necessary, and publish a reproducible setup guide.

Use existing Kodi functionality before adding custom code. Add a helper only where configuration or a skin cannot meet the agreed behaviour reliably.
