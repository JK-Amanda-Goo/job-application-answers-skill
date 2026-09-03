# Hiring-manager outreach message

An optional follow-on once an application's answers are done: a short message the applicant can send the hiring manager (or recruiter) on LinkedIn, alongside or just after the application.

The whole job of this message is to make one busy person think *I should talk to this person* — before they've opened the applicant's resume. It is not a cover letter, not a summary of the application, and not an introduction of the form "I recently applied and wanted to reach out." It is one proof point, aimed at this role, delivered fast.

## The bar

A hiring manager gets these constantly and archives most in under five seconds. The ones that survive share a shape: the first line is a specific thing the sender has done, not a statement that they'd like to be considered. If the first line could have been sent by any applicant, it's already lost.

Assume the reader will read exactly the first sentence and decide from it whether to read the rest.

## Length

- **LinkedIn connection note:** 300 characters, hard limit. Roughly 45–55 words. One proof point, the role, one line of fit. Nothing else fits and nothing else should.
- **Direct message / InMail:** keep it to 75–110 words even though more is allowed. Four beats (below), each 1–2 sentences. If it runs past ~120 words it reads as a wall and gets deferred.

Default to the shorter one unless the user says they can already message the person directly.

## The four beats

1. **Hook — a specific thing you did.** Pull the single most role-relevant proof point from the application you just wrote. Lead with the outcome or the artifact, not the job title. "I took a YC company's first self-serve AI product from zero to 2,000 customers in two months" — not "I'm a product manager with experience in 0→1 products."
2. **The role, named, and why this proof maps to it.** One sentence connecting what you just said to what this specific role needs — drawn from the JD's real requirements, not its boilerplate. This is the line that says *I read the actual job.*
3. **One more concrete detail.** A second number, a named tool, a decision, a thing you built. Enough that the reader believes beat 1 rather than just noting it. Keep it to one — two supporting details is a paragraph, not a message.
4. **A low-friction close.** Offer a short conversation or to share more, as a peer would. Not "I would be grateful for your consideration." Something like "Happy to walk through how I'd approach [specific problem from the JD] — worth a quick call?"

## What kills it

- **Opening with the ask.** "I'm reaching out because I recently applied for..." — delete. Start on the proof.
- **Flattery.** "I've long admired [Company]'s work" / "your mission deeply resonates with me." The reader has read it a thousand times and it signals nothing. If there's genuine specific interest, make it a fact — "I've been running your API in a side project since March" — or leave it out.
- **Summarizing the resume.** They can open it. The message earns the resume open; it doesn't replace it.
- **Every slop tell in `ai-slop-checklist.md`.** Run that pass on this message too — manufactured enthusiasm, buzzwords, rule of three, "not just X but Y," formulaic openings and closings. A short message has nowhere to hide them.
- **Hedging.** "I think I could potentially be a strong fit." You did the work; state it.
- **Length.** The single most common reason these don't get answered. When in doubt, cut a sentence.
- **No clear role.** If the reader can't tell which opening you mean in one glance, the message asks them to do work before they've decided you're worth it.

## Reuse, don't re-derive

The application answers you just wrote already contain the proof points, the numbers, and the JD-fit reasoning. This message is a compression of that material into 3–4 sentences, not a fresh analysis. Pull the strongest single thread and cut everything else.

Carry the company-identifying parenthetical on a past employer's first mention here too (`Sendbird (YC W16, chat/AI-agent API platform)`) — the reader has even less context in a cold message than in an application, and it's still evidence of caliber. Keep it tight; in a 90-word message the tag is three words, not a clause.

## Worked examples (generic)

**Connection note (52 words):**

> I took a YC company's first self-serve AI product from 0 to 2,000 customers in two months as its founding PM. Saw you're hiring a Senior PM to build out the self-serve motion — that 0→1 activation problem is the one I've spent the last two years on. Would love to compare notes.

**Direct message (98 words):**

> Hi [Name] — I applied for the Senior PM role on the growth team, but wanted to reach out directly because the JD's core problem is one I've worked on hands-on.
>
> At [Company] (Series A, speech-AI app, 5M+ downloads) I owned the creator-led acquisition channel: co-made five videos past 2M views each and pushed installs up 10% in a single week with no paid spend. Before that I ran 0→1 self-serve at a $1B API company.
>
> Your JD emphasizes finding a repeatable loop, not one-off spikes — happy to walk through how I'd approach that here. Worth a short call?

## Reporting back and archiving

Show the message with a character count (for a connection note) or word count (for a DM), and one line on which proof point you led with and why.

Once the user is happy, archive it to `~/job-application-answers/answers/` as `YYYY-MM-DD-company-position-outreach-message.md`, with `question: Hiring-manager outreach message` in the frontmatter. It's reusable material the same way the answers are — the next application to a similar role can adapt it.
