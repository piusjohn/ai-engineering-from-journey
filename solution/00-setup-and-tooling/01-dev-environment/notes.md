# What I Learned: Dev Environment

Phase 00: Setup & Tooling · Lesson 01

Source: [Dev Environment](../../../phases/00-setup-and-tooling/01-dev-environment/docs/en.md)

Completion: Reported complete by me; recorded on 2026-10-26.
These notes were drafted from the lesson content for my review and submission.
Exercise outputs and quiz scores have not been recorded yet.

## What I learned

I learned that a reliable development environment is the foundation for working
through the AI engineering curriculum.

- The environment has four layers: system tools, package managers, language
  runtimes, and AI libraries. Setup proceeds from the foundation upward.
- Python supports much of the machine learning work, Node.js supports the
  TypeScript tooling, Rust supports systems work, and Julia is useful for math.
- Virtual environments isolate Python dependencies between projects.
- Package and runtime managers help install and manage the tools a project uses.
- Verification should match the learning route. Optional tools for later lessons
  do not need to block the first lesson.
- GPU support depends on the hardware and backend: NVIDIA uses CUDA, Apple
  Silicon can use MPS, and CPU execution remains useful for many lessons.

## Practical takeaway

I should check the active runtime and environment when diagnosing missing
packages or version conflicts. Installing a package into a different environment
from the one running my code can cause import failures.

The lesson provides this beginner-route verification command, run from the
repository root:

```bash
python3 phases/00-setup-and-tooling/01-dev-environment/code/verify.py --route beginner
```

## Evidence to add

My installed runtime versions, virtual environment location, and the output of
my route verification have not been recorded yet.
