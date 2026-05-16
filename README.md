## Ivaylo Bahtchevanov 

This page is where I keep the things I'm building on the side. It includes agent tools that have been useful for me in the past, engineering primitives, agent engineering methodology, diagnostic tools, and fun product ideas and musings.

**Blog:** [ivaylogb.github.io](https://ivaylogb.github.io) 

## The diagnostic stack
Diagnostic infrastructure for LLM-mediated systems. Discipline + toolkit for turning LLM failure-analysis into typed, falsifiable, machine-applyable Findings. Three reference tools, an orchestrator, and a spec for analyzing/comparing. The tools read from Braintrust, LangSmith, PostHog, OpenTelemetry) and identify defects with proposed fixes.

### 📐 [agent-diagnosis-spec](https://github.com/ivaylogb/agent-diagnosis-spec)
The structural opinions that make the outputs trustworthy. JSON Schema for the Finding object, prose specification of the four-layer model, structured-edit format, five-variant evidence union, and the grounding principles. v0.1, with a conformance test suite that runs against the three reference implementations.

### 🔬 [agent-researcher](https://github.com/ivaylogb/agent-researcher)
A failure-diagnosis agent for other agents. When a target agent fails an eval, this reads the failing scenario and the target agent's source, produces a small set of structured hypotheses categorized against the four-layer model, applies one mechanically, and re-runs the eval to measure the delta. Closed-loop system. Three subcommands `diagnose`, `apply`, `iterate` help the agent refine itself in a structured, systematic way. The worked example in `examples/issue_107/` runs the full flow against reference_agent's routing eval, including a comparison run where one hypothesis (Layer 3 framing) was confirmed by the eval and another (Layer 1 framing) was falsified.

### 📉 [funnel-researcher](https://github.com/ivaylogb/funnel-researcher)
A failure-diagnosis tool for developer-API activation funnels. Reads the funnel definition, dropoff data, and the product's artifacts (docs, SDK, error catalog), produces 2-3 structured hypotheses about why developers drop off at a target step, with `file:line` evidence and applyable structured edit specs. Three subcommands (`diagnose`, `apply`, `iterate`) give out-of-the-box functionality for drilling into a hypothesis and iterating.

### 📡 [integration-watcher](https://github.com/ivaylogb/integration-watcher)
A pattern-finding tool for developer integrations against a third-party API. Reads a stream of API-call traces from a cohort of developer integrations, a watch question, and the product's artifacts, and produces structured findings about where integrations get stuck and what developers are/aren't using properly. Three subcommands (`watch`, `apply`, `iterate`) for analyzing trace patterns and proposing grounded fixes.

### 🪠 [pluma](https://github.com/ivaylogb/pluma)
The orchestrator. One CLI over agent-researcher, funnel-researcher, and integration-watcher, with a cross-tool report that surfaces findings appearing in ≥2 tools against the same product. Houses the adapter and converters that bridge external platforms (PostHog, with more on the way) into the tools' input shapes. Worked examples include a Stripe Connect onboarding run in `examples/stripe/`.

---

## Reference implementations

<p><strong><a href="https://github.com/ivaylogb/agent-engineering">agent-engineering</a></strong><br>
  Abstractions, recipes, cookbooks, and end-to-end working examples.</p>

<table>
<tr>
<td width="50%" valign="top">

<strong>🧠 <a href="https://github.com/ivaylogb/agent-context-kit">agent-context-kit</a></strong>

Dynamic context management. Patterns for assembling, compressing, and routing context into agent calls. What goes in the window, what stays out, and how to make those decisions cheaply at runtime.

</td>
<td width="50%" valign="top">

<strong>⚡ <a href="https://github.com/ivaylogb/agent-tool-kit">agent-tool-kit</a></strong>

Tool definitions, MCP server scaffolding, and composition patterns. Opinionated about the shape of a good tool contract.

</td>
</tr>
<tr>
<td width="50%" valign="top">

<strong>🔁 <a href="https://github.com/ivaylogb/agent-eval-loop">agent-eval-loop</a></strong>

A layered eval framework, with unit-style checks, simulated trajectories, and live shadow evaluation for catching agent regressions before they ship.

</td>
<td width="50%" valign="top">

<strong>🛠️ <a href="https://github.com/ivaylogb/agent-skill-kit">agent-skill-kit</a></strong>

Methodology and Claude Code skills for shipping production-grade agents. Reference agent, audit skills, and a meta-agent that scaffolds new agents from a description.

</td>
</tr>
</table>

---
## Building Fun Ideas

---

### 🏠 Real Estate - [costseg-pro](https://costsegnow.vercel.app/)
A cost-segregation tool for real estate investors, built end-to-end on Vite, React, and Vercel. Started as an excuse to dabble more in real estate, now used by a handful of active investors.

### 📈 Finance [Portfolio-manager-and-researcher](https://github.com/ivaylogb/personal-portfolio-manager-and-researcher)
Personal portfolio monitoring + AI-assisted equity research framework. Daily briefs, SEC alerts, user-defined rules engine, methodology skills for thesis exploration. Not financial advice.

### 🕊️ Spiritualism - [Selah](https://sela-blond.vercel.app/)
Philosophical and spiritual meditative partner.

### 📝 Writing - [ivaylogb.github.io](https://ivaylogb.github.io)
Notes on engineering tools and methodology for LLM-mediated systems.

---
