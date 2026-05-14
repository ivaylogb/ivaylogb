# Ivaylo Bahtchevanov

---
This page is where I keep the things I'm building on the side for fun. It includes agent tools that have been useful for me in the past, engineering primitives, and fun product ideas I'm willing to make public. 
---
## Agent engineering kit

The goal here is to make it easy to build and deploy production-grade agents through ease of management of context, tools, evals, and skills.  

<p><strong><a href="https://github.com/ivaylogb/agent-engineering">agent-engineering</a></strong><br>

  The four abstractions with reciptes and end-to-end working examples. </p>

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
Closed-loop system to get to a specific outcome from a starting point. Three subcommands `diagnose`, `apply`, `iterate` help the agent refine itself in a structured, systematic way.
Uses the abstractions from `agent-engineering`. The worked example in `examples/issue_107/` runs the full flow against reference_agent's routing eval, including a comparison run where one hypothesis (Layer 3 framing) was confirmed by the eval and another (Layer 1 framing) was falsified.

### 📉 [funnel-researcher](https://github.com/ivaylogb/funnel-researcher)
A failure-diagnosis tool for developer-API activation funnels. Reads the funnel definition, dropoff data, and the product's artifacts (docs, SDK, error catalog), produces 2-3 structured hypotheses about why developers drop off at a target step, with `file:line` evidence and applyable structured edit specs. Built for growth/PLG PMs running developer-facing API products and agent platforms.
Currently ships the `diagnose` subcommand; the same three-stage shape as agent-researcher (`diagnose`, `apply`, `iterate`) is the build target as the methodology is validated in this domain.
Same methodology as agent-researcher, applied to a different problem class. The worked example diagnoses a fictional agentic-API product against a realistic dropoff cohort; 9 of 9 file:line citations in the produced report verified against the fixture source.

---

## Personal Products

### 🏠 [costseg-pro](https://costsegnow.vercel.app/)
A cost-segregation tool for real estate investors, built end-to-end on Vite, React, and Vercel. Started as an excuse to dabble more in real estate, now used by a handful of active investors.

### 📈 [Portfolio-investing-assistant](https://github.com/ivaylogb/personal-portfolio-manager-and-researcher)
Personal portfolio monitoring + AI-assisted equity research framework. Daily briefs, SEC alerts, user-defined rules engine, methodology skills for thesis exploration. Not financial advice.

### 🕊️ [Selah](https://sela-blond.vercel.app/)
Philosophical and spiritual meditative partner.

---
