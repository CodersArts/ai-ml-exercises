# Contributing to ai-ml-exercises

First off — thank you. Every solution, fix, and improvement makes this library more useful for the thousands of engineers who use it. This guide explains how to contribute in a way that keeps the repo consistent and high-quality.

---

## Table of contents

- [What you can contribute](#what-you-can-contribute)
- [Before you start](#before-you-start)
- [How to add a solution](#how-to-add-a-solution)
- [Solution file template](#solution-file-template)
- [Code quality standards](#code-quality-standards)
- [How to report a bug or request a task](#how-to-report-a-bug-or-request-a-task)
- [Review process](#review-process)
- [Community guidelines](#community-guidelines)

---

## What you can contribute

| Contribution type | Welcome? | Notes |
|-------------------|---------|-------|
| Add a solution to an unsolved task | ✅ Yes | Most needed — see open issues |
| Fix a bug in an existing solution | ✅ Yes | Include a test case that reproduces the bug |
| Improve an explanation or add a diagram | ✅ Yes | Clarity improvements are always welcome |
| Add a new task to an existing pillar | ✅ Yes | Must follow the task template and be approved first |
| Request a new pillar / major change | ✅ Yes | Open a Discussion first, not a PR |
| Translate a task to another language | ✅ Yes | Create a `tasks/[pillar]/[locale]/` subdirectory |
| Add a dataset | ⚠️ Case-by-case | Must be open licence (CC, MIT, or public domain) |
| Promotional content | ❌ No | This is a learning resource, not an ad platform |

---

## Before you start

1. **Check open issues first.** Someone may already be working on the same task. Look for the `solution needed` label.

2. **Comment on the issue** you want to solve. Say "I'll take this one" so we can assign it to you and avoid duplicate work.

3. **Fork the repo** and work on a branch — never commit directly to `main`.

4. **Keep one PR per task.** Do not bundle multiple solutions into one pull request.

---

## How to add a solution

### Step 1 — Fork and clone

```bash
git clone https://github.com/YOUR_USERNAME/ai-ml-exercises.git
cd ai-ml-exercises
git checkout -b solution/T016-missing-values
```

Branch naming convention:
- `solution/T016-missing-values` — adding a new solution
- `fix/T066-xgboost-typo` — fixing a bug
- `improve/A009-ragas-evaluation` — improving explanation

### Step 2 — Create the solution file

Solutions live in `solutions/[pillar]/` mirroring the task file structure.

```
tasks/cl/T016-missing-values.md        ← the exercise (problem + starter code)
solutions/cl/T016-missing-values.md    ← your solution (full code + explanation)
```

If the task file doesn't exist yet, create both.

### Step 3 — Use the template

Copy the template below. Do not skip sections — reviewers will ask you to fill them in.

### Step 4 — Test your code

Every code block in your solution must run without errors on Python 3.10+.

```bash
# Create a clean environment
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt

# Run your solution file
python solutions/cl/T016_missing_values.py
```

If your solution requires additional packages beyond `requirements.txt`, add them and include the install command clearly in your file.

### Step 5 — Open a pull request

- Title: `[Solution] T016 — Handle missing values: drop, fill, interpolate`
- Link the issue number in the PR description: `Closes #42`
- Fill in the PR checklist (it appears automatically)

---

## Solution file template

Copy this exactly. Replace everything inside `{{ }}`.

````markdown
# {{ Task ID }} — {{ Task Title }}

**Pillar:** {{ Pillar name }}  
**Difficulty:** {{ Beginner / Intermediate / Advanced }}  
**Contributor:** [@{{ your_github_username }}](https://github.com/{{ your_github_username }})  
**Tested on:** Python {{ version }}, {{ key library }} {{ version }}

---

## Problem statement

{{ 2–4 sentences describing the real-world scenario. Write as if explaining to a junior engineer on their first day. Avoid jargon without explanation. }}

---

## What you will learn

- {{ Learning outcome 1 }}
- {{ Learning outcome 2 }}
- {{ Learning outcome 3 }}
- {{ Add more as needed }}

---

## Prerequisites

- {{ e.g. Python basics (loops, functions) }}
- {{ e.g. pandas installed: pip install pandas }}

---

## Dataset / setup

```python
{{ Self-contained dataset creation code.
   Must run with zero external files.
   Use numpy random seeds for reproducibility. }}
```

---

## Starter code

> **Your task:** Replace every `???` so the final output matches the expected result shown at the bottom.

```python
{{ Starter code with deliberate gaps marked as ???.
   3–7 gaps is the sweet spot.
   Gaps should test understanding, not trivial syntax. }}
```

**Expected output:**
```
{{ Paste the exact terminal output the completed code should produce. }}
```

---

## Solution

```python
{{ Full working solution.
   Add a comment on every non-obvious line.
   Use f-strings and modern Python idioms.
   Must be runnable from top to bottom with no edits. }}
```

---

## Explanation

### {{ Key concept 1 }}
{{ 2–4 sentences explaining WHY this works, not just WHAT it does. }}

### {{ Key concept 2 }}
{{ Continue as needed. Use tables for comparisons. }}

---

## Common mistakes

- **{{ Mistake 1 }}** — {{ Why it's wrong and how to fix it }}
- **{{ Mistake 2 }}** — {{ Why it's wrong and how to fix it }}
- **{{ Mistake 3 }}** — {{ Why it's wrong and how to fix it }}

---

## Challenge extension

1. {{ Harder variation of the same problem }}
2. {{ Integration with the next task in sequence }}
3. {{ Real-world dataset version }}

---

## Related tasks

- [{{ Task ID }} — {{ Title }}](../../tasks/{{ pillar }}/{{ filename }}.md)
- [{{ Task ID }} — {{ Title }}](../../tasks/{{ pillar }}/{{ filename }}.md)

---

> **Working on a similar problem with your own data?**  
> [Request 1:1 help from a Codersarts ML expert →](https://codersarts.dev/contact)
````

---

## Code quality standards

### Python style

- Python 3.10+ syntax
- Follow [PEP 8](https://peps.python.org/pep-0008/) — use `black` or `ruff` to auto-format before submitting
- Use type hints on function signatures
- Maximum line length: 100 characters
- Use f-strings, not `.format()` or `%`

```bash
# Format before committing
pip install black
black solutions/cl/T016_missing_values.py
```

### Code blocks

- Every code block must be fenced with the language tag: ` ```python `, not just ` ``` `
- Include `import` statements at the top of every block — never assume the reader has run the previous block
- Add `# ---` section dividers for clarity in long scripts

### Explanations

- Write for someone who has seen Python before but not this specific technique
- Prefer short paragraphs over long ones — one idea per paragraph
- Use tables to compare options (e.g. IQR vs Z-score)
- No walls of text — break up with subheadings if over 150 words

### Output

- Include exact expected output as a code block (```` ```text ```` or ```` ``` ````)
- Round printed floats to 3–4 decimal places for readability
- If output is large (e.g. a DataFrame), show only the first 5 rows with `print(df.head())`

---

## How to report a bug or request a task

### Bug in an existing solution

1. Open an issue with the title: `[Bug] T066 — XGBoost solution: wrong feature importance axis`
2. Include:
   - The task ID and file path
   - What you expected to happen
   - What actually happened (paste the error or wrong output)
   - Your Python version and OS
   - A minimal reproduction snippet if possible

### Request a new task

1. Open an issue with the title: `[Task Request] Add: Fine-tune Gemma 2 with QLoRA`
2. Include:
   - Which pillar it belongs to
   - Why it's in demand (link to a job posting, tweet, or paper if you have one)
   - Suggested difficulty and tools

We review task requests weekly and add approved ones to the backlog with the `task approved` label.

### Request a solution for a specific task

Comment on the task's open issue or open a new one tagged `solution needed`. The maintainers and community will prioritise based on demand.

---

## Review process

All pull requests go through this process:

| Step | Who | What they check |
|------|-----|----------------|
| Automated checks | GitHub Actions | Code runs without errors, file is in correct location |
| Content review | Maintainer | Template followed, explanation clarity, code quality |
| Final merge | Maintainer | Merged to `main`, issue closed |

**Typical turnaround:** 48 hours on weekdays, longer on weekends.

If your PR has been open for more than 5 days with no response, ping `@codersarts-maintainers` in a comment.

### What causes a PR to be sent back

- Code does not run (`python solution.py` throws an error)
- Missing sections in the template (especially "Common mistakes" and "Expected output")
- Explanation is missing or only restates the code without explaining why
- Starter code gaps are too easy (trivial `???` that test syntax, not understanding)
- No `random_state` or `np.random.seed` — output must be reproducible

---

## Community guidelines

This repo follows the [Contributor Covenant](https://www.contributor-covenant.org/) Code of Conduct.

In short:

- Be kind and constructive in issue comments and PR reviews
- Assume good intent — not everyone is a native English speaker
- Focus feedback on the code and explanation, not the person
- No self-promotion or off-topic links in issues or PRs

Violations can be reported to `contact@codersarts.com`. We take this seriously.

---

## Recognition

Contributors are listed in [CONTRIBUTORS.md](CONTRIBUTORS.md) and mentioned in our monthly newsletter. Top contributors (5+ merged solutions) get a free 1:1 session with a Codersarts ML expert.

---

## Questions?

- Open a [GitHub Discussion](https://github.com/codersarts/ai-ml-exercises/discussions) for general questions
- Join our [Discord](https://discord.gg/CM2YQpbRAN) for real-time chat
- Email `contact@codersarts.com` for anything else

Thank you for making this better. Every solution helps someone get unstuck.

— The Codersarts team
