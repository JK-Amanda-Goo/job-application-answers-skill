# Job Application Answers (Claude Code skill)

Helps you write answers to job application questions — "why do you want to work here," "tell us about a time you...," supplemental essays, any free-text field on an application form.

The point of this skill is that it **doesn't just write the answer for you**. An AI can produce a polished, competent, completely forgettable application answer in one shot, and recruiters read hundreds of those. What makes an answer land is a specific detail only you could have written. So the workflow asks for your thinking first, then does the work of structuring and pressure-testing it.

## How it works

1. **Profile setup** *(first run only)* — you supply your resume plus the context that applications keep needing: the projects you'd want to talk about in depth, how you'd explain your career path, what you're actually looking for, your constraints. Saved locally so you never paste it again.
2. **Intake** — company, position, job description, the question, and a length limit if the form gives one. Defaults to 2–3 paragraphs (~150–250 words) when it doesn't.
3. **Archive check** — searches your past answers first. People answer the same handful of questions across many applications, and adapting a refined answer beats rewriting from scratch. If a similar one exists you're shown it and offered *reuse as-is / adapt / write fresh* — with any company-specific references flagged so nothing goes out with the wrong company's name in it.
4. **Your thinking** — you're asked what comes to mind before any draft exists. Keywords, bullets, a half-written sentence, all fine. This happens *before* the skill offers its own angles, because a suggested angle turns the answer into the model's idea with your permission rather than yours with the model's help. Stuck? It'll pull candidate angles from your profile instead.
5. **Draft** — built on your material, structured to the question type (behavioral, motivational, case, background all want different shapes).
6. **AI-slop pass** — checked against a concrete list of machine-writing tells: manufactured enthusiasm, buzzwords, three-item lists, "not just X but Y," uniform sentence rhythm, abstract self-praise.
7. **Recruiter + hiring-manager review** — read twice more through two different lenses, since they screen for different things. You're told what the review caught and what changed.
8. **You confirm**, then it's archived for reuse.

## Your data stays local

Nothing is uploaded anywhere. The skill keeps your material in a workspace folder outside this repo:

```
~/job-application-answers/
├── profile/     # resume + career context
└── answers/     # past answers, searched for reuse
```

The repo's `.gitignore` blocks personal files as a second line of defense. If you fork this, keep it.

## Install

```bash
git clone https://github.com/JK-Amanda-Goo/job-application-answers.git ~/.claude/skills/job-application-answers
```

Then just say what you need in a Claude Code session:

> "지원서 질문 하나 답변해야 하는데 도와줘" · "Help me answer this application question" · or paste a JD and a question

## Requirements

- Claude Code (or another agent that supports skills)
- Nothing else — no API keys, no external services

## Voice

If you have a personal writing-voice skill (something like `yourname-voice`), this skill will use it when drafting. Without one, it takes voice cues from how you wrote your own notes in step 4 — your fragments are a voice sample.

## What this intentionally doesn't do

- **Write without your input.** If you have genuinely nothing, it offers angles from your profile rather than inventing experience. It won't fabricate a story you didn't tell it.
- **Submit anything.** It drafts; you paste.
- **Optimize for ATS keyword stuffing.** It connects to what a JD actually asks for, which is a different thing.

## Files

- `SKILL.md` — the workflow
- `references/question-type-playbook.md` — question types and the structure each rewards
- `references/ai-slop-checklist.md` — concrete tells of machine-written text
- `references/recruiter-hm-review-rubric.md` — the two review lenses
- `assets/profile-template.md` — scaffold for your career context file

## Releasing

Every notable change gets a `CHANGELOG.md` entry (Keep a Changelog format), a matching git tag, and a GitHub Release whose notes are that changelog section:

```bash
# 1. Add a new version section to the top of CHANGELOG.md
# 2. git add -A && git commit -m "..."
git tag -a vX.Y.Z -m "vX.Y.Z - <one-line summary>"
git push origin main --tags
gh release create vX.Y.Z --title "vX.Y.Z" --notes "<paste the CHANGELOG section>"
```

## License

MIT — see `LICENSE`.
