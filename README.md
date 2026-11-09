# Simple TV for Kodi

A simple, offline way to watch familiar television programmes: choose a large programme picture and start watching.

This project began with a family need: making a collection of favourite TV programmes accessible to someone living with dementia. The aim is a calm, predictable experience that can also be useful to other people who find conventional TV menus difficult.

**Status:** requirements and design documentation. There is no working add-on or tested hardware configuration yet. The name is a working title.

## The experience we want

- A small set of large programme pictures, with clear names and fixed positions.
- Arrow buttons move the selection; OK starts the selected programme.
- An unfinished episode resumes where it was left. After a completed episode, the next selection starts the next episode.
- Play/Pause pauses and resumes. Home returns to the same programme screen.
- Settings and episode management are available separately to a carer or helper.
- Videos, artwork and viewing progress work locally, without an everyday internet connection.

The first version is a programme chooser. Channel surfing and an electronic programme guide are outside its initial scope.

## Intended platform

Develop and test the interface in a separate Windows Kodi installation, then validate it on an **OSMC Vero V** connected to a television, using videos on a USB drive.

The proposed implementation combines a Kodi skin, remote-button mappings and, where necessary, a small Python add-on for programme selection and playback coordination. We will use Kodi's player rather than build another playback engine. Other Kodi-compatible hardware may work, but compatibility must be demonstrated.

The skin can be developed on Windows. Deployment to OSMC will transfer selected components and configure the USB source on the target; it will not restore an entire Windows Kodi profile onto Linux.

## Project documents

- [Project brief](docs/PROJECT_BRIEF.md): intended users, requirements and exact first-version behaviour.
- [Technical approach](docs/TECHNICAL_APPROACH.md): proposed boundaries, state handling, portability and open decisions.
- [Accessibility and validation](docs/ACCESSIBILITY_AND_VALIDATION.md): design principles and release acceptance checks.
- [Contributing](CONTRIBUTING.md): engineering standards and expectations for changes.

## Design with people

There is no single interface that suits everyone with dementia. Programme pictures, text size, contrast and button behaviour need testing with the person using the system. Preserve familiar skills and choice, use respectful language, and make mistakes easy to recover from.

The project draws on [Alzheimer's Society's design guidance](https://www.alzheimers.org.uk/sites/default/files/2022-05/alzheimers-society-co-creation-guide.pdf) and [DEEP's dementia-led accessibility guidance](https://dementiavoices.org.uk/wp-content/uploads/2013/11/DEEP-Guide-Creating-websites.pdf). This is an accessibility project, with no claim of clinical validation or therapeutic benefit.

## Media and privacy

Users supply their own videos and artwork that they are entitled to use. The repository will not distribute TV episodes, commercial programme images or real viewing histories. Development fixtures must be original or suitably licensed.

No accounts, telemetry, cloud services or paid subscriptions are planned for normal viewing.

## Licence

Original project material is available under the [MIT licence](LICENSE). Kodi, OSMC, dependencies and any separately licensed material retain their own licences. An existing skin must not be copied into this project under MIT unless its licence permits that use.
