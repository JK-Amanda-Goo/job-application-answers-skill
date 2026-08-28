# Recruiter and hiring-manager review

Two people read this answer, they read it differently, and an answer can clear one while failing the other. Run both lenses separately rather than blending them into a general "is this good?" — the blended version reliably misses things.

## Lens 1 — The recruiter

**Situation:** screening a stack of applications, roughly thirty seconds each, deciding advance-or-reject. Not a domain expert in the role. Mostly matching against the JD and scanning for reasons to stop reading.

Check:

**Does it visibly match the JD?**
The recruiter is holding requirements in their head. If the JD's central ask is "experience taking a 0→1 product to market" and the answer never touches that, it fails — even if it's a great answer to some other question. Not keyword-stuffing; the substance needs to line up with what they're screening for.

**Is there a clear reason to advance?**
After thirty seconds, could they articulate one sentence of why this person moves forward? If the answer is competent but leaves no single impression, it dies in the stack. Competent and forgettable is the most common failure mode, and it doesn't feel like failure when you're writing it.

**Any red flag or unanswered question?**
- A gap, pivot, or short tenure raised but not explained
- Seniority mismatch with the role (over- or under-)
- Location or work-authorization ambiguity when the JD is specific
- Anything that reads as negative about a previous employer
- Enthusiasm that doesn't match the actual role (applying to a niche infra role with generic "I love building products")

**Does it read fast?**
Dense paragraphs, buried lede, jargon requiring domain knowledge the recruiter doesn't have. The first sentence should carry weight — assume the rest may be skimmed.

## Lens 2 — The hiring manager

**Situation:** will actually work with this person. Knows the domain deeply. Reads fewer answers, more carefully. Asking whether this person can do the job and whether they'd be good to work with.

Check:

**Is this evidence, or just a claim?**
The central question. "I'm strong at cross-functional collaboration" is a claim. "Eng wanted to ship the simpler version and I disagreed; we ran a two-week test and I turned out to be wrong about which mattered" is evidence. Hiring managers discount claims almost entirely — they've read thousands. Every important assertion needs something behind it.

**Are the specifics real?**
Numbers, timeframes, named tools, actual decisions, tradeoffs made. Vague scale ("significantly improved," "large user base") reads as either inflated or not-actually-owned. Real specifics also survive the interview — a made-up-sounding claim invites questions the applicant can't answer.

**Did they do this, or were they nearby?**
Watch for "we" doing all the work with no clear personal contribution. Hiring managers are calibrated on this. The answer should make the applicant's own role unambiguous without overclaiming the team's work.

**Does it fit *this* team's context?**
A 50-person startup and a 5,000-person company want different things from the same job title. An answer optimized for one can read as a poor fit for the other. Signals in the JD: team size, stage, whether they emphasize process or autonomy, what they list first.

**Do they understand the actual problem?**
For case or technical questions especially — does the answer show real understanding of the difficulty, or is it a plausible-sounding structure with nothing underneath? Hiring managers spot this instantly, since it's their domain.

**Would I want to work with this person?**
Harder to check but real. Things that hurt: arrogance, hedging everything, no evident opinions, blaming others in a failure story, treating a failure question as a disguised humblebrag.

## Reporting back

After applying fixes, tell the user briefly what the review caught — one or two lines, not a rubric dump. Something like: "리크루터 관점에서 JD의 핵심 요구사항인 0→1 경험이 안 드러나서 첫 문단에 끌어올렸고, HM 관점에서 '팀이 개선했다'로 읽히는 부분을 본인 역할이 분명하게 고쳤어요."

This matters for two reasons: the user learns what to watch for next time, and they can push back if you changed something they cared about. Silent edits to someone's own story are the wrong default.
