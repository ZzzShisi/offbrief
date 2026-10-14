# OFFBRIEF Skill · 超纲

[简体中文](README.md) · [English](README.en.md)

**Bring a task, a plan, or a bottleneck. Discover another way forward.**

An Agent Skill for creative thinking, brainstorming, and problem solving. It helps AI look at your work from another angle.

Start with an idea to find a useful starting point. Bring a bottleneck, your previous attempts, and your constraints to explore another approach. When you need a plan, report, or draft, useful insights become part of the deliverable. When you already have a result, ask it to check for blind spots.

**Deliver what you planned. Discover what you hadn’t considered.**

Version **1.3.0** · [Download the skill ZIP](https://github.com/ZzzShisi/offbrief/releases/download/v1.3.0/OFFBRIEF_v1.3.0.zip) · [Installation guide](INSTALL.en.md) · [See a workplace example](#workplace-example)

![OFFBRIEF cover: an unfolded paper map reveals another route](docs/images/cover.png)

The cover’s message: “Let AI go beyond the brief. Discover another way forward.”

[Quick start](#quick-start) · [The problem it addresses](#the-problem-it-addresses) · [Design philosophy](#design-philosophy) · [How it works](#how-it-works) · [Installation](#installation) · [Workplace example](#workplace-example) · [Usage](#usage) · [Version history](#version-history)

## Quick start

After installing and loading the skill, bring an ongoing task:

> I’m working on ____, and I’m stuck at ____. Help me look for a different approach.

An early idea is enough to start. If you already have a result, you can ask:

> Review this from another angle with OFFBRIEF. Don’t change it yet.

Natural requests such as “look at this from another angle” or “check my reasoning” can be used in context. Whether the skill is selected automatically depends on the host’s discovery mechanism, configuration, and task context. You can also explicitly request `offbrief`.

## The problem it addresses

When we ask AI for help, we often already have a goal, method, and deliverable in mind. The answer follows that direction and becomes more detailed, while another useful route may never enter the discussion.

You may recognize these moments:

- A plan keeps getting more detailed, but you still cannot see how to move it forward.
- Repeated reminders leave the same handoff or dependency unresolved.
- An event or report is complete, and you wonder what decision it actually helped someone make.
- You have a solid result and want to see whether another valuable option is missing.

OFFBRIEF revisits the assumptions behind the task: who needs to participate first, what could happen earlier, whether another goal is worth considering, and how existing outputs could be used.

**The aim is to help you see another option that is relevant to your task and worth comparing or trying.**

## One task, new possibilities

| Capability | What it helps you explore |
|---|---|
| **New approaches** | Keep the goal and change the participation, timing, relationships, or mechanism. |
| **Alternative goals** | Consider what the deliverable should ultimately enable, and propose another goal for you to evaluate. |
| **New possibilities** | Find further paths in your existing materials, experience, constraints, or intermediate outputs. |

## Design philosophy

### Include the question itself in the thinking

Understand what you want to achieve, then examine familiar assumptions: why the goal is defined this way, who must be involved first, and why events happen in this order. Reconsidering an assumption can bring a new approach or goal into view.

### Explore widely, then reconnect with reality

Allow bold reframing and small discoveries. Explain how an idea relates to the task, then consider time, resources, permissions, and constraints. An uncertain direction can begin with a small experiment.

### Bring creativity into the work already underway

An early idea, a bottleneck, a deliverable, and a completed result can all benefit from creative thinking. Useful insights become part of the requested work and help it move forward.

### Turn a discovery into a meaningful choice

Focus on what would actually change in the approach, goal, relationship, or behavior. The option should be worth comparing, trying, or exploring further.

### Keep judgment and decisions with the user

Separate facts, hypotheses, and proposals. You decide whether to change the goal, expand the scope, or adopt a new direction. Preserve work that is already sufficient and follow precise instructions for exact tasks.

## How it works

The repeatable thinking process is defined in `SKILL.md`. Supporting methods and boundaries live in `references/`, which the host reads as needed.

| Step | Purpose |
|---|---|
| **Brief: understand the task** | Identify the goal, known facts, previous attempts, fixed constraints, and actual friction. |
| **Branch: explore different paths** | Revisit assumptions and look for distinct options through participants, relationships, timing, and goals. |
| **Bridge: reconnect with reality** | Explain relevance, consider resources and permissions, identify failure conditions, and suggest a small experiment when useful. |
| **Bet: choose what is worth pursuing** | Present the most promising direction, or a few distinct options when comparison is useful, while keeping the decision with you. |

Methods include reversing assumptions, shifting goals, structural analogy, exchanging roles, reordering time, temporarily relaxing constraints, and finding value in by-products.

Execution relies on the host model. The skill itself consists of text instructions and resources, with no runtime scripts. Research, file reading, and file creation use the host’s available and authorized tools.

## Installation

### Ask your AI tool to install it

In a tool that supports installing Agent Skills, say:

```text
Install this Agent Skill: https://github.com/ZzzShisi/offbrief
Its name is offbrief, and SKILL.md is at the repository root.
Confirm version 1.3.0 is loaded, then let me try it on an ongoing task.
```

The host determines the installation mechanism. Use `offbrief` as the installed folder name and preserve the relative locations of `SKILL.md`, `references/`, and `assets/`.

### Use the dedicated skill ZIP

Download [OFFBRIEF_v1.3.0.zip](dist/OFFBRIEF_v1.3.0.zip) and use your host’s supported import or installation flow. It contains the skill, reference resources, a template, and the license.

For ZIP layouts, WorkBuddy guidance, Codex directory installation, updates, and a short check after installation, see [INSTALL.en.md](INSTALL.en.md).

## Workplace example

### Weekly reports keep waiting for another department

This simulated workplace scenario was run as a model test with OFFBRIEF 1.3.0. The English prompt and excerpt below are translations of the original Chinese test.

**Prompt:**

> Every week I collect Excel reports from six departments for consolidation on Friday morning. The column headers are fixed. People often discover on Friday that a field needs data from someone else, and reminders are already too late. We cannot change systems or add a daily report. Help me find a different way to address the waiting.

**Translated response excerpt:**

> Arrange cross-department fields as scheduled handoffs: keep submitting the complete Excel report on Friday, but confirm during the week who will provide the data, when, and with which definition.
>
> The bottleneck you described is that people only ask someone else for an answer when they reach the field. Identifying the dependency can happen before entering the final value. Fixed headers make it possible to arrange that handoff earlier.

The response then suggests trying one frequently delayed field with one pair of data providers and recipients, and observing whether Friday still requires urgent coordination. It also notes that scheduling a handoff cannot make data exist before it is generated.

The option changes the timing of the handoff while preserving the report structure and existing systems. Its usefulness still needs to be tested in the actual workplace.

[Original complete response (Chinese)](docs/evidence/F02-response.md) · [More examples (Chinese)](docs/EXAMPLES.md)

## Usage

| Where you are in the task | A request you can use |
|---|---|
| **An early idea** | I want colleagues to start using this tool. I have no plan yet. Help me find a starting point worth trying. |
| **A bottleneck** | These are the approaches I have tried, and these constraints are fixed. Help me explore another path. |
| **A deliverable** | Write a one-page pilot plan. Integrate useful new ideas into the result and give me one usable deliverable. |
| **A completed result** | Review this against the original requirements from another angle. Don’t change it yet. |

Creative thinking can become part of the deliverable. You do not need to choose an internal mode. Reviewing an existing result is one of several ways to use the skill.

## Testing and boundaries

Version 1.3.0 was tested for exploration, delivery, review, implicit discovery, exact tasks, and file creation. The original [test record is in Chinese](docs/TESTING.md).

The record contains 27 model responses: 15 version 1.3.0 text requests, one encoding retest, eight comparison responses, two implicit-discovery runs, and one file-delivery run. These are model responses rather than a count of users. The workflow test prompts were written in Chinese; this page’s English example is a documentation translation.

The intended behavior includes:

- Distinguish facts, hypotheses, and new proposals; state conditions when material is missing.
- Leave changes to the goal or scope for you to decide.
- Preserve valid work, follow a request to review without editing, and accept an adequate result.
- Follow exact requests for numbers, translation, extraction, or specified corrections.
- Complete requested deliverables and integrate useful insights without duplicating the work.

Results depend on the host model, context, and tools. Current tests support observations within those scenarios, without establishing statistical conclusions about user preference or business improvement.

## Repository structure

```text
offbrief/
├── SKILL.md          # Instructions read by the host
├── references/       # Methods, boundaries, and examples loaded as needed
├── assets/           # Discovery-card template
├── README.md         # Chinese homepage
├── README.en.md      # English homepage
├── INSTALL.md        # Chinese installation guide
├── INSTALL.en.md     # English installation guide
├── docs/             # Images, examples, and test records
├── dist/             # Dedicated skill ZIP and SHA-256 checksum
├── CHANGELOG.md      # Version changes
└── LICENSE           # MIT License
```

## Help improve OFFBRIEF

Try it on an ongoing task and share your experience in **Issues**: what you were doing, which option you newly noticed, and whether you adopted it. Feedback in English is welcome.

If the output merely changes wording or adds unnecessary work, describe that too. Such feedback helps improve the judgment of which new options are worth presenting.

Remove confidential materials, account details, and information that should not be public before submitting. Changes to the skill should explain the problem they address and provide a reproducible example when possible.

## Version history

### 1.3.0

- Creative thinking throughout the task: finding a direction, making progress, delivering work, and reviewing results.
- Natural requests are interpreted in context; a finished draft is not required, and reasoning review is distinguished from exact checks.
- Useful insights can be integrated into deliverables, with the host’s tools used for research and file creation.
- Workflow model tests retain their scope, original responses, and known limitations.

### Earlier versions

- **1.2.0:** Added review of existing results, preservation of valid work, and distinction between defects and conditional options.
- **1.1.0:** Prioritized workplace scenarios and natural requests, with clearer introduction and first-use guidance.
- **1.0.0:** Initial creative thinking skill.

[Full changelog (Chinese)](CHANGELOG.md)

## License

[MIT License](LICENSE).
