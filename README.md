# Apply Connect 2.0

**[View interactive prototype](https://saurabhsudhir15.github.io/apply-connect-prototype/)**

A PM case study and interactive prototype for a browser extension that eliminates application friction for job seekers on LinkedIn.

---

## The Problem

Active job seekers on LinkedIn abandon applications the moment they click Apply on a non-Easy Apply role. They get redirected to a third-party ATS portal (Workday, Greenhouse, iCIMS), hit a registration wall, and are asked to re-enter everything that already exists on their LinkedIn profile.

53% of job seekers surveyed stopped applying because of this. 67% built workarounds.

## The Solution

Apply Connect 2.0 is a browser extension that activates automatically when a user is redirected to a supported ATS. It pre-fills email on the account creation screen, uploads the LinkedIn resume to trigger the ATS's own parse and fill process, and populates remaining structured fields from the user's profile. The user lands on a largely pre-filled form instead of a blank one.

Account creation is reduced, not eliminated. The only field left is setting a password.

## User Flow

| Step | What the User Does | What the Extension Does |
| :---- | :---- | :---- |
| 1 | Clicks Apply on a LinkedIn listing | Detects redirect to a supported ATS |
| 2 | Lands on account creation page | Pre-fills email. User sets password only. |
| 3 | Sees application form | Uploads resume, triggers ATS parse and fill, pre-fills structured screening questions |
| 4 | Reviews and submits | Nothing is locked. User is always in control. |

## PM Process

This prototype was built as part of a structured product sprint:

1. **Problem framing** - root cause analysis of application abandonment across LinkedIn's job seeker flow
2. **Solution brainstorming** - 9 solutions generated using root-cause analysis and analogy thinking, ranging from quick wins to moonshots
3. **Prioritization** - RICE scoring across all solutions. Apply Connect 2.0 scored 13.5 (P0). Next best: 4.0.
4. **PRD** - 7-section product requirements document covering problem, solution, user flow, metrics, risks, and scope decisions
5. **Prototype** - 4-screen interactive HTML prototype of the complete user flow

## Success Metrics

| Metric | Definition |
| :---- | :---- |
| External application completion rate (P0) | % of extension-activated sessions where a form submit is detected on the ATS page |
| Extension activation rate | % of eligible redirect sessions where the extension successfully activates |
| 30-day repeat usage rate | % of users who use the extension on more than one application within 30 days of install |
| 7-day uninstall rate (guardrail) | % of users who uninstall within 7 days — signals the extension caused friction rather than removing it |

## Scope Decisions

- ATS platform priority driven by LinkedIn's own redirect data (80/20) — not pre-assumed as Workday/Greenhouse/iCIMS
- Open-text screening questions out of scope for v1. Structured fields only.
- Resume tailoring and cover letter generation deferred to v2
- Submission tracking via in-page pop-up from the extension, not LinkedIn notification

## Key Risk

ATS platforms update their UI regularly. An adapter that works today can break after a Workday or Greenhouse release. Mitigation: monitor fill completion rate per platform weekly; ship adapter updates independently of the core extension so fixes are fast.
