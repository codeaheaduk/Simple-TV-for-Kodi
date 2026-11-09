# Contributing

The priority is predictable, accessible viewing and dependable recovery. Keep changes small enough to understand, review and reverse.

## Before implementing

Read the [project brief](docs/PROJECT_BRIEF.md) and [technical approach](docs/TECHNICAL_APPROACH.md). State the concrete user problem a change solves. Record significant decisions about playback state, dependencies, skin licensing and hardware support.

## Engineering standards

- Prefer small, clearly named functions with explicit inputs, outputs and ownership of state.
- Separate pure selection logic from Kodi API calls, persistence and presentation.
- Use Kodi's existing capabilities where they meet the requirement. Avoid unnecessary frameworks, services and dependencies.
- Validate external data and configuration at the boundary. Give failures a useful helper-facing explanation and a calm viewer-facing outcome.
- Do not swallow errors, silently reset progress or mark failed playback as watched.
- Keep resource management and event handling explicit; avoid arbitrary sleeps and uncontrolled background polling.
- Preserve originals, configuration and viewing progress. Make migrations recoverable.
- Maintain consistent remote behaviour across windows and remove accidental routes into technical menus.
- Keep logs free of identifying health information, credentials and unnecessary media paths.
- Document supported versions and actual test results. Never describe an untested platform as supported.

For Python, use type hints where useful and adopt a consistent formatter/linter when the implementation begins. For skin XML, keep naming, indentation, focus navigation and resource references consistent. Do not add tooling configuration that claims checks exist before they are implemented.

## Validation and review

Add meaningful tests for playback selection and state changes, including failures and boundaries. A cosmetic documentation change does not need implementation-mirroring tests.

Each change should explain its resulting behaviour, validation and remaining limitations. Update the acceptance checklist and setup instructions when behaviour changes. A passing unit test does not establish remote, playback or hardware compatibility.

## Public repository hygiene

Use original or appropriately licensed fixtures and assets. Do not commit TV episodes, commercial artwork, real viewing databases, credentials, device identifiers or local diagnostic logs. Sanitise issue reports and screenshots.

Original project material uses MIT. Preserve the licence and attribution of any upstream material, and document incompatible licensing before importing it. Do not add a licence header that claims ownership of borrowed code.

Publishing a repository, uploading releases and modifying a user's installed TV system are separate actions from preparing a local change. Make releases reproducible and provide recovery instructions before asking people to install them.
