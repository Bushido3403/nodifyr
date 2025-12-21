# What is Nodifyr?

Nodifyr is an **open-source IoT ecosystem** focused on modular hardware for IoT, easy-to-use (and develop!) interfaces, and long-term maintainability.

At its core, Nodifyr is an attempt to build infrastructure. Not just devices, but a system where nodes, accessories, firmware, and documentation come together to create a system that just works.

This project is being developed in public and documented as it grows.

---

## The motivation

A lot of IoT projects fail quietly for the same reasons:

- hardware is tightly coupled to one use case
- interfaces are undocumented or inconsistent
- firmware grows organically without structure
- revisions overwrite history instead of explaining it
- knowledge lives in people's heads instead of artifacts
  - this leads to expensive proprietary system engineers which companies struggle to maintain!

Nodifyr exists to explore a different approach:
**Bring industry-level IoT hardware and firmware knowledge & systems to the public.**

---

## What Nodifyr is (and is not)

### Nodifyr *is*:

- a modular IoT platform
- a collection of hardware, firmware, and system-level design decisions
- an evolving reference implementation
- a documented design process, not just finished outputs
- an experiment in building durable technical knowledge over time

### Nodifyr is *not*:

- a finished product (in theory, it never will be!)
- a startup (at least not yet)
- a single board or device

Some ideas will be wrong at their beginning.
Those outcomes are expected, and documented.
I can't work on a project at this scale if I expect perfection from myself, so my philosphy becomes:
**This is a living system. I will iterate openly, document honestly, and improve continuously.**

---

## Core ideas

While the implementation is still evolving, Nodifyr is guided by a few consistent principles:

- **Modularity**  
  Boards, nodes, and accessories should have clear boundaries and defined interfaces.

- **Transparency**  
  Design decisions, tradeoffs, and mistakes are recorded rather than hidden.

- **Longevity**  
  Designs should be understandable months or years later, even by someone new.

- **Real constraints**  
  Components are chosen with manufacturing, sourcing, and assembly in mind.

---

## How this project is structured

Nodifyr is split into multiple repositories and documentation sections, roughly along these lines:

- **[Hardware](https://github.com/Bushido3403/nodifyr-hardware)**
  Board designs, schematics, revisions, and electrical rules.

- **[Firmware](https://github.com/Bushido3403/nodifyr-firmware)**
  Embedded code, system behavior, and on-chip logic.

- **[Software](https://github.com/Bushido3403/nodifyr-software)**
  Cloud endpoints, API interactions, security.

- **Documentation (You are here!)**
  Architecture, interfaces, decisions (ADRs), measurements, and devlogs.

This documentation site serves as the **source of truth** tying all of that together.

---

## Why everything is documented

This site exists for a few reasons:

- to force clarity while designing
- to capture intent before it's forgotten
- to make future revisions easier
- to create a readable engineering narrative

My goal is not perfection, it's **a realistic way to develop**.

If something changes, the history of *why* should still exist.

---

## Who this is for

Nodifyr is primarily for:

- engineers and students
- people interested in embedded systems and IoT
- anyone curious about how hardware projects actually evolve
- businesses looking to implement the technology
- potential collaborators

It's also for *future me*, when today's decisions no longer feel obvious.

---

## Current status

Nodifyr is in active development.

At the time of writing:
- hardware design for the first dev board is in early revision stages
- firmware is mostly flow logic (diagrams coming soon!)
- interfaces are being defined
- documentation is growing alongside the project

Nothing here should be treated as final.

---

## Where to go next

Currently the only documentation page I have filled out is the current progress on the S3 Dev Board:
`devlog/2025-12-20-revA-schematic-checkpoint.md`

This project will change.  
The documentation will change with it :)