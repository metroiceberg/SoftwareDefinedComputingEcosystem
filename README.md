# Software-Defined Computing Ecosystem (SDCE)

This repository contains the **research and specification work** for the Software-Defined Computing Ecosystem (SDCE).

SDCE explores a computing architecture in which the capabilities of CPUs, GPUs, accelerators, memory, storage, and other resources can be treated as dynamically available computational resources rather than being permanently bound to individual machines or workloads.

The goal is to investigate whether heterogeneous, independently owned computing resources can be safely and efficiently coordinated into a shared computational ecosystem while preserving local ownership, control, security, and practical performance.

This repository is **not the production implementation**. It is the research foundation from which future specifications, experiments, prototypes, and implementations may develop.

## Research Principles

The project distinguishes between what is established, derived, hypothesized, proposed, demonstrated, and rejected. Experiments are intended to test claims rather than confirm assumptions, and negative results are valuable outcomes.

## Where to Start

For the complete current conceptual overview, see:

### 🌯 [The Whole Enchilada](ENCHILADA.md)

The Enchilada is the living, comprehensive description of the SDCE concept, its motivations, architectural direction, research questions, and long-term vision.

For the project's research discipline and evidence standards, see [RESEARCH_METHOD.md](RESEARCH_METHOD.md).

## Current Research Audit

The first major prior-art audit has now been completed. It returned **179 relevant scholarly papers** and shows that many individual SDCE mechanisms—grid resource sharing, idle-capacity harvesting, computational markets, heterogeneous scheduling, accelerator pooling, federation, and resource disaggregation—have substantial prior art.

The project's current research question is therefore narrower and more rigorous:

> **Does SDCE provide a genuinely distinct system-level architecture by integrating these mechanisms into a common computational-resource substrate?**

See the [SDCE Research Question Matrix & Prior-Art Audit](docs/02-research/SDCE_RESEARCH_QUESTION_MATRIX_AND_PRIOR_ART_AUDIT.md) for the granular capability decomposition, prior-art findings, falsification tests, candidate gaps, and next research passes.
