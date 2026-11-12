# FieldOps design

A design case study and working front end: a **dispatcher dashboard** (web) and an **in-cab driver app** (mobile) for yard and fleet operations, built on one shared design system.

**Live:** https://fleurybryanhavyarimana0-x.github.io/fieldops-design/ · [Dispatch board](https://fleurybryanhavyarimana0-x.github.io/fieldops-design/dispatch.html) · [Driver app](https://fleurybryanhavyarimana0-x.github.io/fieldops-design/driver.html)

> Portfolio project designed and built in 2026 by Fleury-Bryan Havyarimana. Asset names, people and locations are demo data; the alert format comes from my [fleet-telemetry-pipeline](https://github.com/fleurybryanhavyarimana0-X/fleet-telemetry-pipeline).

## The idea

Telemetry systems produce alerts; people have to handle them. The same event (an engine idling for ten minutes) needs a decision from a dispatcher at a desk and a one-glance message for a driver in a moving cab. FieldOps treats each alert as a small workflow with an owner: detect, tell the driver, queue for dispatch, close the loop.

## What's here

| File | What it is |
|---|---|
| `index.html` | The case study: problem, users, framing, key decisions, screens, design system, what to test next |
| `dispatch.html` | Dispatch board: shift summary, severity-ordered action queue with acknowledge, fleet table, asset detail |
| `driver.html` | Driver app: shift summary, idle nudge with a one-tap reason, pre-trip checklist with large targets |
| `tokens.css` | Design tokens: colour (light and dark), type scale, 4 px spacing, desk vs cab target sizes |
| `components.css` | Buttons, status pills, cards, alert rows, metrics, tables, built only from tokens |

## Design decisions

- **Status is never colour alone.** Pills pair a word with a shape (circle, diamond, triangle).
- **Two target sizes, one system.** 36 px controls at the desk, 56 px in the cab for gloves and vibration.
- **The driver can answer the alert.** "I'm waiting to load" pauses the idle alert and tells dispatch why.
- **Summary before detail.** Four numbers and an ordered queue first; the table and detail when needed.

## Accessibility

AA contrast pairs in both themes, visible focus on every control, keyboard selection in the fleet table, `aria-live` for status changes, reduced motion respected.

## Run locally

Open `index.html` in a browser. No build step.
