# mechacut — Hermes plugin (Portable Agent Plugins v1)

Skills-only package: two instructions files, zero code, zero daemon.
An agent that installs this knows how to use mechacut.studio exactly —
and how to propose a tool the network's own verified way.

## What installs
- `skills/mechacut` — the operating contract (keyless curl tier,
  byte-stable outputs, sha256 per response, refusals that name the
  field and the expectation, the one-operation-at-a-time calc
  protocol for weak models).
- `skills/mechacut-network` — the network door: /api/v1/agent/propose
  (a CONTRACT is proposed, never code), the public registry at
  /proposals with named bench results, and the three laws.

## Disclosure (what the skills actually make an agent do)
- Plain HTTPS calls to https://mechacut.studio (GET /agent/manifest,
  GET /route?q=…, POST /api/v1/*). These are ordinary HTTPS requests:
  the harness does not prompt before each one — the skills state, up
  front, what text leaves the machine.
- Free tier: keyless, 30 requests/min, no account, nothing stored —
  an API key would contradict the product.
- Paid routes: x402 v1 (USDC on Base). The skill instructs the agent
  to ASK THE HUMAN before paying anything; a payment is a human
  decision, mechanically verified by the facilitator.
- 50/50 revenue split for accepted external proposals: the splitter
  factory is live on Base (0xFB209Eb982baA11Ff18CAF1ef22f29729DC3709a)
  but NO paid tool clone is registered yet — today nothing splits;
  monetization requires the proposer's own Base account (EIP-55
  format-verified, responsibility with the owner). Said here, in the
  SKILL-KIT, and on /PAYOUTS: built and proven, honestly not yet
  feeding.

## Numbers that are checkable right now
`curl https://mechacut.studio/agent/manifest` — version, counts,
tiers. 1312 tests on the product repo, adversarial-audit fixes shipped
same-day (24-11: slash-date ambiguity refusal, expected-field on every
400 class via a single seam, docs-as-skill discipline). Bench corpus:
`GET /integrity.json` — replayable pins, audit us with your own
numbers.

## Install / validate
```bash
hermes plugins validate .            # the catalog CI gate
hermes plugins install mechacut/plugin
```
