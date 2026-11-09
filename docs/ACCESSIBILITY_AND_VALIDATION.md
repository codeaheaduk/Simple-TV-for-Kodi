# Accessibility and validation

## Design principles

Design with the viewer and their helper. Dementia does not imply one set of abilities or preferences. Test the interface from the viewer's usual seat, in normal lighting, using the intended remote.

- Keep programme locations and controls consistent.
- Use short, respectful adult language and familiar programme names.
- Pair relevant photographs with text; check that both are understood.
- Use large readable text, plain backgrounds and clear focus indicators.
- Avoid decorative motion, scrolling descriptions, unexpected sounds and timed decisions.
- Keep ordinary actions visible and provide a reliable way home.
- Preserve choice and allow familiar programmes to be watched again.
- Separate helper maintenance from ordinary viewing.

The initial programme count is a prototype choice, not a scientific limit. High contrast is useful, but a contrast score or font size alone does not establish readability on a television.

## Evidence and its limits

- [Alzheimer's Society: Dementia and co-creation](https://www.alzheimers.org.uk/sites/default/files/2022-05/alzheimers-society-co-creation-guide.pdf): practical guidance on involving people and accessible design.
- [DEEP: Creating websites for people with dementia](https://dementiavoices.org.uk/wp-content/uploads/2013/11/DEEP-Guide-Creating-websites.pdf): dementia-led guidance on language, layout and meaningful pictures.
- [W3C cognitive accessibility guidance](https://www.w3.org/WAI/WCAG2/supplemental/objectives/o1-understandable/): familiar, understandable controls. Web guidance informs our design; it does not certify a TV interface.
- [Jentoft and colleagues, 2014](https://pubmed.ncbi.nlm.nih.gov/24932651/): a small qualitative study of simplified remotes; useful support for familiar controls, not proof of our proposed product.

Research was reviewed in November 2026. No clinical study of this project or usability validation of its prototype has been completed.

## Acceptance checklist

All items below are pending. Record software versions, hardware, remote, results and known limitations when testing.

| Area | Acceptance condition |
|---|---|
| Startup | After setup, cold boot reaches programme choices without unrelated menus or sign-in. |
| Selection | A viewer can identify focus, move it and start a programme with arrows and OK. |
| Resume | Leaving and returning to a programme resumes the appropriate unfinished episode. |
| Switching | Progress remains independent for at least two programmes. |
| Completion | Natural episode end and the chosen completion threshold produce the documented next selection. |
| Final episode | Replay is deliberate and no picture disappears unexpectedly. |
| Navigation | Home and repeated Back return to the intended screen without shutdown/exit dialogs. |
| Playback controls | Pause, resume and held/repeated buttons have predictable outcomes. |
| Missing storage | Programme configuration and progress survive; restoring the USB allows recovery. |
| Failure | An unavailable or unplayable file does not advance progress or mark completion. |
| Offline | Artwork, selection, playback and restart work with the network disconnected. |
| Restart | Normal restart preserves progress; abrupt-power behaviour and any loss are documented. |
| TV integration | Input, power, volume and standby work with the recorded television/remote setup. |
| Recovery | A helper can restore a known-good setup from documented backups. |

Automated tests should cover episode ordering, resume/completion decisions, invalid state and failure transitions. Integration checks must confirm those rules against actual Kodi behaviour. Hardware and user observation remain essential.

Use short, comfortable observation sessions. Ask one ordinary task at a time, allow time, and stop if the person becomes tired or frustrated. Treat difficulties as information about the design. Record anonymised observations with permission; do not publish identifying health details or home video.
