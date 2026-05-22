# Taxonomy

Use this file to avoid profile sprawl. Foresight Radar should normalize related user phrases into canonical themes plus focus tags.

## Rule Of Thumb

Create a new profile only when at least one is true:

- the source map is materially different
- the scoring rubric is materially different
- the audience or decision is materially different
- the theme is repeatedly requested as a standalone recurring watch

Otherwise, keep one canonical profile and add focus tags.

## Canonical Theme Pattern

```text
canonical profile
  aliases
  focus tags
  possible child profiles
```

## Horizontal Themes

### risk-security-governance

Use for security, cyber, privacy, IT risk, AI risk, compliance, governance, operational resilience, and technology risk unless a narrower recurring watch is justified.

Aliases:

- security risk
- cyber risk
- cybersecurity
- privacy risk
- data protection
- IT risk
- technology risk
- AI risk
- AI security risk
- model risk
- operational resilience
- compliance risk
- third-party risk
- vendor risk
- governance risk

Focus tags:

- cybersecurity
- privacy
- data-protection
- ai-security
- model-risk
- agent-risk
- cloud-security
- identity-access
- vulnerability
- incident
- ransomware
- third-party-risk
- compliance
- regulation
- governance

Create child profiles only when needed:

- ai-security-risk: AI-specific attack surface, model risk, agent permissions, prompt injection, data leakage.
- privacy-data-protection: privacy regulation, data protection enforcement, consent, cross-border transfer.
- cyber-incident-watch: breaches, ransomware, vulnerabilities, threat intelligence.
- enterprise-risk-governance: board/CISO risk management, controls, audit, resilience, third-party risk.

### ai-automation

Use for AI adoption, automation, agents, model capability, developer tooling, and workflow transformation.

Focus tags:

- agents
- coding
- enterprise-ai
- model-release
- open-source-models
- workflow-automation
- ai-infra

### regulation-policy

Use for policy, regulation, enforcement, standards, and public-sector rulemaking across industries.

Focus tags:

- enforcement
- standards
- legislation
- regulators
- public-sector
- compliance

### capital-market-structure

Use for funding, M&A, IPOs, capital expenditure, investment cycles, and market structure.

Focus tags:

- fundraising
- m-and-a
- capex
- ipo
- private-markets
- valuation

### supply-chain-geopolitics

Use for geopolitical constraints, supply chain resilience, export controls, sanctions, tariffs, and industrial policy.

Focus tags:

- export-controls
- sanctions
- tariffs
- reshoring
- critical-minerals
- chokepoints

## Vertical Themes

### energy-utilities-infrastructure

Use for energy, utilities, grid, power markets, generation, storage, transmission, and infrastructure technology.

Aliases:

- energy
- utilities
- utility tech
- power tech
- grid tech
- grid infrastructure
- data-center power demand
- electricity market

Focus tags:

- grid
- transmission
- storage
- nuclear
- renewables
- power-market
- datacenter-demand
- utility-dx
- regulation
- capex

Create child profiles only when needed:

- datacenter-power-demand: AI/data-center power demand and grid constraints.
- grid-tech: transmission, distribution, grid software, interconnection, grid reliability.
- utility-regulation: tariff, rate cases, utility policy, market rules.

### healthcare-life-sciences

Use for healthcare, providers, medical devices, pharma, biotech, public health, and health data.

Focus tags:

- providers
- medtech
- pharma
- biotech
- health-ai
- regulation
- reimbursement
- clinical-evidence

### semiconductors-electronics

Use for chips, semiconductor equipment, EDA, packaging, fabs, export controls, and electronics supply chain.

Focus tags:

- fabs
- equipment
- packaging
- memory
- gpu
- export-controls
- supply-chain

## Intersection Themes

Do not create an intersection profile at first use. Compose existing profiles and record the combination.

Good intersection candidates after repeated use:

- energy-utilities-infrastructure + ai-automation + datacenter-demand
- risk-security-governance + ai-automation + regulation-policy
- semiconductors-electronics + supply-chain-geopolitics
- healthcare-life-sciences + ai-automation + regulation-policy

## Naming Rules

Use canonical lowercase hyphen names.

Prefer broad parent names:

- `risk-security-governance`
- `energy-utilities-infrastructure`
- `regulation-policy`

Use focus tags for narrower asks:

- `focus: ai-security`
- `focus: privacy`
- `focus: datacenter-demand`

Avoid duplicate profile names:

- `security-risk`
- `cyber-risk`
- `cybersecurity-risk`
- `privacy-risk`

unless the user explicitly wants independent recurring watches.
