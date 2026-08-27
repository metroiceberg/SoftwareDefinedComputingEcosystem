# Phase 0 — Technical Starting Point

## Purpose

This document establishes the current technical starting point for **Phase 0: Single-System Feasibility**, the logical lynchpin of the SDCE research program.

It is not a specification and does not prescribe the eventual implementation of SDCE. Its purpose is to give researchers a concrete technical proposition to examine before the project expands to multiple physical systems.

## The Proposition

The working proposition is that a single conventional computer may be capable of exposing its heterogeneous computational capabilities as software-defined resources that can be discovered, characterized, allocated, monitored, and reclaimed independently enough to support useful workloads.

The critical distinction is between the **physical computer** and the **computational capabilities it contains**.

The physical machine remains a single system. SDCE asks whether software can construct a useful resource abstraction above that physical reality.

## What We Are Trying to Establish

A minimally viable Phase 0 system should allow us to investigate whether software can:

1. Discover relevant computational resources.
2. Describe their capabilities and constraints.
3. Represent those resources through a coherent abstraction.
4. Determine what capacity is currently available.
5. Assign available capacity to defined workloads.
6. Monitor resource utilization and workload behavior.
7. Adjust or reclaim allocated capacity.
8. Protect the host system and its local workloads.
9. Measure the overhead introduced by the abstraction.

The list is intentionally provisional. The Phase 0 Research Questions document is the authoritative place for expanding the questions we need to answer.

## Initial Resource Classes

The first investigation should consider, where technically practical:

- CPU processing capacity
- GPU processing capacity
- system memory
- storage capacity and/or throughput
- specialized accelerators

These resources should not be assumed to be interchangeable. Their hardware and operating-system constraints may require different mechanisms while still fitting within a common conceptual resource model.

## What This Is Not

Phase 0 is not an attempt to build the eventual SDCE ecosystem.

It does not require:

- multiple computers
- networked resource sharing
- internet-scale discovery
- distributed trust
- resource markets
- economic incentives
- decentralized governance
- production-grade orchestration

Those concerns are downstream of the foundational question.

## Implementation Neutrality

The experiment should remain neutral regarding the eventual architectural form of SDCE.

Possible future implementations could include an operating system, kernel facility, hypervisor, runtime, service layer, orchestration layer, or another architecture.

Phase 0 should determine whether the underlying capability is feasible before selecting among those possibilities.

## The Technical Challenge

The central technical challenge is not simply whether a computer can run multiple processes at once. Modern operating systems already do that.

The question is whether the SDCE abstraction provides a meaningful layer of **resource-level representation and dynamic allocation** beyond conventional process scheduling and hardware utilization.

The experiment must therefore distinguish between:

- ordinary operating-system scheduling
- virtualization or partitioning
- conventional application-level resource management
- the proposed SDCE resource abstraction

If existing mechanisms already provide the necessary behavior, that finding must be treated seriously. SDCE must demonstrate a meaningful distinction or benefit rather than merely renaming existing capabilities.

## Initial Experimental Shape

The eventual Phase 0 experiment should probably begin with a deliberately small number of resource classes and a deliberately simple workload.

The goal is to establish the abstraction before increasing complexity.

A useful progression may be:

**Observe → Represent → Allocate → Exercise → Monitor → Reclaim → Measure**

Only after this basic loop is understood should additional resource types, workload complexity, or more sophisticated scheduling be introduced.

## Evidence Standard

A successful demonstration must produce evidence that can be measured and reproduced.

The research should compare the proposed approach against appropriate baselines and record limitations, overhead, and failure modes.

A demonstration that merely appears to work is insufficient if the same result is fully explained by conventional operating-system behavior.

Likewise, a technically impressive prototype is not evidence of feasibility unless it answers the foundational questions.

## Expected Outcomes

Phase 0 may produce one of several legitimate outcomes:

### Feasible

The core abstraction can be demonstrated with useful behavior and acceptable constraints.

### Conditionally Feasible

The abstraction works for certain resource classes, workloads, or operating environments but encounters important limitations.

### Infeasible as Proposed

The abstraction cannot provide meaningful independent resource management, or its costs and constraints overwhelm its potential benefit.

### Requires Reformulation

The original proposition is too broad, ambiguous, or incorrectly framed and must be revised before a valid feasibility test can be completed.

None of these outcomes is a failure of the research process. The purpose of Phase 0 is to discover which description reality supports.

## Next Technical Step

The next step after this document is **not** to build a complete SDCE prototype.

It is to define the minimum experimental setup capable of distinguishing the SDCE proposition from capabilities already provided by the host operating system.

That experiment should emerge from the research questions and should be small enough that a negative result is informative rather than buried beneath implementation complexity.

> **Build only enough to test the lynchpin.**
