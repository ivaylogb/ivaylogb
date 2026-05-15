## Ivaylo Bahtchevanov 

This page is where I keep the things I'm building on the side for fun. It includes agent tools that have been useful for me in the past, engineering primitives, and fun product ideas I'm willing to make public. 


## Agent engineering kit

The goal here is to make it easy to build and deploy production-grade agents through ease of management of context, tools, evals, and skills.  

<p><strong><a href="https://github.com/ivaylogb/agent-engineering">agent-engineering</a></strong><br>

  Abstractions, recipes, cookbooks, and end-to-end working examples. </p>

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

## Built on the kit

### 🔬 [agent-researcher](https://github.com/ivaylogb/agent-researcher)
A failure-diagnosis agent for other agents. When a target agent fails an eval, this reads the failing scenario and the target agent's source, produces a small set of structured hypotheses categorized against the four-layer model, applies one mechanically, and re-runs the eval to measure the delta. 
Closed-loop system to get to a specific outcome from a starting point. 
Three subcommands `diagnose`, `apply`, `iterate` help the agent refine itself in a structured, systematic way.
Uses the abstractions from `agent-engineering`. The worked example in `examples/issue_107/` runs the full flow against reference_agent's routing eval, including a comparison run where one hypothesis (Layer 3 framing) was confirmed by the eval and another (Layer 1 framing) was falsified.

### 📉 [funnel-researcher](https://github.com/ivaylogb/funnel-researcher)
A failure-diagnosis tool for developer-API activation funnels. Reads the funnel definition, dropoff data, and the product's artifacts (docs, SDK, error catalog), produces 2-3 structured hypotheses about why developers drop off at a target step, with `file:line` evidence and applyable structured edit specs. Built for growth/PLG PMs running developer-facing API products and agent platforms.
Three subcommands (`diagnose`, `apply`, `iterate`) give out-of-the-box functionality for drilling into a hypothesis and iterate. 
Same methodology as agent-researcher. The worked example diagnoses a fictional agentic-API product against a realistic dropoff cohort.

### 📡 [integration-watcher](https://github.com/ivaylogb/integration-watcher)
A pattern-finding tool for developer integrations against a third-party API.  a stream of API-call traces from a cohort of developer integrations, a watch question, and the product's artifacts, produces structured findings about where integrations get stuck, what developers aren't using, and what they're using wrong. 
Three subcommands (`watch`, `apply`, `iterate`) for overseeing the APIs.
The worked example produces 3 findings across Layers 1, 2, 3 against a synthetic 200-call trace cohort, including a Layer 1 self-correction that pushes back on the cohort's watch question. 
v1 ships with one named denominator-math limitation surfaced in the README and a v1.1 prompt fix already in tree.

---


## Worked artifacts

### 🧪 [Pluma — fictional agentic-API platform](https://github.com/ivaylogb/funnel-researcher/tree/main/fixtures/pluma_api)

A fictional agentic-API product I built as a teaching artifact for funnel-researcher. Pluma is deliberately imperfect in five specific ways: agent_id setup buried in a separate doc from quickstart, error messages that name the problem without the fix path, an SDK `run()` signature that hides a precondition, a README quickstart that reads as linear when agent creation is a branch, and a scoped-keys concept introduced only in the error catalog.

Each imperfection produces a specific signal in the synthetic dropoff data that funnel-researcher's `diagnose` is built to catch. Same pattern as `reference_agent` for agent-researcher — a known-broken target whose failure modes are the methodology's worked example.

---
## Personal Products

---

### 🏠 Real Estate - [costseg-pro](https://costsegnow.vercel.app/)
A cost-segregation tool for real estate investors, built end-to-end on Vite, React, and Vercel. Started as an excuse to dabble more in real estate, now used by a handful of active investors.

### 📈 Finance [Portfolio-manager-and-researcher](https://github.com/ivaylogb/personal-portfolio-manager-and-researcher)
Personal portfolio monitoring + AI-assisted equity research framework. Daily briefs, SEC alerts, user-defined rules engine, methodology skills for thesis exploration. Not financial advice.

### 🕊️ Spiritualism - [Selah](https://sela-blond.vercel.app/)
Philosophical and spiritual meditative partner.

---
