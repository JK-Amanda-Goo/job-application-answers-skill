# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.1.3] - 2026-08-30

### Added
- Step 4 working principle: tag every past employer with its identifying parenthetical (stage/funder, what it does, scale marker) on first mention, drafted in from the start rather than left for the Step 5 slop pass (checklist item 11) to catch. Prompted by a real run where the first draft named "Sendbird" bare and the tag had to be added on review.

## [0.1.2] - 2026-08-28

### Added
- Two new items on `references/ai-slop-checklist.md`'s review pass: (11) label a company's first mention with identifying keywords (funding stage, sector, scale) rather than assuming the reader knows it, and (12) use bullet points instead of forced prose when a question's answer is genuinely a parallel list (tooling, inputs/outputs) rather than a narrative.

## [0.1.1] - 2026-08-27

### Changed
- Added an explicit "Not for" clause to the skill description (resume/CV writing or review, mock-interview practice, LinkedIn/social posts, networking or outreach emails, offer negotiation, recommendation letters, choosing which companies to apply to). Chosen by hand after skill-creator's automated description-optimization tool (`run_loop.py`) turned out to be non-functional against the installed Claude Code CLI version — see the dev-journal entry for the diagnosis. The exclusion list itself covers the near-miss negative cases from the trigger eval set regardless of the tool issue.

### Added
- Initial release. A seven-step workflow for answering job application questions that draws out the user's own thinking before drafting, rather than generating a complete answer from the job description alone.
- Local workspace (`~/job-application-answers/`) with `profile/` for resume and career context, and `answers/` for an archive of past answers — kept outside the repo, with `.gitignore` rules as a second line of defense.
- Archive reuse: past answers are searched before drafting, since the same questions recur across applications. Offers reuse-as-is / adapt / write-fresh, and flags company-specific references in an old answer so nothing goes out naming the wrong employer.
- `references/question-type-playbook.md` — motivational, behavioral, case/technical, background, open-ended, and logistics questions, and the structure each rewards.
- `references/ai-slop-checklist.md` — ten concrete tells of machine-written text, plus the "could another applicant have submitted this?" test.
- `references/recruiter-hm-review-rubric.md` — separate recruiter (30-second screen) and hiring-manager (evidence and fit) lenses, run separately because an answer can pass one and fail the other.
- `assets/profile-template.md` — scaffold for the career-context file, prompting for the material applications keep needing but a resume can't hold.
- Default length of 2–3 paragraphs (~150–250 words) when an application form states no limit, which is the common case.
