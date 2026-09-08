# SDCE Research Question Matrix & Prior-Art Audit

**Status:** Preliminary / evidence-gathering
**Date:** 2026-09-08
**Research source:** Undermind — `SDCE Prior Art Audit`
**Search result set:** 179 relevant papers returned

## 1. Purpose

This document decomposes the Software-Defined Computing Ecosystem (SDCE) concept into granular technical capabilities and tests each capability against known prior art.

The purpose is **falsification and boundary discovery**, not a novelty declaration.

The central question is:

> **Does SDCE contain a system-level architectural contribution that is not already provided by existing distributed-computing, grid, volunteer-computing, cloud-federation, heterogeneous-scheduling, resource-disaggregation, accelerator-pooling, and computational-economy systems?**

A key hypothesis under investigation is that SDCE's potentially distinctive contribution may lie not in any single primitive, but in the **integration of multiple established mechanisms into a common computational-resource substrate spanning heterogeneous resources, machines, owners, and administrative domains**.

That hypothesis remains unproven.

---

## 2. Evidence Classification

Each finding should eventually receive one of the repository's standard evidence states:

- **Established** — supported by reliable evidence or direct observation.
- **Derived** — follows from established information plus explicit assumptions.
- **Hypothesized** — plausible but requiring evidence.
- **Proposed** — an architectural or policy choice.
- **Demonstrated** — supported by reproducible experiment, simulation, benchmark, or prototype.
- **Rejected** — evidence shows the claim or approach is inadequate or inconsistent with project goals.

For this first audit pass, most SDCE-difference fields are intentionally marked **Open / Investigate** rather than promoted to Established.

---

## 3. Initial Prior-Art Landscape

The completed deep search returned 179 relevant papers. The highest-ranked results show that SDCE's individual building blocks have substantial historical precedent.

### Strong precedent identified

| Area | Representative prior art | What it demonstrates |
|---|---|---|
| Dynamic resource sharing across organizations | Foster et al., *The Anatomy of the Grid* (2001) | Grid computing explicitly addresses coordinated resource sharing across dynamic collections of people, institutions, and resources. |
| Service-oriented distributed resource integration | Foster et al., *The Physiology of the Grid* (2002) | Uniform service semantics, discovery, location transparency, delegation, and integration across heterogeneous platforms. |
| Computational resource markets | Chun et al., *Computational Resource Exchanges for Distributed Resource Allocation* (2004) | Auction-based allocation and resource exchange for distributed computing resources. |
| Inter-grid resource selection | Iosup et al., *Inter-operating grids through delegated matchmaking* (2007) | Hierarchical/decentralized resource selection across grids and delegated remote-resource binding. |
| Distributed computational economies | Waldspurger et al., *Spawn: A Distributed Computational Economy* (1992) | Actual market-based use of idle heterogeneous workstations, including fairness, currency, pricing, and resource allocation. |
| Federated resource trading | Li et al., *Virtual Machine Trading in a Federation of Clouds* (2013) | Dynamic resource trading, pricing, scheduling, and economic optimization between clouds. |
| Federated heterogeneous resource allocation | AuYoung et al., *Resource Allocation in Federated Distributed Computing Infrastructures* (2004) | Allocation of heterogeneous distributed resources across administrative domains. |
| Volunteer computing | Anderson, *BOINC: A Platform for Volunteer Computing* (2019) | Large-scale use of heterogeneous, unreliable, intermittently available consumer resources. |
| Peer-to-peer resource exchange | Chun et al., *Bootstrapping a Distributed Computational Economy with Peer-to-Peer Bartering* (2003) | Resource discovery, secure peering, and decentralized resource exchange. |
| Opportunistic desktop computing | Wright, *Cheap cycles from the desktop to the dedicated cluster* (2007) | Combining dedicated and opportunistic scheduling to harvest desktop capacity. |
| Shared accelerator pools | Zhu et al., *FPGA Resource Pooling in Cloud Computing* (2018) | Treating FPGA accelerators as a shared pool independently of VM/server placement. |
| Accelerator virtualization | Yu et al., *AvA: Accelerated Virtualization of Accelerators* (2020) | Virtualization and policy-controlled sharing of heterogeneous accelerators. |
| Resource disaggregation | Vilanova et al., *Caladan: a distributed meta-OS for data center disaggregation* (2020) | A resource fabric, virtual devices, distributed naming, and execution across disaggregated resources. |
| Computing continuum orchestration | Ullah et al., *Orchestration in the Cloud-to-Things compute continuum* (2023) | Runtime orchestration across geographically distributed, heterogeneous cloud/edge/IoT resources. |

**Preliminary conclusion:** SDCE cannot credibly claim novelty for resource pooling, dynamic discovery, heterogeneous scheduling, idle-capacity harvesting, distributed resource markets, federation, accelerator pooling, or disaggregation individually.

---

## 4. Granular Capability Matrix

The following matrix is the working decomposition of SDCE. The important question is not merely whether a capability exists, but **how completely existing systems provide it, under what assumptions, and whether the proposed SDCE composition creates a materially different system property**.

| ID | SDCE capability / claim | Prior-art evidence | Current assessment | Remaining question |
|---|---|---|---|---|
| R-01 | Discover available computational resources dynamically | Grid, meta-scheduling, volunteer computing, federation | **Established prior art** | What discovery semantics, if any, remain materially different? |
| R-02 | Describe resources by capabilities rather than machine identity | Grid information services, heterogeneous schedulers | **Established prior art** | Can SDCE define a more general resource ontology spanning CPU/GPU/FPGA/ASIC/memory/storage/network? |
| R-03 | Represent heterogeneous resources in one resource model | Grid and heterogeneous cluster literature | **Established in bounded domains** | Has a common model spanning radically different resource types and ownership boundaries been demonstrated? |
| R-04 | Treat resource capacity as independently allocatable from the host machine | FPGA pooling, virtualization, disaggregation | **Established in specific domains** | What is the minimum general abstraction that works across CPU/GPU/accelerator/memory/storage? |
| R-05 | Dynamically attach/detach resources from workloads | Grid, cloud, accelerator pooling, orchestration | **Established in multiple forms** | Is SDCE's resource lifecycle model materially different? |
| R-06 | Pool resources across multiple physical machines | Grid, cloud, volunteer, cluster systems | **Established prior art** | What distinguishes an SDCE pool from a conventional distributed resource pool? |
| R-07 | Pool resources across administrative domains | Grid, federation, PlanetLab-era systems | **Established prior art** | Does SDCE require a different trust/policy architecture? |
| R-08 | Use intermittently idle desktop/workstation capacity | Spawn, Condor, BOINC, OurGrid | **Strong established prior art** | What prevents SDCE from being merely a modernized opportunistic scheduler? |
| R-09 | Preserve local owner control over contributed capacity | Volunteer/opportunistic/federated systems | **Established principle** | Can SDCE provide stronger or more general owner-side policy semantics? |
| R-10 | Reclaim contributed capacity when local demand rises | Opportunistic scheduling / desktop harvesting | **Established prior art** | Is the proposed local-first control plane technically novel or simply policy configuration? |
| R-11 | Express workload requirements independently of physical machines | Grid brokers, schedulers, cloud orchestration | **Established prior art** | Can SDCE define a richer cross-resource workload contract? |
| R-12 | Match workloads to heterogeneous resources dynamically | Heterogeneous schedulers, cloud/edge orchestration | **Established prior art** | What scheduling problem remains unsolved? |
| R-13 | Decompose workloads across heterogeneous resources | Distributed runtimes, accelerator systems, computing continuum | **Established in specialized systems** | Can SDCE provide a general decomposition substrate without application-specific assumptions? |
| R-14 | Migrate/retry work when resources disappear | Volunteer and opportunistic computing | **Established prior art** | Does SDCE introduce stronger resource-continuity semantics? |
| R-15 | Make network topology/latency/bandwidth first-class scheduling attributes | Distributed/edge scheduling | **Established prior art** | Is SDCE's treatment materially broader or more general? |
| R-16 | Integrate CPU, GPU, FPGA, ASIC and future accelerators | Heterogeneous computing + accelerator virtualization/pooling | **Partially established** | **Potential gap:** has one general ecosystem substrate been demonstrated across all these classes? |
| R-17 | Integrate compute, memory, storage and network as resource primitives | Disaggregation / continuum / cloud systems | **Partially established** | **Potential gap:** is the abstraction sufficiently general across local and distributed resources? |
| R-18 | Resource-level identity independent of host identity | Grid services / virtual resources / disaggregation | **Established in forms** | What additional semantics does SDCE require? |
| R-19 | Secure resource participation by independently controlled owners | Grid security, volunteer computing, federation | **Established problem and partial solutions** | Can SDCE create a unified trust/isolation model across participation types? |
| R-20 | Assume heterogeneous trust rather than a single trusted cluster | Grid, volunteer, federated systems | **Established problem** | Is there a novel trust composition mechanism? |
| R-21 | Resource provider can define fine-grained participation policy | Volunteer/cloud/federation systems | **Established in forms** | What policy primitives are uniquely required by SDCE? |
| R-22 | Resource consumer can select resources by capability, policy, cost and locality | Grid brokers / cloud schedulers / markets | **Established prior art** | Is SDCE's unified selection model novel? |
| R-23 | Economic valuation of computational resources | Spawn, Bellagio, cloud trading | **Established prior art** | What resource unit/valuation model would be materially new? |
| R-24 | Computational tender / auction mechanism | Spawn and computational resource exchanges | **Established prior art** | Can tendering be integrated with heterogeneous resource scheduling in a new way? |
| R-25 | Reciprocal resource exchange / bartering | OurGrid, peer-to-peer computational economies | **Established prior art** | What differs from prior reciprocity models? |
| R-26 | Voluntary participation without compulsory contribution | Volunteer / community grids | **Established principle** | Is SDCE's economic treatment materially different? |
| R-27 | Consumption-only participation path | Cloud/service models | **Established in principle** | Does SDCE's combination with local resource participation create a distinct model? |
| R-28 | Contribution may offset service cost but cannot create a negative obligation | **Not yet specifically located** | **Proposed** | Is this merely product policy, or does it create a meaningful ecosystem mechanism? |
| R-29 | Direct purchase of a local system without ecosystem participation | **Not yet investigated** | **Proposed** | Likely product/business policy rather than architectural novelty. |
| R-30 | Unified resource accounting across heterogeneous contributors | Economic/federated resource systems | **Partially established** | What accounting abstraction is required for heterogeneous resource units? |
| R-31 | Resource reputation/reliability affects scheduling | Volunteer/grid/cloud systems | **Established prior art** | What new trust/reputation semantics are required? |
| R-32 | Detect and quarantine faulty/malicious resources | Volunteer/distributed systems | **Established prior art** | Can SDCE unify this across trusted and untrusted resource classes? |
| R-33 | Resource provider remains authoritative over physical hardware | Virtualization / volunteer / federation | **Established principle** | What technical enforcement mechanism is distinctive? |
| R-34 | Ecosystem can dynamically aggregate fragmented idle capacity | Spawn, Condor, BOINC, grids | **Established prior art at multiple scales** | Does SDCE achieve materially different generality or efficiency? |
| R-35 | Local-first resource allocation with opportunistic ecosystem use | Condor/opportunistic scheduling | **Established prior art** | What architectural difference remains? |
| R-36 | Cross-domain workload execution under policy | Grid/cloud federation | **Established prior art** | Is the SDCE policy model more general? |
| R-37 | Common resource fabric exposed above individual operating systems | Disaggregation, meta-OS, grid services | **Partially established** | **Potential gap:** what does a general-purpose cross-machine resource fabric look like outside controlled data centers? |
| R-38 | Resource identity, discovery, allocation, execution and release form one lifecycle | Many systems implement subsets | **Integration candidate** | Has this lifecycle been generalized across heterogeneous resources and domains? |
| R-39 | Security, economics, scheduling and resource abstraction operate in one architecture | Individual systems combine some dimensions | **Integration candidate** | Has any architecture integrated all four as first-class substrate concerns? |
| R-40 | Resource provider, consumer, agent and coordinator roles form one ecosystem | Grid/cloud/market architectures have analogous roles | **Integration candidate** | Is SDCE role composition materially different? |
| R-41 | Same substrate can support local, LAN, WAN and federated resource scopes | Pieces exist at different scopes | **Integration candidate** | Has one coherent resource model operated across all scopes? |
| R-42 | Workloads need not know which physical machine supplies a capability | Grid/cloud abstraction | **Established principle** | What new capability follows from making this abstraction universal? |
| R-43 | Resource selection can consider technical and economic constraints simultaneously | Computational economies + schedulers | **Established in specialized settings** | Is there a generalized multi-dimensional clearing mechanism? |
| R-44 | Resource availability is continuously dynamic rather than statically provisioned | Volunteer/opportunistic/edge systems | **Established prior art** | What novel runtime semantics are proposed? |
| R-45 | The ecosystem is intended as a general computational substrate rather than a single workload platform | **Potentially less directly matched** | **Open** | Is this genuinely a new architectural level or simply a broader federation? |
| R-46 | A unified architecture integrates resource abstraction, discovery, orchestration, trust, economics and policy | Pieces strongly established; complete integration not yet established from first-pass results | **Primary novelty hypothesis** | **Does the integrated architecture produce a new technical capability or only a collection of known mechanisms?** |

---

## 5. The Integration Hypothesis

The first-pass evidence strongly changes the framing of SDCE.

The defensible claim is **not**:

> "SDCE invents distributed resource sharing."

Nor is it:

> "SDCE invents computational resource markets."

Nor:

> "SDCE invents heterogeneous resource pooling."

Those claims are contradicted by decades of prior work.

The researchable claim is closer to:

> **SDCE proposes a general computational-resource substrate in which heterogeneous resources can be discovered, described, allocated, scheduled, consumed, monitored, reclaimed, exchanged, and governed across machines and potentially administrative domains, while preserving resource-owner authority and treating technical, security, policy, and economic constraints as first-class parts of the same resource lifecycle.**

This is currently a **hypothesis**, not a novelty conclusion.

The critical test is whether prior systems already provide this same integrated architecture, perhaps under different terminology.

---

## 6. Integration Must Be Tested Against Composition, Not Keywords

A major methodological risk is concluding novelty merely because no paper uses the term "SDCE."

The audit must instead test whether existing components can be composed without introducing a genuinely new architectural mechanism.

For each candidate prior-art system, ask:

1. Does it expose resources independently of their host machines?
2. Does it represent heterogeneous resource capabilities?
3. Can those resources span physical machines?
4. Can they span administrative domains?
5. Are resources dynamically attachable/detachable?
6. Can local owners reclaim capacity?
7. Can workloads specify requirements independent of machine identity?
8. Can the scheduler reason about locality and network constraints?
9. Can untrusted or semi-trusted resources participate?
10. Is resource identity distinct from machine identity?
11. Can resource value be expressed economically?
12. Can resources be bought, sold, exchanged, or tendered?
13. Are these mechanisms part of one coherent control plane?
14. Does the architecture support multiple resource classes rather than one specialized class?
15. Does it operate across local, LAN, WAN, and federated scopes?
16. Does it provide a general workload execution substrate rather than a specialized workload broker?
17. Does the composition produce a capability unavailable from the constituent systems through ordinary integration?

A system that answers most of these questions becomes a serious candidate for prior-art equivalence and must be investigated deeply.

---

## 7. Current Candidate Prior-Art Clusters

### Cluster A — Grid computing

**Strength:** Very strong overlap in dynamic resource discovery, heterogeneous resources, security, virtual organizations, cross-domain sharing, brokers, and resource selection.

**Potential SDCE distinction:** A more general resource-fabric abstraction that treats individual computational capabilities as independently addressable resources rather than primarily brokering jobs to participating sites.

**Risk:** This distinction may already exist in Grid service/resource-disaggregation literature.

### Cluster B — Computational economies

**Strength:** Strong overlap in resource markets, pricing, auctions, fairness, incentives, and idle-resource utilization.

**Potential SDCE distinction:** Economics integrated directly into a generalized heterogeneous resource lifecycle rather than applied primarily to compute nodes, VMs, or specialized resource pools.

**Risk:** Spawn and later work demonstrate surprisingly broad integration already.

### Cluster C — Volunteer/opportunistic computing

**Strength:** Strong overlap in idle-capacity harvesting, owner control, churn, heterogeneous machines, reliability, and contribution incentives.

**Potential SDCE distinction:** Treating the contributed unit as a generalized resource fabric rather than primarily executing independently distributable tasks on opportunistic nodes.

**Risk:** This may be an abstraction difference rather than a technical contribution.

### Cluster D — Accelerator pooling / virtualization

**Strength:** Strong overlap in separating accelerators from host placement and exposing them as shared resources.

**Potential SDCE distinction:** Extending the same abstraction beyond a controlled data center and beyond one accelerator class.

**Risk:** Resource disaggregation and computing-continuum research may already cover this generalization.

### Cluster E — Cloud federation / computing continuum

**Strength:** Strong overlap in multi-domain orchestration, dynamic placement, heterogeneous resources, locality, pricing, and distributed execution.

**Potential SDCE distinction:** A unified resource-level abstraction rather than federation primarily at the cloud/cluster/service level.

**Risk:** Modern continuum orchestration may already be moving directly toward this model.

---

## 8. Most Important Potential Gaps to Investigate

The first pass suggests that the following are the most promising areas for deeper investigation—not because they are assumed novel, but because the evidence is less conclusive:

### G-01 — Universal heterogeneous resource abstraction

Can CPU, GPU, FPGA, ASIC, memory, storage, and network capacity be represented through one capability-oriented model without destroying the characteristics required for scheduling and execution?

### G-02 — Resource-level rather than machine-level federation

Do existing federated systems genuinely treat individual resources as first-class movable/allocatable entities, or do they primarily federate machines, VMs, containers, jobs, or services?

### G-03 — One lifecycle across all resource types

Is there an architecture in which discovery → selection → allocation → execution → monitoring → reclamation → accounting applies uniformly across fundamentally different resource classes?

### G-04 — Technical + economic + trust-aware scheduling

Existing literature often combines two or three of these concerns. Determine whether a single general scheduler/resource market treats capability, performance, locality, trust, policy, availability, and economic value simultaneously.

### G-05 — Cross-scope resource fabric

Determine whether a single architecture provides coherent semantics from a local PC through LAN resources, WAN resources, and independently administered ecosystem resources.

### G-06 — General workload substrate

Determine whether existing systems provide a sufficiently general execution substrate or whether they require workloads to conform to specialized models such as embarrassingly parallel tasks, VMs, containers, accelerator APIs, or batch jobs.

### G-07 — Composition as a technical contribution

Even if every individual mechanism exists, determine whether their integration requires a new control-plane protocol, resource ontology, scheduling formulation, trust model, accounting mechanism, or execution abstraction.

This is the most important gap question.

---

## 9. Falsification Tests

The following conditions would substantially weaken or eliminate the current SDCE integration hypothesis:

### F-01
A prior system is found that already provides a general heterogeneous resource abstraction across CPU/GPU/accelerator/memory/storage/network resources.

### F-02
That system also supports dynamic resource discovery, allocation, reclamation, workload execution, and monitoring across independent machines.

### F-03
The same system operates across administrative domains with explicit trust and owner-policy enforcement.

### F-04
The system integrates economic allocation, pricing, exchange, or tendering into the same resource-control architecture.

### F-05
The system provides a general-purpose workload execution substrate rather than a narrow scheduler or specialized application platform.

### F-06
The proposed SDCE architecture can be reproduced simply by combining existing systems through conventional APIs without requiring a new architectural mechanism.

If F-06 is true, "integration" by itself is unlikely to constitute a sufficient technical contribution.

---

## 10. Positive Evidence That Would Strengthen SDCE

Conversely, SDCE becomes more technically interesting if research demonstrates that:

1. Existing systems solve these problems only within narrower resource or administrative scopes.
2. No existing architecture provides a universal resource ontology across heterogeneous resource classes.
3. Existing economic systems trade relatively coarse resource units rather than independently addressable heterogeneous capabilities.
4. Existing volunteer systems primarily distribute tasks rather than expose a general resource fabric.
5. Existing accelerator pooling is specialized to controlled infrastructure.
6. Existing disaggregation architectures assume tightly controlled data-center environments.
7. Existing federation architectures compose services/sites rather than individual computational capabilities.
8. Combining these mechanisms requires a new resource lifecycle, control-plane protocol, scheduling model, or trust boundary.
9. The resulting architecture enables workloads or resource exchanges that the constituent prior systems cannot support without substantial architectural modification.

---

## 11. Research Priority Matrix

| Priority | Research question | Why |
|---|---|---|
| **P0** | Does a general resource ontology spanning heterogeneous resource classes already exist? | Foundational to the SDCE abstraction. |
| **P0** | Does any existing system integrate resource-level abstraction, discovery, orchestration, trust, and economics? | Directly attacks the integration hypothesis. |
| **P0** | Can existing systems be composed to produce SDCE without a new architectural mechanism? | Tests whether integration itself is substantive. |
| **P1** | What is the boundary between resource-level federation and machine/service-level federation? | May define the architectural distinction. |
| **P1** | How general are modern computing-continuum resource models? | Modern literature may already close the apparent gap. |
| **P1** | What workloads can use a genuinely heterogeneous resource fabric? | Determines whether the abstraction has practical technical value. |
| **P1** | What trust model works across independently owned resources? | Necessary for real ecosystem operation. |
| **P2** | What economic mechanism is appropriate? | Important, but likely not the primary novelty axis. |
| **P2** | What commercial participation model is appropriate? | Primarily product/business research unless it creates technical mechanisms. |

---

## 12. Required Next Research Passes

This first report is not the final prior-art audit. The next passes should deliberately triangulate different evidence types:

### Scholarly literature

- Use Undermind to trace citations from the strongest historical matches.
- Use SciSpace to search for terminology variants around resource fabrics, resource-level federation, computational substrates, disaggregated computing, and heterogeneous resource markets.
- Use Consensus to test narrowly defined questions and validate high-impact claims.

### Patents

Search specifically for:

- heterogeneous computational resource pooling
- resource-level federation
- computational resource markets
- dynamic accelerator/resource attachment
- distributed resource fabrics
- owner-controlled resource contribution
- heterogeneous resource scheduling across administrative domains

Patent evidence must be analyzed separately from scholarly novelty.

### Implementations

Search GitHub and public technical documentation for actual implementations of:

- resource discovery/federation
- opportunistic scheduling
- heterogeneous scheduling
- accelerator pooling
- resource disaggregation
- distributed computational markets
- volunteer computing
- computing-continuum orchestration

The question is not whether a paper *describes* the mechanism, but whether a working system actually implements it and at what scope.

### Formal analysis

Once the architecture's candidate distinguishing mechanism is clearer, formalize it sufficiently to determine whether the proposed integration creates a new optimization, scheduling, allocation, or systems problem.

---

## 13. Current Research Position

**Status: Hypothesized.**

The first audit does **not** support claiming that SDCE's component technologies are novel.

It does support continuing investigation into a more specific proposition:

> **SDCE may represent a system-level architecture that unifies resource abstraction, discovery, allocation, orchestration, trust, ownership policy, and economic exchange across heterogeneous computational resources and multiple scopes of resource ownership.**

Whether that constitutes a genuine technical contribution remains unresolved.

The project should therefore avoid language such as "novel," "first," or "unprecedented" until the deeper literature, patent, and implementation audits are complete.

The most valuable possible outcome of the next research phase is not confirmation. It is a precise answer to one of two questions:

**A. What existing architecture already is SDCE?**

or

**B. What exact architectural mechanism distinguishes SDCE from everything that already exists?**

Until that distinction is established, SDCE remains a research hypothesis rather than a novelty claim.

---

## 14. Primary Evidence Sources

The initial deep search identified, among others, the following high-relevance works:

- Foster et al. (2001), *The Anatomy of the Grid: Enabling Scalable Virtual Organizations*.
- Foster et al. (2002), *The Physiology of the Grid: An Open Grid Services Architecture for Distributed Systems Integration*.
- Waldspurger et al. (1992), *Spawn: A Distributed Computational Economy*.
- Chun et al. (2003), *Bootstrapping a Distributed Computational Economy with Peer-to-Peer Bartering*.
- AuYoung et al. (2004), *Resource Allocation in Federated Distributed Computing Infrastructures*.
- Chun et al. (2004), *Computational Resource Exchanges for Distributed Resource Allocation*.
- Andrade et al. (2005), *Peer-to-peer grid computing with the OurGrid Community*.
- Iosup et al. (2007), *Inter-operating grids through delegated matchmaking*.
- Wright (2007), *Cheap cycles from the desktop to the dedicated cluster: combining opportunistic and dedicated scheduling with Condor*.
- Anderson (2019), *BOINC: A Platform for Volunteer Computing*.
- Mengistu & Che (2019), *Survey and Taxonomy of Volunteer Computing*.
- Yu et al. (2020), *AvA: Accelerated Virtualization of Accelerators*.
- Vilanova et al. (2020), *Caladan: a distributed meta-OS for data center disaggregation*.
- Zhu et al. (2018), *FPGA Resource Pooling in Cloud Computing*.
- Li et al. (2013), *Virtual Machine Trading in a Federation of Clouds: Individual Profit and Social Welfare Maximization*.
- Ullah et al. (2023), *Orchestration in the Cloud-to-Things compute continuum: taxonomy, survey and future directions*.

These references are an initial evidence set, not an exhaustive bibliography. The Undermind search returned 179 relevant papers and should be treated as the discovery corpus for the next passes.

---

## 15. Audit Provenance

The underlying deep search is maintained in the SDCE Research workspace as **SDCE Prior Art Audit**. The search was explicitly designed to challenge SDCE by looking for overlapping architectures and mechanisms across grid computing, distributed computing, volunteer computing, cloud federation, edge/continuum computing, heterogeneous scheduling, accelerator virtualization/pooling, resource disaggregation, and computational resource markets.

Future revisions of this document should preserve the distinction between:

- evidence that an individual mechanism exists;
- evidence that a complete architecture exists;
- evidence that the proposed integration is technically nontrivial; and
- evidence that the integration creates a novel technical capability.

That distinction is central to the credibility of the SDCE research program.
