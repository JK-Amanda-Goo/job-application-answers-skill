# Changelog

All notable changes to this project are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

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
