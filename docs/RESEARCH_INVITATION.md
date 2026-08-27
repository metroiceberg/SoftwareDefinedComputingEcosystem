# Invitation to Challenge the SDCE Hypothesis

## We Are Looking for People Who Will Try to Break It

The **Software-Defined Computing Ecosystem (SDCE)** is a research concept exploring whether computational capabilities can be treated as dynamically available software-defined resources rather than being permanently bound to individual machines or workloads.

The long-term vision is ambitious: a computational ecosystem capable of coordinating heterogeneous resources across independently controlled systems.

But we are **not asking anyone to evaluate that vision yet**.

We are starting with the logical lynchpin.

## The First Question

> **Can a single physical computer expose its heterogeneous computational capabilities through a software-defined resource abstraction and dynamically assign those resources to workloads without unacceptable disruption to the host system?**

If the answer is no, the broader ecosystem is irrelevant.

If the answer is yes, we have earned the right to investigate what happens when the abstraction is extended beyond a single machine.

That is why Phase 0 — Single-System Feasibility — comes first.

## What We Are Asking From Researchers

We are looking for technically knowledgeable people willing to examine the proposition critically.

In particular, we want people who can help us:

- identify assumptions we have overlooked
- identify existing technologies that already solve the proposed problem
- identify technical limitations or contradictions
- challenge the definition of a software-defined computational resource
- identify workloads for which the model cannot work
- identify hardware or operating-system constraints
- propose experiments that could falsify the proposition
- identify measurements necessary to establish meaningful feasibility
- suggest alternative interpretations or architectures
- add questions we have not thought to ask

**You do not need to agree with the premise. In fact, disagreement is useful.**

## What We Are Not Asking

We are not asking you to:

- endorse SDCE
- accept the long-term vision
- build a distributed ecosystem
- commit to an implementation architecture
- prove the concept correct
- become a long-term collaborator before evaluating the premise

The first task is much smaller:

> **Try to break the foundational proposition.**

## Why the Research Is Structured This Way

The project deliberately separates its broad vision from the evidence required to support it.

The repository contains:

- **ENCHILADA.md** — the comprehensive current conceptual picture
- **RESEARCH_METHOD.md** — the project's research and evidence discipline
- **PHASE_0_SINGLE_SYSTEM_FEASIBILITY.md** — the foundational feasibility gate
- **PHASE_0_RESEARCH_QUESTIONS.md** — the current questions and potential attack surface
- **PHASE_0_STARTING_POINT.md** — the current technical starting point for investigation

These documents are living research artifacts. They are not intended to represent a completed theory.

## Questions Are Welcome

We explicitly acknowledge that we do not know all of the questions, let alone all of the answers.

The Phase 0 Research Questions document is therefore open to addition and revision.

If you identify a question that is absent, add it.

If you identify an assumption that appears unjustified, challenge it.

If you identify an existing technology that makes part of the proposition unnecessary, tell us.

If you find a fundamental reason the proposition cannot work, **that is valuable research.**

## What Success Looks Like

The first success condition is not a working product.

It is a defensible answer to the foundational question.

That answer may be:

- feasible
- conditionally feasible
- infeasible as currently proposed
- or in need of reformulation

Any of these outcomes advances the research.

## The Invitation

If you have relevant expertise in operating systems, computer architecture, GPU computing, virtualization, distributed systems, resource scheduling, systems engineering, or related fields, we invite you to examine the proposition and attempt to falsify it.

Read the Phase 0 materials.

Find the weakest assumption.

Tell us what we missed.

And if the proposition survives your criticism, help us design the smallest experiment capable of testing it.

**We are not building a case for SDCE. We are building a case for finding out whether SDCE is possible.**

That investigation starts with one computer.
