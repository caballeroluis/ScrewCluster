# ScrewCluster 🔩

**Open-source computer vision for grouping visually similar screws by colour.**

*Simpler sorting. Faster repairs.*

![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge&logo=gnu&logoColor=white)
![Status: Early stage](https://img.shields.io/badge/status-early%20stage-orange?style=for-the-badge)

ScrewCluster is an early-stage open-source project exploring how computer vision could help find visually similar screws in mixed collections during electronic repairs.

The idea is simple: group visually similar screws and assign a different colour to each group, making it easier to identify potential matches when looking for a replacement screw.

The goal is not to identify screw types, assign names to them, or determine where they belong. It is simply about finding visual similarities.

> **Project status:** Initial concept. No working prototype exists yet.

## The problem

Many devices contain different types of screws. Sometimes the same screwdriver is used for every screw in a device, but the screws themselves can vary considerably in length, thread or head shape. When one goes missing, the real challenge is finding a similar replacement, as you may need to consult the documentation for the exact phone model, component and screw position.

<img width="1280" alt="Screws and repair components on a blue repair mat" src="https://github.com/user-attachments/assets/1eb79058-ee5b-4221-83eb-1dec386eee46" />

*Photo 1: The repair bench. Screws can look alike at first glance, even when they are not identical.*

If you lose a screw during a repair, you might ask a colleague to lend you another screw from the same position in an identical device. Using that screw as a reference, you can search for a similar one in your box. The problem is that telling them apart can be extremely difficult, even under a microscope.

Many screws look almost identical to the naked eye, and comparing them one by one can be frustrating, especially when searching through a box full of mixed screws like this one, commonly found in repair shops:

<img width="1280" alt="A box containing a large collection of mixed screws" src="https://github.com/user-attachments/assets/8fccadc0-d145-4978-85df-4558c1f26932" />

*Photo 2: The screw box. Finding a visually similar part in a mixed collection can take time.*

What if you could see similar screws grouped by colour, making potential matches easier to spot?

## The idea

Imagine examining a collection of mixed screws through a digital microscope connected to a monitor. ScrewCluster would explore how to:

- Detect individual screws in an image.
- Compare their visual appearance.
- Group visually similar screws.
- Highlight each group with a different colour.

<img width="1195" alt="Individual screws viewed through a digital microscope with coloured outlines" src="https://github.com/user-attachments/assets/9ca2f8e6-5aa4-44cb-80c6-dcbf913c41fb" />

*Photo 3: A microscope view illustrating how coloured outlines could distinguish individual screws and visual groups. This is a conceptual illustration, not a result from a working ScrewCluster implementation.*

## The solution

The key idea is to use a **known screw as a visual reference**.

Imagine you have lost a screw and a colleague lends you one that looks identical. You place that reference screw under a digital microscope alongside the mixed screw collection. ScrewCluster would explore how to highlight visually similar screws using the same colour.

The goal is to make potential matches stand out, so you can find them without testing every screw in the phone through trial and error.

- **Use a reference:** place the borrowed screw under the microscope.
- **Find visual matches:** dynamically compare it with the screws in the collection.
- **Highlight similar screws:** assign the same colour to the reference screw and its potential visual matches.
- **Distinguish other screws:** use different colours for visually distinct groups.

ScrewCluster would not need to identify a screw by name or know which device it came from. Its purpose would be to group screws according to their visual appearance. If a new screw appears in the image, the system would explore how to assign it a colour automatically based on its similarity to the others, making it easier to find a similar part.

## Possible interfaces

- **Mobile device:** a phone could photograph a collection of screws and display proposed groups using coloured overlays in an app.
- **PC connected to a digital microscope:** a microscope connected to a computer could display a magnified view of the collection in real time, highlighting visually similar screws with different colours.

*These are possible directions to explore, not implemented features.*

## Looking for collaborators

The project is at an early stage, and I would like to hear from people interested in exploring this problem:

- **Computer vision enthusiasts:** How would you approach visual similarity grouping and feature extraction?
- **AI and machine learning developers:** Which techniques and embeddings would be worth exploring?
- **Electronics repair technicians:** Would colour-coded groups help you find replacement screws in your day-to-day work?
- **Open-source contributors:** Help explore ideas, test approaches and share suggestions.

Have an idea? You can [open an issue on GitHub](https://github.com/caballeroluis/ScrewCluster/issues).

## License

ScrewCluster is distributed under the GNU General Public License, version 3.0 ([GPL-3.0](https://github.com/caballeroluis/ScrewCluster/blob/main/LICENSE)).

---

**A simple idea: group similar screws, assign a colour to each group, and make replacement parts easier to find.**
