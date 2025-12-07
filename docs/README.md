# Lume

A composable, visual, testable authoring platform for interactive fiction.

## The idea

IF is wonderful, but I wish there was more powerful tooling. Twine gives you a visual editor that falls apart at scale. Ink gives you power but no visibility into structure. Neither has collaboration, testing, or real debugging tools.

I've spent a decade building complex, stateful UIs as a frontend engineer. The patterns we use—reactive state, component composition, event sourcing, devtools—solve exactly the problems IF authors face. _Lume_ applies them to narrative.

---

## The problem

If you've built a branching narrative, you know:

- Stories become unnavigable past 50 nodes. The graph turns to spaghetti.
- State is impossible to track. "If the player picked up the key in chapter 2 but insulted the guard in chapter 1, what happens in chapter 4?" Good luck.
- Testing means clicking through every path by hand.
- Collaboration means emailing files and losing sync.
- You get visual editing or powerful state management, never both.

---

## The approach

Lume treats stories as composable, event-sourced systems.

You author in storylets, self-contained narrative units that receive world state and emit events. Components, but for fiction.

State is typed and scoped to entities (characters, locations, items) rather than floating globally. Events are immutable. Reducers define how state changes. This gives you deterministic replay and real debugging.

The editor keeps visual structure and prose in sync. Zoom out to see shape, zoom in to write. A state panel shows what's true at any point and what could become true. Preview mode lets you play through while watching state update, step backward, branch to explore.

Testing is first-class. Define assertions like "this scene should always be reachable" or "gold should never go negative" and run them automatically.

---

## Primitives

- **Story** — root container, global context
- **Storylet** — composable narrative unit with local state
- **Quality** — typed state (flags, counters, enums, references)
- **Event** — immutable record of something that happened
- **Reducer** — pure function defining state transitions
- **Predicate** — conditions for storylet availability
- **Passage** — prose with interpolation and conditionals

---

## Status

Early. Building the foundation: visual graph, text editor, state panel, preview, HTML export.

Coming later: automated path testing, time-travel debugging, collaboration, AI-assisted authoring.

---

## Open source

MIT licensed. The core model belongs to the community.

[github.com/wellwright-labs/lume](https://github.com/wellwright-labs/lume)

---

## Why I'm building this

I want to make narrative games. The tooling has been the blocker. Like any good engineer, I'm procrasting writing by fixing the tooling.

If you're making IF and want to talk about what you'd like to see, I'd love to hear from you.

