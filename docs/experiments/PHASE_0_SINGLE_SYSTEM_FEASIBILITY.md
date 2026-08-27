# Phase 0 — Single-System Feasibility

## Purpose

Phase 0 is the **logical lynchpin of the SDCE research program**.

The broader Software-Defined Computing Ecosystem (SDCE) vision proposes that computational capabilities can be treated as dynamically available resources rather than being permanently bound to individual machines or task-specific roles.

Before that proposition can be meaningfully evaluated across multiple computers, networks, organizations, or an ecosystem of independently owned systems, its fundamental premise must first be examined within the smallest useful environment:

> **Can a single physical computer behave as a software-defined collection of independently addressable computational resources?**

This document establishes the research foundation for answering that question.

---

## 1. The Foundational Proposition

The foundational SDCE proposition is:

> **The computational capabilities within a physical computer can be abstracted into software-defined resources that can be discovered, characterized, allocated, monitored, and reclaimed independently of the traditional machine-level abstraction.**

The proposition does not require that every hardware component be completely separable, interchangeable, or remotely usable.

The research question is whether useful computational resource abstraction is technically possible while preserving the constraints and characteristics imposed by the underlying hardware and operating system.

---

## 2. Why Single-System Feasibility Comes First

The broader SDCE vision introduces additional variables at every level of scale:

- network latency
- distributed coordination
- heterogeneous machines
- independent ownership
- trust boundaries
- node failure
- data movement
- economic incentives
- large-scale scheduling

Those problems are important, but they can obscure whether the underlying computational abstraction itself works.

A single-system environment removes most of those variables.

If the fundamental abstraction cannot be demonstrated within one physical computer, then expanding the architecture to multiple computers does not solve the underlying problem. It merely adds complexity around it.

Conversely, if the abstraction can be demonstrated on one computer, the result provides a concrete foundation from which increasingly distributed environments can be investigated.

Therefore:

**Single-system feasibility is a prerequisite for evaluating the broader SDCE architecture.**

---

## 3. Scope

Phase 0 is intentionally narrow.

### In Scope

Initial investigation may include:

- discovery of available CPU resources
- discovery of available GPU resources
- discovery of available memory
- discovery of available storage
- representation of heterogeneous resources
- resource capability description
- resource capacity measurement
- resource availability measurement
- resource allocation
- resource monitoring
- resource reclamation
- local workload protection
- workload isolation
- scheduling behavior
- resource contention
- measurable system overhead

### Out of Scope

Phase 0 does not attempt to solve:

- multi-machine orchestration
- wide-area distributed computing
- decentralized resource markets
- ecosystem-wide trust
- cross-organization governance
- large-scale economic incentives
- global scheduling
- internet-scale resource discovery

Those concerns become subsequent research questions only if the foundational premise survives Phase 0.

---

## 4. Initial Research Question

The first experiment should answer the smallest useful version of the proposition:

> **Can a single conventional PC expose its available computational capabilities through a common software-defined resource abstraction and dynamically assign those resources to workloads without unacceptable disruption to the host system?**

The experiment should not assume a particular eventual implementation.

The eventual SDCE architecture could theoretically take the form of an operating system, kernel facility, hypervisor, runtime, service layer, orchestration layer, or another architecture entirely.

Phase 0 tests the underlying capability rather than selecting the final implementation model.

---

## 5. Candidate Resource Classes

The initial investigation should consider at least the following resource classes:

### CPU

Can processing capacity be represented and allocated independently of the machine as a whole?

### GPU

Can GPU computational capability be exposed as a resource with measurable capacity, availability, and workload requirements?

### Memory

Can memory capacity be treated as a managed resource while respecting operating-system and application constraints?

### Storage

Can storage capacity and potentially storage throughput be represented as resources independently of the physical storage device?

### Network

Network capability may initially be measured as a resource characteristic rather than treated as a distributed resource. Its role should become more significant in later phases.

The inclusion of a resource class in Phase 0 does not imply that the class can or should be managed identically to every other resource.

---

## 6. Resource Independence

A central question is what **independently addressable** actually means.

Independence does not necessarily mean physical isolation.

For example, CPU, memory, and GPU resources may remain technically interdependent at the hardware and operating-system levels. The research objective is to determine whether their useful computational capabilities can nevertheless be represented and managed as distinct resources through software.

The investigation should therefore distinguish between:

- physical independence
- logical independence
- allocatable independence
- observable independence
- workload independence

The required degree of independence must be established empirically rather than assumed.

---

## 7. Local-First Constraint

A successful Phase 0 system must remain a useful computer to its owner.

Resource allocation must therefore account for host-system requirements.

A participating resource should be capable of being made available to an SDCE workload while allowing local workloads and system functions to retain appropriate priority.

This introduces an important dynamic:

**available capacity is not necessarily fixed capacity.**

The amount of capacity available to SDCE may change as the host system's own requirements change.

This behavior is not a secondary feature. It is central to the broader concept of safely utilizing intermittently idle computing capacity.

---

## 8. What Would Count as Evidence?

Phase 0 should produce measurable evidence rather than a qualitative demonstration alone.

Useful evidence may include:

- successful identification of distinct resource classes
- measurable resource availability
- successful allocation of resources to defined workloads
- successful adjustment of allocations while workloads are active
- successful reclamation of resources
- preservation of local system functionality
- measurable performance overhead
- measurable scheduling latency
- measurable resource contention
- repeatability across multiple test conditions

The exact experimental metrics should be established after the initial architecture of the test system is defined.

---

## 9. Success, Partial Success, and Failure

### Success

Phase 0 succeeds if the research demonstrates that a single physical computer can expose useful computational capabilities through a software-defined resource abstraction and dynamically manage those resources for workloads within acceptable constraints.

Success does **not** establish that SDCE will scale to multiple computers or operate economically at ecosystem scale.

### Partial Success

A partial result may demonstrate that some resource classes or allocation mechanisms work while others do not.

Such results are valuable and should refine the architecture rather than being treated as failure of the entire concept.

### Failure

Failure may occur if the proposed abstraction cannot provide meaningful resource independence, if allocation cannot be performed safely, if overhead overwhelms the benefit, or if host-system protection cannot be maintained.

A negative result is a legitimate research outcome.

The objective is to determine the limits of the proposition, not to force a positive result.

---

## 10. Questions the Experiment Must Eventually Answer

1. What is the smallest useful definition of an SDCE resource?
2. Which resource characteristics must be exposed to software?
3. Which resources can actually be allocated independently?
4. What mechanisms does the operating system already provide?
5. What capabilities require lower-level access?
6. What resource-management overhead is introduced?
7. How quickly can resources be allocated and reclaimed?
8. How effectively can local workloads preempt or constrain SDCE workloads?
9. Which workload types benefit from the abstraction?
10. Which workload types do not?
11. Where do hardware dependencies prevent abstraction?
12. Where does the abstraction become useful despite those dependencies?
13. What is the minimum viable software architecture required to demonstrate the proposition?

---

## 11. Research Boundary

Phase 0 should remain deliberately smaller than the eventual SDCE architecture.

The goal is not to build the ecosystem in miniature.

The goal is to isolate and test the **lynchpin proposition** on which the ecosystem depends.

Only after sufficient evidence has been obtained should the project advance to the next layer of complexity.

The intended progression is:

**Phase 0: Single PC**

→ **Phase 1: Multiple resources and workloads within a controlled local environment**

→ **Phase 2: Multiple physical systems**

→ **Phase 3: Distributed ecosystem behavior**

→ **Phase 4: Larger-scale and independently owned participation**

The names and boundaries of later phases are provisional and should not be treated as established architecture.

---

## 12. Guiding Principle

> **If the core proposition does not work on a single processing system, the grand ecosystem is irrelevant.**

Therefore the first responsibility of SDCE research is not to build the ecosystem.

It is to determine whether the ecosystem's foundational idea is technically sound.

**Prove the smallest thing first.**
