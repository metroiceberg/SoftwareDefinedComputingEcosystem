# Phase 0 — Research Questions

## Purpose

This document defines the questions surrounding **Phase 0: Single-System Feasibility**, the logical lynchpin of the SDCE research program.

The purpose is not to provide answers in advance. It is to identify the questions that must be answered before the broader Software-Defined Computing Ecosystem can be meaningfully evaluated.

> **We do not claim to know all of the questions, let alone all of the answers.**

This document is therefore intentionally open-ended and should be expanded whenever a new technically relevant question, objection, limitation, or alternative interpretation is identified.

Adding a question is not an admission that the SDCE proposition is correct or incorrect. It is an acknowledgment that the question deserves investigation.

---

## 1. The Core Question

> **Can a single physical computer expose its heterogeneous computational capabilities through a software-defined resource abstraction and dynamically assign those resources to workloads without unacceptable disruption to the host system?**

Everything in Phase 0 ultimately serves this question.

---

## 2. What Does “Resource” Mean?

1. What constitutes a computational resource within a single physical computer?
2. Can CPU, GPU, memory, storage, and accelerator capabilities be represented through a common abstraction?
3. Which characteristics must a resource expose to be useful to a scheduler or workload?
4. Is a resource defined by hardware, capability, capacity, availability, or some combination of these?
5. Can a resource be logically independent even when it is physically interdependent with other resources?
6. What degree of resource independence is actually necessary for SDCE?
7. Are there resources that fundamentally cannot be abstracted in the proposed manner?

---

## 3. What Does “Software-Defined” Mean?

8. What specific control does the software layer need over a resource?
9. Which resource-management capabilities already exist in modern operating systems?
10. Which capabilities require virtualization, drivers, kernel facilities, firmware support, or hardware support?
11. Does SDCE require capabilities that current operating systems fundamentally do not expose?
12. Is SDCE creating a new abstraction, or primarily coordinating abstractions that already exist?
13. Where is the boundary between resource abstraction and conventional operating-system scheduling?

---

## 4. Can Resources Actually Be Allocated Independently?

14. Can CPU capacity be allocated independently to an SDCE workload?
15. Can GPU capacity be allocated independently to an SDCE workload?
16. Can memory be dynamically allocated while maintaining host stability?
17. Can storage capacity or throughput be treated as an allocatable resource?
18. Can specialized accelerators be exposed through the same conceptual model?
19. What happens when two resources are inherently coupled?
20. Can resource allocations change while workloads are running?
21. Can allocated resources be reclaimed without terminating or corrupting workloads?

---

## 5. Host-System Preservation

22. Can SDCE workloads operate without making the host computer unusable?
23. How should local workloads be prioritized over SDCE workloads?
24. Can the system dynamically reduce ecosystem resource availability when local demand increases?
25. What constitutes unacceptable disruption to the host?
26. What resource reservations are required for the operating system itself?
27. Can resource reclamation happen quickly enough to be practically useful?
28. What happens during sudden resource contention?

---

## 6. Workloads

29. What characteristics must a workload have to make resource abstraction useful?
30. Which workloads can be divided into independently executable tasks?
31. Which workloads require tightly coupled resources?
32. Which workloads gain nothing from SDCE because coordination overhead dominates?
33. Can an application express its computational requirements independently of specific hardware?
34. How should workloads describe minimum, preferred, and optional resource requirements?
35. Can workloads adapt to changing resource availability?

---

## 7. Performance and Overhead

36. What overhead does the SDCE abstraction introduce?
37. How much scheduling overhead is acceptable?
38. How much monitoring overhead is acceptable?
39. Does abstraction reduce performance compared with direct use of the hardware?
40. If so, under what workloads and by how much?
41. What minimum workload size is necessary for SDCE to provide a net benefit?
42. Are there resource classes for which abstraction overhead is inherently prohibitive?

---

## 8. Existing Technology

43. Which existing operating-system facilities already provide portions of the proposed behavior?
44. How do containers, virtual machines, process scheduling, CPU affinity, cgroups, GPU partitioning, and related mechanisms overlap with SDCE?
45. What existing distributed-computing systems already address portions of the problem?
46. Is SDCE proposing a genuinely distinct abstraction, or a new combination of existing mechanisms?
47. What known technical limitations have previous systems encountered?
48. What lessons from existing systems should constrain the SDCE design?

---

## 9. Falsification and Adversarial Questions

49. Is the central resource abstraction merely a restatement of existing OS scheduling?
50. Does the abstraction provide enough additional capability to justify its complexity?
51. Is “independent resource” a technically meaningful concept for the resources being considered?
52. Does resource abstraction inevitably introduce unacceptable overhead?
53. Are there fundamental hardware constraints that prevent useful abstraction?
54. Does local-system protection make meaningful resource sharing impractical?
55. Does the proposed model solve a real problem better than conventional approaches?
56. What observation would cause us to reject or substantially revise the core proposition?
57. What assumptions are currently unsupported?
58. What assumptions are we making simply because they seem intuitive?

---

## 10. Measurement

59. What should be measured to establish feasibility?
60. What baseline should SDCE performance be compared against?
61. How should resource utilization be measured?
62. How should allocation and reclamation latency be measured?
63. How should host-system impact be measured?
64. How should repeatability be established?
65. What experimental conditions could produce misleading results?
66. Which measurements would distinguish genuine resource abstraction from ordinary process scheduling?

---

## 11. Minimum Viable Demonstration

67. What is the smallest experiment capable of demonstrating the core proposition?
68. What is the smallest number of resource classes required?
69. What is the smallest workload required?
70. What capabilities must exist before the experiment is meaningful?
71. What can be demonstrated entirely in software?
72. What requires actual hardware experimentation?
73. What result would justify proceeding to the next phase?

---

## 12. Questions From Outside Researchers

This section is intentionally reserved for questions contributed by people who were not involved in developing the initial SDCE concept.

Outside criticism is expected to expand the research surface rather than merely confirm the existing questions.

New questions should be preserved even when they challenge fundamental assumptions.

*No external questions have yet been added.*

---

## 13. Living Document Policy

This document is **open to addition and revision**.

It should not be treated as a closed specification or an exhaustive list.

Anyone participating in SDCE research should be encouraged to add questions when they identify:

- an unexplored assumption
- a potential failure mode
- a technical limitation
- an alternative interpretation
- an existing technology that may invalidate an assumption
- an experimental concern
- a measurement problem
- a scalability concern
- a security concern
- a question that exposes an ambiguity in the model

The existence of an unanswered question is not a defect in the research program. **Failing to recognize an important question is.**

The purpose of this document is therefore to make uncertainty visible.

---

## 14. Relationship to Phase 0

These questions should ultimately feed the design of the Phase 0 experiment.

The experiment should not attempt to answer every question listed here. Instead, the questions should be classified according to whether they are:

- necessary to establish foundational feasibility
- relevant but deferred
- dependent on later architectural decisions
- outside the scope of Phase 0
- rendered unnecessary by experimental results

The first experiment should answer the **smallest set of questions necessary to determine whether the foundational proposition survives initial testing**.

That is the purpose of the lynchpin.
