# Project brief

Agreed direction: 9 November 2026. Implementation status: not started.

## Purpose

Make it possible to enjoy familiar TV programmes from local USB storage with very little navigation. Success means comfortable viewing with an appropriate level of help, rather than exposing every feature of a media centre.

The motivating user is familiar with traditional television controls and finds channel up/down easier than complex menus. The chosen first prototype is nevertheless a small picture-based programme chooser with remembered playback. Test that assumption early; keep the option of carer-started playback.

## First-version interaction

1. After initial installation and configuration, the device starts Kodi and presents programme choices. A brief boot logo is acceptable; no unrelated launcher, profile chooser or sign-in should be needed for ordinary use.
2. Each programme has a recognisable picture, a short name and a stable position. Adding episodes must not reorder programme choices.
3. Arrows move an obvious focus indicator. OK starts watching without opening an information page or asking which episode to play.
4. Selecting a programme resumes its most recently active unfinished episode. If the previous episode was completed, it starts the next eligible episode in the configured order.
5. Each programme remembers its own progress when another programme is selected.
6. Play/Pause pauses and resumes. OK performs the same action during fullscreen video if supported by the final keymap.
7. Home stops playback, allows progress to be saved, and returns to programme choices. Back during playback does the same; Back at the programme screen stays there. These are first-prototype defaults to validate with the user.
8. After an episode ends, return to programme choices. Automatic next-episode playback is not a first-version requirement.
9. When a series is exhausted, retain its picture and offer a simple, deliberate way to watch again. Do not silently remove it or reset progress. The exact replay interaction remains to be tested.

The definition of 'completed' must be explicit and tested. Decide how Kodi's resume and watched status relate to reaching the credits, early stopping and naturally reaching the end before implementing selection logic.

## Carer/helper configuration

Provide a separate route to select the USB library, choose programme artwork and order, select an earlier episode, restart a programme, adjust subtitles and recover the installation. Normal viewing should not require entering a PIN or navigating those tools.

Changes to programme order or progress must be deliberate and reversible. Do not rename, move, transcode or delete original media as a side effect of scanning or viewing.

## Offline and recovery requirements

- After setup, watching and restarting must work with the network disconnected.
- Programme names, artwork, episode ordering and progress must be locally available.
- Missing USB storage must preserve programme choices and progress, show a calm message and permit recovery when storage returns.
- Repeated presses, held keys and interrupted playback must not unexpectedly open technical menus or launch multiple episodes.
- Failure must not silently mark an episode watched or advance to another episode.
- A helper must be able to restore a known-good configuration.

## Initial scope

Windows development, Vero V/OSMC deployment, one viewer, one USB library, a small curated programme list and local playback. Test real sample formats on the target before advertising compatibility.

Out of scope for the first version: streaming providers, live broadcasts, channel simulation, programme guides, voice assistants, recommendations, multiple viewing profiles, remote internet management and OS replacement.

## Details still to establish

- Actual Vero Kodi/OSMC version and remote behaviour.
- Television model, HDMI input, power and volume arrangements.
- Whether the existing Sky remote can be used; compatibility is not established.
- Preferred picture/text layout, programme count and viewing distance.
- Completion, replay and missing-storage behaviour on the real device.
- Whether local episode metadata is already available and how files are organised.

These uncertainties should be resolved through small prototypes and observation, not hidden behind production-ready claims.
