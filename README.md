## Ivaylo Bahtchevanov 

This page is where I keep the things I'm building on the side. It includes agent tools that have been useful for me in the past, engineering primitives, agent engineering methodology, diagnostic tools, and fun product ideas and musings.

**Blog:** [ivaylogb.github.io](https://ivaylogb.github.io) 

## The diagnostic stack
Diagnostic infrastructure for LLM-mediated systems. Tools for turning LLM failure-analysis into typed, falsifiable, machine-applyable Findings. Three reference tools, an orchestrator, and a spec for analyzing/comparing outputs read from Braintrust, LangSmith, PostHog, OpenTelemetry. 
The goal is to identify where the defect is and propose a clean fix.

### 📐 [agent-diagnosis-spec](https://github.com/ivaylogb/agent-diagnosis-spec)
The shared output format the tools below produce. A Finding has a claim, a file:line citation as evidence, a proposed edit, and a category (was the eval wrong, was the API interface wrong, was the documentation wrong at the moment of decision, or was the call sequence wrong). Includes a conformance test suite.

### 🔬 [agent-researcher](https://github.com/ivaylogb/agent-researcher)
A failure-diagnosis agent for other agents. Reads a failing agent eval, looks at the agent's source, and writes 2-3 hypotheses for why the agent failed. For each one, it proposes an exact code edit and a verification step (apply the edit, re-run the eval, check whether the pass rate moved). 

### 📉 [funnel-researcher](https://github.com/ivaylogb/funnel-researcher)
A failure-diagnosis tool for developer-API activation funnels. Reads a developer-facing API's onboarding funnel: the step definitions, the dropoff numbers, the product's docs, artifacts, and SDK. Provides structured hypotheses on why developers fall off at a target step. Cites the specific file and line where the friction lives. Proposes edits. Out-of-the-box functionality for drilling into a hypothesis and iterating.

### 📡 [integration-watcher](https://github.com/ivaylogb/integration-watcher)
A pattern-finding tool for developer integrations against a third-party API. Reads a stream of API call traces from real developer integrations and finds patterns in how they're getting stuck. Identifies which behaviors recur across multiple integrations, cites where in the product surface the trigger lives, and proposes edits.

### 🪠 [pluma](https://github.com/ivaylogb/pluma)
Runs the three tools above and finds where they agree. When the funnel tool and the trace tool independently point at the same file:line as the source of a defect, that's a stronger signal than either alone. Also houses the adapter layer that connects external platforms to the tools' inputs. Worked example against Stripe Connect onboarding lives in `examples/stripe/`.

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
