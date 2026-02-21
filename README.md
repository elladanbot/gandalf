🧙 Gandalf

Gandalf is an autonomous execution engine for verifiable action.

Not a chatbot.
Not a copilot.
Not a workflow toy.

Gandalf turns intent into reality — and proves it happened.

⸻

The Problem

AI systems can speak fluently.
They cannot prove they actually did anything.

Logs can be fabricated.
Text can be hallucinated.
Claims are cheap.

Trust collapses.

⸻

The Gandalf Principle

If an action happened, it must leave a verifiable trace.

Every real action performed by Gandalf produces:
• A persistent artifact
• A concrete reference (commit, file, PR, hash, etc.)
• A human-readable proof object

No artifact → No action.

⸻

What Gandalf Is

Gandalf is a general-purpose execution layer where:
• Humans express intent
• Gandalf plans
• Gandalf executes deterministic operations
• The world changes
• Proof is generated automatically

Gandalf is not a model.
Gandalf is infrastructure around models.

⸻

Core Primitive: Receipts

A Receipt is Gandalf’s atomic unit of truth.

A receipt records:
• Intent
• Plan
• Actions
• Artifacts
• Verification commands
• Rollback instructions

Receipts are immutable once written.
Together, they form a verifiable ledger of reality.

⸻

Core Primitive: Skills

A Skill is a reusable, auditable operation.

Examples:
• Create repository
• Create branch
• Create file
• Modify file
• Run formatter
• Execute tests

Skills are plain-text definitions that declare:
• Inputs
• Operations
• Verification
• Rollback

Skills do not decide.
They only execute.

⸻

Runtime

Gandalf includes a small runtime that:
• Loads skills
• Injects inputs
• Renders operations
• Executes them locally
• Writes receipts

The runtime is intentionally minimal.

Complexity lives in receipts, not in opaque orchestration.

⸻

Properties

Gandalf is designed to be:
• Deterministic where possible
• Auditable by default
• Composable
• Human-verifiable
• Machine-readable

Every layer optimizes for trust, not vibes.

⸻

Mental Model

Think of Gandalf as:

Git + Makefile + Agent Brain + Proof System

But coherent.

⸻

Long-Term Vision

Gandalf becomes infrastructure for:
• Autonomous software engineering
• Research automation
• Operations & DevOps
• Scientific experimentation
• Agent collectives
• Self-improving systems

Where today we run scripts, tomorrow we run Gandalf.

⸻

Non-Goals

• Entertainment chatbots
• Prompt toys
• Fake autonomy demos
• Unverifiable “AI did X” claims

If Gandalf cannot prove it, Gandalf did not do it.

⸻

Status

Early stage.
Designing primitives before scale.

Speed later.
Correctness first.

⸻

One Sentence

Gandalf is an agent that proves it changed reality.

⸻

Repository Layout (Current 21 Feb 2026)

gandalf/
├─ receipts/
│  ├─ logs/            # Immutable executed receipts
│  ├─ templates/       # Receipt templates
│  └─ schema/          # JSON schema for receipts
│
├─ skills/
│  ├─ github/
│  │   ├─ create-repo.md
│  │   ├─ create-branch.md
│  │   └─ create-file.md
│  └─ filesystem/
│      └─ create-file.md
│
├─ bin/
│  └─ run-skill        # Minimal skill runtime
│
└─ README.md

⸻

What Is a Skill (Practically)

A skill is a plain-text file that declares:
• Inputs
• Operations to run
• Verification commands
• Rollback commands

Example (simplified):

# Skills: github.create-repo

Creates a GitHub repository using GitHub CLI.

Inputs:
- repo_name
- visibility

Operation:
gh repo create "$repo_name" --$visibility

Skills are deterministic execution units.
They do not contain reasoning.
They only declare how.

⸻

What Is run-skill

run-skill is a small local runtime that:

1. Loads a skill file
2. Injects inputs
3. Renders operations
4. Executes them
5. Writes a receipt

It is intentionally simple and auditable.

⸻

Running a Skill (Example)

./bin/run-skill github.create-repo repo_name=my-app visibility=private

If the action succeeds, a new receipt is written to:

receipts/logs/

That receipt becomes the permanent proof.

⸻

Design Philosophy

• Receipts are the source of truth
• Skills are reusable execution blocks
• Runtime stays minimal
• Intelligence lives outside execution

⸻

What We Are Not Optimizing For Yet

• Performance
• Parallelism
• Cloud orchestration
• UX polish

Correctness first.
Trust first.