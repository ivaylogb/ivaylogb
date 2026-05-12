# Ivaylo Bahtchevanov

---
This page is where I keep the things I'm building on the side for fun. It includes agent tools that have been useful for me in the past, engineering primitives, and fun product ideas I'm willing to make public. 
---
## Agent engineering kit

A working hypothesis: production-grade agents stand on four legs — **context, tools, evals, and skills** — and most of the interesting product work in the next few years is in the abstractions across them. These four repos are my own scratch pad for that.

<p><strong><a href="https://github.com/ivaylogb/agent-engineering">agent-engineering</a></strong><br>
The four-layer system. Thesis, failure-mode navigation, recipes, and a working tutorial that composes three kits end-to-end.</p>

<table>
<tr>
<td width="50%" valign="top">

<strong>🧠 <a href="https://github.com/ivaylogb/agent-context-kit">agent-context-kit</a></strong>

Patterns for assembling, compressing, and routing context into agent calls. What goes in the window, what stays out, and how to make those decisions cheaply at runtime.

</td>
<td width="50%" valign="top">

<strong>⚡ <a href="https://github.com/ivaylogb/agent-tool-kit">agent-tool-kit</a></strong>

Tool definitions, MCP server scaffolding, and composition patterns for letting agents act inside real systems. Opinionated about the shape of a good tool contract.

</td>
</tr>
<tr>
<td width="50%" valign="top">

<strong>🔁 <a href="https://github.com/ivaylogb/agent-eval-loop">agent-eval-loop</a></strong>

A layered eval framework — unit-style checks, simulated trajectories, and live shadow evaluation — for catching agent regressions before they ship.

</td>
<td width="50%" valign="top">

<strong>🛠️ <a href="https://github.com/ivaylogb/agent-skill-kit">agent-skill-kit</a></strong>

Methodology and Claude Code skills for shipping production-grade agents. Reference agent, audit skills, and a meta-agent that scaffolds new agents from a description.

</td>
</tr>
</table>

---

## Personal Products

### 🏠 [costseg-pro](https://github.com/ivaylogb/costseg-pro)
A cost-segregation tool for real estate investors, built end-to-end on Vite, React, and Vercel. Started as an excuse to dabble more in real estate, now used by a handful of active investors.

### [Portfolio-investing-assistant](https://github.com/ivaylogb/personal-portfolio-manager-and-researcher)
Personal portfolio monitoring + AI-assisted equity research framework. Daily briefs, SEC alerts, user-defined rules engine, methodology skills for thesis exploration. Not financial advice.

### [Selah](https://sela-blond.vercel.app/)
Philosophical and spiritual meditative partner.

---
