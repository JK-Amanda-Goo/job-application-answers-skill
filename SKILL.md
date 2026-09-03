---
name: job-application-answers
description: Drafts answers to written job-application questions by first drawing out the user's own thinking, then shaping it into a concise, specific, human-sounding answer — with an AI-slop pass and a recruiter/hiring-manager review before it reaches the user. Once the answers are done it can also draft a short hiring-manager outreach message to send with the application. Also reuses their past answers when a similar question comes up again. Use this skill whenever someone is filling out a job application and needs to write a free-text answer: "why do you want to work here," "tell us about a time you...," "what interests you about this role," a supplemental essay, a cover-letter-style prompt, or any open text field on an application form. Trigger it when the user pastes a job description alongside a question, says they're applying somewhere and needs help writing something, mentions a question they keep getting asked on application forms, or asks for help with application or cover-letter wording — even if they never say the words "application question." Not for resume/CV writing or review, mock-interview practice, LinkedIn or social feed posts, standalone networking or cold-outreach messages unconnected to an application you're writing, offer negotiation, recommendation letters, or deciding which companies to apply to — those are adjacent but different tasks.
---

# Job Application Answers

Write application answers that sound like the applicant, not like a language model — by making the applicant the source of the substance and taking on the work of structuring, tightening, and pressure-testing it.

The trap this skill exists to avoid: an AI can produce a polished, competent, utterly forgettable application answer in one shot. Recruiters read hundreds of those. What makes an answer land is a specific detail only this person could have written — a real number, a real decision, a real thing that went wrong. That material lives in the applicant's head, not in the job description. So the workflow spends its first move *asking* rather than *writing*.

## The workspace

All user data lives outside this skill directory, in a workspace folder:

```
~/job-application-answers/
├── profile/     # resume + career context, read on every run
└── answers/     # archive of past answers, searched for reuse
```

Create it on first use. Never commit anything from it into this skill's repo — it holds a real person's resume and career history. If the user prefers a different location, respect it and remember it; nothing here depends on the exact path.

## Step 0 — Profile setup (first run only)

Check whether `~/job-application-answers/profile/` exists and has content. If it does, read it and move on — don't make the user re-supply it.

If it's empty or missing, explain briefly why this is worth two minutes: these answers get much better with real material to draw on, and setting it up once means never pasting a resume again.

Ask for:
- **Resume** — paste, or a path to a PDF/docx/md file (read it and save a markdown version).
- **Anything else that keeps coming up in applications.** Prompt with concrete examples, because "other context" is too vague to answer cold: the two or three projects they'd want to talk about in depth (resume gives one line; an answer needs the story), how they'd explain their career path or a gap or a pivot, work-authorization or location constraints, what they're actually looking for in the next role, and any story they find themselves telling in every interview.

Save to `profile/resume.md` and `profile/context.md`. Use `assets/profile-template.md` as the scaffold for the second file.

Tell the user they can edit these files directly anytime, and offer to update them when something new comes up in conversation.

## Step 1 — Intake

Collect, asking only for what's missing:

1. **Company**
2. **Position**
3. **Job description** (paste)
4. **The question**
5. **Length limit**, if the form states one

On (5): many forms don't specify. If the user doesn't mention a limit, don't interrogate them about it — default to **2–3 paragraphs, roughly 150–250 words**, and say that's what you're targeting so they can redirect. That length is long enough to carry a real example and short enough that a recruiter reads all of it.

Applications usually ask several questions. Keep company/position/JD for the rest of the session so the user only pastes them once, and expect follow-up questions for the same application.

## Step 2 — Check the archive before writing anything

People apply to many companies and answer the same handful of questions over and over. Rewriting from scratch each time wastes the user's effort and produces *worse* answers, because the earlier one was already refined through this whole process.

Search past answers:

```bash
grep -H -e '^question:' -e '^company:' -e '^position:' ~/job-application-answers/answers/*.md 2>/dev/null
```

Judge similarity by what the question is actually *asking for*, not string overlap. "Why do you want to work here?" and "What draws you to our mission?" want the same underlying material. "Tell us about a time you led through conflict" and "Tell us about a time you failed" do not.

If you find a close match, read that answer and show it to the user before drafting. Offer three paths, and say which one you'd pick and why:

- **Reuse as-is** — realistic only when the old answer is company-agnostic. Most aren't.
- **Adapt** — usually the right call. Keep the spine and the specific evidence; replace the company-specific reasoning with reasoning about *this* company and JD.
- **Write fresh** — when the angle genuinely doesn't transfer, or the user has since done something better to talk about.

Before proposing reuse, scan the old answer for anything welded to the old employer: company name, their product, their mission language, a detail that only made sense for that role. Flag those explicitly — a pasted answer with the wrong company name in it is the single most damaging thing this skill could produce.

If nothing similar exists, say so briefly and continue.

## Step 3 — Ask for the user's thinking (do not skip to drafting)

This is the step that makes the difference, and it's the one that's tempting to skip because drafting first *feels* more helpful.

Ask something like:

> 이 질문에 대해 떠오르는 생각을 편하게 주세요 — 키워드, 불렛, 반쯤 쓴 문장, 뭐든 괜찮아요. 특히 꼭 들어갔으면 하는 경험이나 표현이 있으면 알려주세요.

Ask **before** offering your own angles. If you propose three directions first, the user picks one and the answer becomes yours with their permission rather than theirs with your help — and it will read that way. Their unpolished fragment is better raw material than your polished guess.

Accept whatever comes back: a few words, a messy paragraph, a voice-memo transcript, half of it in another language.

**When they're stuck** (they say they have nothing, or ask you to just write it): don't push twice. Pull two or three candidate angles from `profile/` — real projects or experiences that would answer this question — and present them as a menu with a one-line sketch each. Picking from real material still routes through their judgment, which is most of what authenticity requires. Then ask one or two specific follow-ups about the one they choose ("what was actually hard about it?", "what number would show it worked?"), because those answers become the concrete details that carry the piece.

## Step 4 — Draft

Build the answer on what they gave you. Your job is structure, compression, and connection — not invention. If you find yourself adding a claim they didn't make, stop: either ask, or cut it.

Match the structure to what the question is doing. See `references/question-type-playbook.md` for the common types (behavioral, motivational, case/technical, background, open-ended "anything else") and what actually works for each — the structure that makes a "why us" answer land is different from the one a "tell us about a time" answer needs.

Working principles:
- **Lead with the specific, not the frame.** "I spent six months rebuilding onboarding for users who'd churned" beats "I'm passionate about user-centric product development."
- **Connect to this JD's real requirements**, not its boilerplate. Most JDs have two or three things that actually matter and a lot of standard language; answer the former.
- **One example, developed** beats three, listed. Depth is what's scarce.
- **Tag every past employer on first mention.** When you name a company from `profile/`, carry its short identifying parenthetical — stage/funder, what it does, a scale marker if one is true and known (`Sendbird (YC W16, chat/AI-agent API platform, $1B valuation)`). The reader has no reason to know a past employer or portfolio company, and the tag is evidence of caliber, not decoration. Draft it in from the start rather than leaving it for the Step 5 pass to catch. Later mentions in the same answer don't repeat the full tag.
- **Keep their words** where they wrote something well. If they said "it was a mess for about a month," that's often better than anything you'd substitute.
- **Respect the length limit.** If there isn't one, 150–250 words.

## Step 5 — AI-slop pass

Read the draft as an editor whose only job is catching machine-sounding writing, then fix what you find. This matters practically, not just aesthetically: recruiters now read these answers specifically watching for AI-generated text, and the tells are well known.

Work through `references/ai-slop-checklist.md`. The highest-yield checks: manufactured enthusiasm, buzzwords, three-item lists, "not just X but Y," uniform sentence rhythm, and abstract self-praise with no concrete anchor.

Fix silently — don't narrate the checklist at the user.

## Step 6 — Recruiter and hiring-manager review

Now read the draft twice more, as two different people who will actually see it. They screen for different things, and an answer can pass one and fail the other.

- **Recruiter**, thirty seconds: Does this match what the JD asks for? Is there an obvious reason to advance them? Any red flag or unanswered question? Does it read fast?
- **Hiring manager**, actually evaluating: Is this evidence they can do the job, or just a claim that they can? Are there real specifics — numbers, decisions, tradeoffs? Does it fit this team's context? Would I want to work with this person?

Use `references/recruiter-hm-review-rubric.md` for the full lenses. Apply the fixes, then tell the user briefly what the review caught and what you changed — that's the part they learn from, and it's how they can push back if you changed something that mattered to them.

## Step 7 — Confirm and archive

Show the final answer with a short note on what changed in review and the word count.

Ask for confirmation. If they want changes, revise and re-run Steps 5–6 — a revised draft hasn't been through the review passes.

Once they're happy, save to `~/job-application-answers/answers/` as `YYYY-MM-DD-company-position-question-slug.md`:

```markdown
---
company: Acme
position: Senior Product Manager, Payments
question: Why do you want to work at Acme?
date: 2026-08-27
word_count: 187
---

[final answer]
```

The frontmatter is what makes Step 2 work later, so fill it in accurately — especially `question`, stored as the full question text rather than a paraphrase.

Then continue to Step 8.

## Step 8 — Offer a hiring-manager outreach message

Once this application's answers are done, offer one more thing: a short message the user can send the hiring manager or recruiter on LinkedIn, alongside the application. A well-aimed note gets a real person to open the resume — which is most of what an application is trying to earn.

Offer it **once per application**, after the answers are finished — not after every question. Ask in English, since the user sends these in English regardless of the language you're working in:

> Your answers are set. Want me to draft a short LinkedIn message to the hiring manager to go with this — just a tight intro and why you fit the role, aimed at getting them to want a conversation?

If they decline, offer the next question or the next application and stop.

If they want it, draft per `references/hiring-manager-outreach.md`. The essentials:

- **It's a compression of the answers you just wrote**, not fresh analysis. Pull the single strongest role-relevant proof point and cut everything else.
- **Lead with a specific thing they did**, never with the ask. The first sentence decides whether the rest gets read.
- **Name the role and connect the proof to what the JD actually needs** in one line — that's what signals they read the real job.
- **Keep it to length**: a LinkedIn connection note is 300 characters (~45–55 words); a direct message stays 75–110 words. Default to the shorter one unless the user says they can message the person directly.
- **Run the `ai-slop-checklist.md` pass on it too.** A short message has nowhere to hide manufactured enthusiasm or a formulaic opening.

Show the draft with a character count (connection note) or word count (DM) and one line on which proof point you led with and why. On confirmation, archive it to `~/job-application-answers/answers/` as `YYYY-MM-DD-company-position-outreach-message.md` with `question: Hiring-manager outreach message` in the frontmatter, then offer the next question or application.

## Voice

If the user has a personal writing-voice skill (something like `<name>-voice`), use it in Steps 4–6 — it'll capture how they actually write far better than generic guidance. Check the available skills for one before drafting.

Otherwise, take voice cues from what they wrote in Step 3 and from `profile/context.md`. Their fragments are a voice sample; match their register rather than defaulting to formal application-ese.

This applies to the Step 8 outreach message too.

## Reference files

- `references/question-type-playbook.md` — question types and the structure that works for each (Step 4)
- `references/ai-slop-checklist.md` — concrete tells of machine-written text (Step 5)
- `references/recruiter-hm-review-rubric.md` — the two review lenses (Step 6)
- `references/hiring-manager-outreach.md` — shape, length, and anti-patterns for the outreach message (Step 8)
- `assets/profile-template.md` — scaffold for `profile/context.md` (Step 0)
