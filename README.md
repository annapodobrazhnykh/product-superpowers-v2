# Product Superpowers: Triple Diamond

Agent skills for Claude and Codex that walk a product initiative from idea to launch: one step at a time, with a human sign-off after each step and a critic at the end of each stage.

The skill files are written in Russian. The agent replies in whatever language you write in.

## What it is built on and what is added

**Built on** [product-on-purpose/pm-skills](https://github.com/product-on-purpose/pm-skills) (Apache 2.0): 68 product management skills, each producing one artifact — PRD, user stories, competitive analysis, market sizing, experiment design and more. They are included here unmodified and work as tools.

**Added on top:**

- **A navigator.** It works out what you came with: a one-off request, a mid-process entry, or the full path. It picks a route for the type of idea and leads step by step.
- **A four-stage route** with human sign-off after every step: Idea → Opportunity Discovery → Solution Discovery → Delivery.
- **Two routes.** Improving a live product goes through the funnel. A new initiative goes through market and niche. Small changes take a short path straight to an A/B test.
- **Stage critics and a final critic** working from checklists: what is done, what is missing, what rests on an assumption.
- **Research help:** the agent helps you plan and run user interviews, or runs synthetic interviews for a quick first pass.
- **Plain language:** the agent explains in simple words and ends every step with a "What to decide now" block.

## Install

**Any agent** (Codex, Claude Code, Cursor and others) via the [skills CLI](https://github.com/vercel-labs/skills):

```
npx skills add annapodobrazhnykh/product-superpowers-v2
```

**Claude Code**, as a plugin:

```
/plugin marketplace add annapodobrazhnykh/product-superpowers-v2
/plugin install triple-diamond@product-superpowers-v2
```

**Ask your agent.** Give Claude or Codex the link to this repository and say: "Install this skill set into my project and put AGENTS.md in the project root."

**Manually.** Copy the `skills` folder into `.agents/skills` in your project (`.claude/skills` for Claude Code) and `AGENTS.md` into the project root.

After installing, open a new chat and check: "List the Triple Diamond stages and the skills for each."

## Map

| Stage | Question | Skills |
|---|---|---|
| 1. Idea | What are we improving or where are we going, and which metric measures it | `stage-1-idea` |
| 2. Opportunity Discovery | Which main user obstacle are we removing | `stage-2-market`, `stage-2-users`, `stage-2-funnel`, `stage-2-competitors`, `stage-2-synthesis`, `stage-2-critic` |
| 3. Solution Discovery | What we build, what it gives, how we test it cheaply and how we launch | `stage-3-vision`, `stage-3-plan`, `stage-3-critic`, `final-critic` |
| 4. Delivery | How we launch, what production data shows, what we do next | `stage-4-delivery`, `stage-4-learn` |

Besides the route, there are tools you can call at any point. They cover user research and surveys, market sizing and competitive analysis, problem framing and prioritization, experiments, PRDs and user stories, launch checklists, and retrospectives.

## How it works

- One step at a time. After each step the agent shows the result and ends with "What to decide now".
- If a step rests on assumptions, the agent offers a choice: test them or accept them and move on.
- After an interview guide, the agent offers synthetic interviews when the audience can plausibly be simulated. They never count as confirmation.
- A stage critic runs at the end of a stage, and only after you say yes.
- You can come with a one-off request: "check my interview guide", "build a survey". The agent does just that.
- If you enter mid-process ("build a prototype"), the agent asks up to five short questions about what was skipped. Say "skip" and it does what you asked.
- By default the agent publishes nothing externally: a prototype is a single local HTML file.

## Getting started

Describe your idea in one sentence and add "lead me step by step":

> I'm a PM at a bank. I want to build shared expense tracking for a group of friends on a trip. Lead me step by step.

Useful phrases:

- "Skip" — don't go back through skipped stages.
- "Do it yourself, no questions" — run the step on assumptions.
- "Run the stage critic."
- "Show the initiative passport."

## License

Apache 2.0. The pm-skills skills belong to their authors; see `NOTICE`.
