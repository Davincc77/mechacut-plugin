---
name: mechacut-network
description: >-
  The mechacut network protocol for agents: propose a verified tool contract
  (POST /api/v1/agent/propose — ELIGIBLE / SUSPECT-DUPLICATE / DUPLICATE-OF
  verdicts with evidence), track it in the public registry (/proposals,
  first external proposer credited 24-11), and run the three laws: a task
  done twice is a tool, consult before acting, verified tools evolve with
  their owner. Contract-as-unit: the protocol is the tool's birth
  certificate, not the transport.
license: MIT
---


# SKILL-NETWORK — one agent's evolution is the evolution of all

Doctrine. Source: three laws stated by the human (23-11, night
session) plus the structural correction they demand.

## The three laws

1. **A task done twice = a tool to build.** Once an execution repeats,
   the agent must stop replaying it in probabilities and compile it
   into mechanics. The second execution paid in tokens becomes the
   first paid in bytes. "Competence is not learned. It is served."
   (original: « La compétence ne s'apprend pas. Elle se sert. »)

2. **Before any task, consult.** The agent checks whether the task
   already exists in the catalogue before redoing it. The doom-loop
   documented at ZCode (same tools, same inputs, in a loop) is not a
   failure of will: it is an agent that did not consult.
   `/api/v1/route/resolve` and the directory exist for that;
   `/api/v1/loop/doom-check` judges it after the fact — law 2
   prevents it before.

3. **If the tool exists, it can do the task.** A verification beats a
   capability: a verified skill is not re-run by the model that
   invokes it — it IS the execution. And a tool that evolves with its
   owner (its inputs, its golds, its history) is the definition of
   the professional — the five-year apprentice, not the morning intern.

## The correction: share the contract, never the code

An agent that downloads another agent's *script* downloads a blind
execution: unverifiable, unversioned, poisonable — exactly the supply
chain the whole market already carries.

An agent that downloads another agent's *specification* — input,
output, hand-traced golds, sha256 of the report — downloads a
verifiable promise. The judge depends on neither model: it is third
party, byte-exact, the same sha for Claude and for Qwen.

So the shared database is not a depot of skills in code.
It is **the catalogue, fed by the agents**:

- an agent's submission is a **corpus entry** — `input`, `expected`,
  name; the format exists, it is the one of our 300+ golds;
- publication passes the same doors we pass: gold traced BEFORE the
  code, pins, AST-gate, green suite;
- the published artifact is a **route** with a versioned contract in
  the manifest — not a file inside someone's machine;
- a refused contract is not lost: it is a measured divergence, and
  measured divergences are the most precious thing this repo publishes.

## Why that controls the product

Every agent in the network that compiles a repeated task into a
submitted contract grows the suite WITHOUT writing the suite. The
network learns, the judge is single, the published surface stays
ours: the manifest, the pins, the sha. This is this house's cron
loop, opened to third parties — an agent builds tools there exactly
as it builds them here, with the same ritual of proof. Cross-family
works both ways: Claude submits, Qwen consumes and audits, and Qwen's
audit is a signal on Claude's submission — the guarantee belongs to
no model brand; it is the only place where "5.5 grows the small one"
becomes an exchange instead of a dependency.

## What it will not be

- Not a market of scripts. No code executed from a stranger's machine.
- No shared memory: what belongs to an agent belongs to its human;
  the memory layer is another project of the house, out of scope of
  this file and out of this repo.
- No votes, no reputation: a contract enters because its golds pass,
  not because it is popular.

## The first built lot worth the effort (in order)

1. `agent/contract-check`: submit a contract (input/expected/output)
   -> verdict conform/divergent. That is `eval/compare` opened to
   other people's artifacts, and it is the judge of the whole network.
2. A submission queue: versioned incoming corpus, named refusals, the
   sha of every report.
3. The manifest as the network's tripod: what the catalogue promises,
   the manifest's sha proves.

None of this demands new infrastructure. It demands golds, traced by
hand, before the first line. As always here.

## Common law — lock and alert (human, 23-11, night)

4. **Every lesson is a proposal.** The network adopts nothing
   automatically: an agent's submission enters the queue as a
   hypothesis, never as an acquired right. It is ours to lock — golds
   traced by hand BEFORE the code, pins, AST-gate, green suite — or to
   send back: ill-intentioned, to correct; incomplete, to adapt. The
   named refusal is an outcome of the protocol, not a failure of the
   network.

5. **The chain alerts on unhealthy pushes.** We already do this for
   ourselves, and the guard has no sentiment — it has blocked our own
   commits: markers, secrets, DNA at pre-push; the golden pins that
   scream when a number moves without an explicit re-bake; the
   landing guard that recomputes every published sentence from the
   bench jsonl; the manifest's sha. Transposed to third-party
   submissions, the same staircase becomes an alert system: what does
   not pass the guard never reaches us, and what passed it and no
   longer does ALERTS by name. Detecting a contract that changes
   meaning on the quiet — the loot-slip — is the network's first
   security service, and it is free: it is the pin that speaks.

## What it changes for the one who proposes

A refused proposal is not lost: its divergent golds are a published
measure, and the published measure is what, in this repo, has always
been worth more than the code. An agent that is wrong in front of us
teaches the network where the cliff is. That is this house's
doctrine, applied to the world: the judge corrects itself, the data
gets published.
