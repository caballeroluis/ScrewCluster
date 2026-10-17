# ScrewCluster 🔩

**Open-source computer vision for finding, matching and grouping screws used in electronics repair.**

*Smarter sorting. Faster repairs.*

![Python](https://img.shields.io/badge/Python-planned-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-planned-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Computer Vision](https://img.shields.io/badge/Computer%20Vision-exploring-0A192F?style=for-the-badge)
![GitHub](https://img.shields.io/badge/GitHub-open%20source-181717?style=for-the-badge&logo=github&logoColor=white)
![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen?style=for-the-badge)
![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge&logo=gnu&logoColor=white)
![Status](https://img.shields.io/badge/status-early%20stage-orange?style=for-the-badge)

ScrewCluster is an early-stage open-source project exploring how computer vision could help technicians identify, group and find matching screws during electronics repair.

The idea comes from a real problem observed during a mobile phone repair course: when many tiny screws are mixed together, identifying the right one and finding it again can take more time than expected.

The goal is to explore a practical visual tool that makes this process faster and easier — from organising a collection of mixed screws to finding a replacement for a specific screw.

ScrewCluster could also make its analysis capabilities available to other developers through an API, enabling web applications, mobile apps and custom repair tools.

> **Project status:** Concept and early development. The workflow and features described here are goals, not claims about a working prototype.

## The problem

Electronics repair often involves handling many small screws that look almost identical at first glance. They may differ in length, head geometry, drive profile or other subtle details.

When screws are mixed together, technicians must inspect them individually, compare their appearance and search for the right one. This becomes tedious when working with small components under magnification.

**Small repair screws can be frustratingly difficult to distinguish, even under a microscope.** Two screws may look virtually identical, yet differ in a way that matters when choosing between them.

Sometimes, magnification isn't enough. The differences may be too subtle to identify reliably by eye, leaving technicians to compare screws repeatedly and resort to trial and error to find the right match.

This is not simply a visibility problem. It is an identification problem: manually determining which screw is which can remain difficult even with magnification.

**The challenge isn't just seeing the screws more clearly. It's distinguishing screws that remain difficult to tell apart even under magnification.**

ScrewCluster aims to explore whether computer vision can help by detecting individual screws, analysing their visual characteristics, grouping similar ones and highlighting potential matches with colour overlays.

Instead of relying entirely on visual inspection and trial and error, technicians could have an additional tool to narrow down the possibilities.

![TODO: Replace this link with a photo of the chaotic screw box commonly found in professional electronics repair workshops.]( )

*The image shows the kind of chaotic screw box commonly found in professional electronics repair workshops.*

### Screw head and drive variations

The shape of a screw head and its drive profile can provide useful visual clues. Different drive designs can look similar while requiring different tools.

<p align="center">
  <img
    src="https://commons.wikimedia.org/wiki/Special:FilePath/Screw_drive_types_3.svg"
    alt="Reference chart of screw drive types"
    width="200"
  />
</p>

*Reference image: screw drive types. This illustrates differences between screw-head profiles; it is not a ScrewCluster detection result.*

Even at microscope magnification, identifying some tiny repair screws can remain a trial-and-error process. The project explores whether computer vision can discover useful visual patterns where direct visual inspection is inconclusive.

Visual similarity alone, however, does not establish a screw's exact specification or compatibility with a particular component.

## The idea

ScrewCluster explores a workflow in which a microscope or camera captures screws and computer vision helps technicians detect, compare and organise them.

The intended experience is straightforward:

1. Place mixed screws in view of a camera or microscope.
2. Detect individual screws in the image.
3. Analyse their visual characteristics.
4. Group screws according to visual similarity.
5. Display the result with semi-transparent colour overlays.
6. Let the technician inspect the groups on a monitor while handling the screws.

The aim is to reduce the effort spent repeatedly comparing tiny screws by eye.

Importantly, the system does not need to know the exact name of every screw to be useful. Grouping pieces that look alike may already help technicians narrow down the possibilities.

## Find a matching screw

ScrewCluster is not only intended to group mixed screws. It could also help technicians find a matching screw when a replacement is needed.

Imagine losing a screw while repairing a phone. You have another phone of the same model available, with a screw in the equivalent position.

You remove that screw and place it under the microscope as a reference.

ScrewCluster could analyse the reference screw, compare its visual characteristics with the other screws in view and highlight the closest visual matches using a colour overlay.

Instead of searching through a mixed tray by eye, you could see which screws look most like the reference and select a potential replacement.

The same workflow could help when a colleague needs a screw and you have several mixed screws available: place the reference screw under the microscope, let ScrewCluster find visually similar candidates, and use the highlighted groups to narrow down the search.

**The goal is to make finding a matching screw faster, even when identifying it by eye is difficult or requires repeated trial and error.**

### Two complementary workflows

- **Automatic grouping:** place a collection of mixed screws under the camera or microscope and let ScrewCluster group visually similar screws.
- **Reference-based matching:** place one known screw under the microscope and let ScrewCluster search the surrounding collection for visually similar candidates.

Both workflows rely on visual similarity rather than requiring every screw to have a predefined name or category.

A visual match is not a guarantee of mechanical compatibility. Screws that look alike may still differ in length, thread, material or other properties that cannot be reliably established from an image alone. Technicians must verify that a candidate is suitable before using it.

## Designed for a microscope workflow

The intended setup uses a microscope with a live image output connected to a monitor. Instead of relying only on the microscope eyepiece, the technician could use the monitor to inspect the live image and any visual annotations.

Colour overlays would make detected screws or similarity groups easier to distinguish without obscuring the underlying image.

In reference-based matching, the reference screw and its closest visual candidates could share a distinctive colour, making the results easier to locate in the camera view.

![TODO: Replace this link with the photo of the microscope, monitor and electronics repair workstation.]( )

*The image shows the microscope, monitor and electronics repair workstation used for screw inspection.*

![TODO: Replace this link with the concept mockup showing semi-transparent colour overlays on the microscope monitor.]( )

*Concept mockup illustrating how semi-transparent colour overlays could highlight candidate screws on the microscope monitor. This is an illustrative mockup, not a screenshot of working ScrewCluster software.*

## An open platform for screw recognition

ScrewCluster is not intended to be limited to a single desktop application. The long-term vision is to make its screw detection and visual similarity capabilities reusable by other developers and applications.

Potential integration options include:

- **REST API** — submit images for analysis and retrieve detection results, similarity groups and metadata.
- **Asynchronous processing** — submit an image or analysis job, receive a job identifier and retrieve the results when processing is complete.
- **Web applications** — build browser-based tools for organising, inspecting, comparing and matching screws.
- **Mobile applications** — integrate screw analysis into Android or iOS apps using images captured with a phone or an external microscope camera.
- **Custom interfaces** — let developers build their own visualisation, inventory and repair workflows around the underlying recognition capabilities.

The aim is to separate the computer vision capabilities from the user interface, making them reusable across different applications.

An asynchronous API could be particularly useful for analysing uploaded images or handling computationally intensive jobs without requiring the client to keep a request open until processing finishes.

For example, a mobile application could submit an image of a reference screw, receive a job identifier and later retrieve the results, including the closest visual matches.

Real-time microscope overlays introduce a different challenge: they would require a sufficiently responsive processing pipeline. This would need to be explored separately from asynchronous image analysis.

These integrations are potential future directions, not currently available features. Their design will depend on the results of the initial computer vision experiments and the needs of potential contributors.

## What could it become?

Potential features include:

- **Visual screw detection** — locate individual screws in an image.
- **Similarity grouping** — group screws by observable visual characteristics.
- **Reference-based matching** — use one screw as a visual reference to find similar screws in a collection.
- **Colour overlays** — make groups and matching candidates easier to identify.
- **Microscope integration** — explore practical camera and video-input workflows.
- **Screw inventory** — help technicians organise and retrieve screws.
- **API-based integration** — let web and mobile developers use the analysis capabilities in their own applications.
- **Custom visualisation tools** — allow different interfaces to present the results according to their users' needs.

The core goal is to detect, group and match screws by visual similarity, not to determine which screw belongs in a particular motherboard location. Compatibility and placement recommendations are outside the current scope.

## Possible technical direction

The implementation has not yet been selected or validated. Areas to explore include:

- Python
- OpenCV
- Image segmentation and feature extraction
- Object detection
- Visual embeddings and similarity metrics
- Clustering methods
- Reference-image matching
- Camera and microscope video input
- Real-time visualisation and overlays
- An API for image submission and result retrieval

These are potential technologies and areas of investigation, not a declaration of an implemented technology stack.

The project should evolve through experiments with real repair images and practical feedback, rather than committing prematurely to a complex architecture.

## Current status

ScrewCluster is in the concept and early-development stage.

- [ ] Collect real images of mixed repair screws.
- [ ] Build an initial image dataset.
- [ ] Prototype individual screw detection.
- [ ] Experiment with visual features and similarity grouping.
- [ ] Display groups using colour overlays.
- [ ] Prototype reference-based screw matching.
- [ ] Test the workflow with a microscope or camera feed.
- [ ] Evaluate performance under real repair conditions.
- [ ] Explore an API for submitting analysis jobs and retrieving results.
- [ ] Evaluate potential web and mobile integrations.

These milestones may change as experiments reveal what works and what is practical.

## Who can contribute?

ScrewCluster is intended to be an open project, and contributions can be useful even before a working prototype exists.

### Computer vision and machine learning

Help investigate screw detection, image segmentation, visual feature extraction, embeddings, clustering and reference-based matching methods.

### Electronics repair technicians

Share practical requirements, repair workflows and feedback about what would make screw identification genuinely useful at the workbench.

### Dataset contributors and image annotators

Help collect, organise and annotate images of screws with different shapes, sizes, orientations and lighting conditions.

### Hardware, cameras and microscope enthusiasts

Explore camera inputs, microscope video outputs, lighting, focus and practical workstation setups.

### Web and mobile developers

Help explore how a future API could support browser-based tools, mobile applications and custom interfaces.

### UI and developer experience

Help design a clear visualisation workflow, colour overlays, documentation and an approachable developer experience.

### Open-source contributors

Help with experiments, reproducible tests, issue reports, documentation and implementation once the initial technical direction becomes clearer.

If the problem sounds familiar or you have experience in any of these areas, [open an issue](https://github.com/caballeroluis/ScrewCluster/issues) to share ideas or discuss a possible contribution.

## Contributing

The project is still taking shape. Early feedback, real-world examples and small, focused experiments are welcome.

Please open an issue before starting a large implementation so that ideas and the project's direction can be discussed openly.

## License

ScrewCluster is released under the [GNU General Public License v3.0](https://github.com/caballeroluis/ScrewCluster/blob/main/LICENSE).

---

**Built around a simple idea: make tiny differences easier to recognise.**
