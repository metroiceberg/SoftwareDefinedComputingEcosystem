# Phase 0 — Prior-Art and Existing Technology Map

## Purpose

This document establishes the initial prior-art review for **Phase 0: Single-System Feasibility**, the logical lynchpin of the SDCE research program.

The purpose is not to claim novelty prematurely. It is to determine what existing technologies already accomplish, where they overlap with the SDCE proposition, and whether the proposed abstraction represents a meaningful distinction or merely a new description of established mechanisms.

This is an initial research map, not a completed literature review. It is expected to grow as researchers identify additional systems, papers, standards, operating-system facilities, hardware capabilities, and related work.

> **If someone has already solved the problem, we want to know. If they have solved only part of it, we want to know that too.**

---

## 1. Proposition Under Examination

Phase 0 examines whether a single physical computer can expose heterogeneous computational capabilities through a software-defined resource abstraction that permits useful discovery, characterization, allocation, monitoring, and reclamation while maintaining acceptable host-system functionality and overhead.

The relevant question for prior art is therefore not simply:

> “Does existing software share computing resources?”

It is:

> **“Does existing technology already provide the specific resource abstraction and behavior being proposed, and if so, what—if anything—remains technically distinct about SDCE?”**

---

## 2. Existing Technology Categories to Investigate

The following categories are initial targets for review. They are not claims that SDCE is distinct from them.

### Operating-System Scheduling

Modern operating systems already multiplex CPU time among processes and provide mechanisms for prioritization, affinity, quotas, and resource control.

**Questions:**

- What aspects of the SDCE proposition are already satisfied by ordinary process scheduling?
- What additional abstraction would SDCE provide?
- Is the distinction meaningful enough to justify a separate architectural layer?

### Linux cgroups and Resource Control

Linux control groups provide mechanisms for organizing processes and controlling resource consumption.

**Questions:**

- Which SDCE resource-management behaviors can already be implemented through cgroups?
- What resource classes are supported?
- What limitations remain?

### Containers

Container technologies provide process isolation and resource controls while sharing an operating-system kernel.

**Questions:**

- How closely does container resource management correspond to the proposed SDCE model?
- Does SDCE require capabilities beyond container-level resource control?

### Virtual Machines and Hypervisors

Virtualization can partition or present computational resources to guest operating systems.

**Questions:**

- Does virtualization already provide the necessary abstraction?
- Does SDCE differ because it treats resources as dynamically allocatable capabilities rather than fixed virtual-machine assignments?
- What overhead or limitations arise from virtualization?

### CPU Affinity, NUMA, and Hardware Partitioning

Modern systems expose increasingly detailed mechanisms for controlling where computation and memory access occur.

**Questions:**

- Which existing mechanisms demonstrate useful resource-level control?
- Which hardware relationships prevent independent allocation?
- What does existing NUMA behavior imply for the SDCE abstraction?

### GPU Compute and Partitioning

Modern GPUs can expose compute capabilities through APIs, contexts, scheduling, virtualization, partitioning, and vendor-specific mechanisms.

**Questions:**

- To what extent can GPU compute capacity already be divided among workloads?
- What forms of GPU partitioning exist?
- Which capabilities are hardware-dependent?
- Does existing GPU scheduling already provide the proposed abstraction?

### Storage and I/O Resource Management

Operating systems and storage platforms already provide quotas, bandwidth controls, I/O scheduling, caching, and related mechanisms.

**Questions:**

- Can storage capacity and throughput already be treated as independently managed resources?
- Which parts of the SDCE model would be genuinely new?

### Existing Resource Managers

Systems and cluster schedulers already allocate computational resources to workloads.

**Questions:**

- What resource abstraction do existing schedulers use?
- Which aspects of SDCE resemble conventional cluster scheduling?
- What does SDCE add or change at the single-system level?

### Distributed and Volunteer Computing

Existing systems demonstrate that computation can be coordinated across independent machines.

**Questions:**

- Which lessons from distributed and volunteer computing constrain the broader SDCE vision?
- Which problems were solved previously?
- Which problems remain unsolved?

---

## 3. Required Comparison

For every significant prior-art system identified, the review should attempt to answer four questions:

1. **What does it already do?**
2. **Which portion of the SDCE proposition does it overlap?**
3. **Where does it differ?**
4. **Does the difference represent a meaningful technical distinction, or merely terminology?**

Where possible, comparisons should identify actual technical mechanisms rather than relying on marketing terminology.

---

## 4. What Would Invalidate the Proposition?

Prior art could materially challenge SDCE in several ways.

### Complete Overlap

An existing technology may already provide the proposed behavior in substantially the same form.

### Architectural Redundancy

The proposed abstraction may be technically possible but provide no meaningful advantage over existing operating-system or virtualization mechanisms.

### Fundamental Limitation

Prior systems may reveal a hardware, operating-system, or performance constraint that makes the proposed abstraction impractical.

### Terminological Novelty Only

The SDCE vocabulary may describe capabilities that already exist without adding a new technical mechanism or useful abstraction.

Any of these findings must be treated as legitimate research results.

---

## 5. What Would Strengthen the Proposition?

Prior art can also clarify rather than invalidate the concept.

Existing mechanisms may demonstrate that important pieces of the proposition are already technically feasible while exposing a gap between individual resource-management mechanisms and the broader abstraction proposed by SDCE.

For example, existing systems may independently manage CPU, memory, GPU, or storage resources without providing a unified resource model across those heterogeneous capabilities.

If such a distinction survives careful review, it should be stated precisely and supported with evidence.

---

## 6. Evidence Standards

Prior-art claims should identify, where practical:

- technology or system name
- organization or authors
- relevant version or publication date
- technical capability being examined
- authoritative source
- limitations or conditions
- relationship to the SDCE proposition

Secondary descriptions may be useful for discovery, but significant technical claims should be checked against primary documentation, specifications, papers, source code, or other authoritative material where available.

Evidence that challenges SDCE should be represented fairly rather than minimized.

---

## 7. Current Status

This document represents an **initial research map**, not a conclusion about novelty or feasibility.

No claim should be made that SDCE is technically novel until the relevant prior art has been investigated sufficiently to support such a statement.

The Phase 0 research program is primarily concerned with feasibility, not establishing intellectual-property claims.

Novelty, patentability, licensing, and related legal questions are separate matters requiring appropriate professional analysis if they become relevant.

---

## 8. Open Prior-Art Questions

This section should remain open for additions.

Potential questions include:

- What existing systems most closely resemble the proposed single-system abstraction?
- Is there an existing operating-system architecture that already treats heterogeneous hardware as a unified resource pool?
- What resource abstractions have been attempted in academic research?
- What limitations caused previous approaches to fail or remain niche?
- Which GPU virtualization and partitioning mechanisms are relevant?
- Which existing schedulers already perform dynamic heterogeneous resource allocation?
- Are there established terms for the abstraction being proposed that we should adopt instead of inventing new terminology?
- Which prior systems provide useful experimental baselines?

Researchers are explicitly encouraged to add questions and sources.

---

## 9. Living Document Policy

This document is intentionally open to addition and revision.

The project does not claim to know all relevant prior art at the beginning of the investigation.

If a contributor discovers:

- a paper we missed
- a system that already implements part of the concept
- a competing architectural model
- a technical limitation
- a better-established term
- a historical precedent
- evidence that challenges the distinction between SDCE and existing technology

it should be added to this document.

**Discovering prior art is not a threat to the research. It is part of doing the research correctly.**

---

## 10. Relationship to Phase 0

The prior-art review should inform the design of the Phase 0 experiment.

The experiment must not attempt to demonstrate something that existing technology already provides unless the purpose is explicitly to establish a baseline or measure a meaningful difference.

The desired outcome is a minimum experiment that can distinguish:

**existing capability**

from

**the additional capability claimed by SDCE.**

That distinction is essential before the broader proposition can be evaluated.
