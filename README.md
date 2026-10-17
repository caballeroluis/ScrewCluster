# ScrewCluster 🔩

**Open-source computer vision for grouping visually similar screws by colour.**

*Smarter sorting. Faster repairs.*

![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge&logo=gnu&logoColor=white)
![Status](https://img.shields.io/badge/status-early%20stage-orange?style=for-the-badge)

ScrewCluster is an early-stage open-source project exploring how computer vision could help organise mixed screws during electronics repair.

The idea is simple: **group visually similar screws and assign a different colour to each group**, making them easier to distinguish during repairs.

The goal is not to identify screw types, assign names or determine where screws belong. It's simply about finding visual similarities.

> **Project status:** Early concept. No working prototype yet.

## The problem

During electronics repair, small screws can easily get mixed together. Many have similar shapes and sizes, and even under a microscope, distinguishing them can be surprisingly difficult.

Comparing them one by one takes time, especially when working with a large collection of tiny screws.

Could computer vision help organise them automatically?

![TODO: Replace this link with a photo of mixed electronics-repair screws.]( )

*Mixed screws from electronics repair, showing the challenge of distinguishing similar-looking screw heads.*

### Screw head and drive variations

The shape of a screw head and its drive profile can provide useful visual clues. However, different designs can look remarkably similar, and distinguishing them is not always easy, even under magnification.

<p align="center">
  <img
    src="https://commons.wikimedia.org/wiki/Special:FilePath/Screw_drive_types_3.svg"
    alt="Reference chart of screw drive types"
    width="200"
  />
</p>

## The idea

Imagine placing a collection of screws under a microscope connected to a monitor.

ScrewCluster would explore how to:

1. Detect individual screws in an image.
2. Compare their visual appearance.
3. Group visually similar screws.
4. Highlight each group with a different colour.

![TODO: Replace this link with a concept mockup showing screws grouped by different colours.]( )

*Concept illustration of colour-coded screw groups. This is not a working software result.*

### Grouping, not identification

ScrewCluster does not need to know what type of screw it sees.

- Visually similar screws would share the same colour.
- Visually different screws would belong to different groups.
- A screw with no sufficiently similar counterparts could form a group of its own.

**Colours represent visual groups, not screw types or compatibility.**

Two screws that look alike are not necessarily interchangeable. Their suitability must still be checked by the technician.

## Contributions welcome

The project is at an early stage, and I'd love to hear from people interested in exploring the problem.

- **Computer vision enthusiasts:** How would you approach visual similarity grouping?
- **AI and machine learning developers:** What techniques might be worth exploring?
- **Electronics repair technicians:** Would colour-coded screw groups be useful at the workbench?
- **Open-source contributors:** Help explore ideas, test approaches and share feedback.

Have an idea? Feel free to [open an issue](https://github.com/caballeroluis/ScrewCluster/issues).

## Current status

- [ ] Collect photos of mixed repair screws.
- [ ] Experiment with detecting individual screws.
- [ ] Explore ways to group visually similar screws.
- [ ] Display the groups using colour overlays.

These are initial goals, not implemented features.

## License

ScrewCluster is released under the [GNU General Public License v3.0](https://github.com/caballeroluis/ScrewCluster/blob/main/LICENSE).

---

**A simple idea: group similar screws, give each group a colour, and make sorting easier.**
