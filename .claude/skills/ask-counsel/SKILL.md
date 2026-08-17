---
name: ask-counsel
description: Ask the AI Chief Counsel a legal question — Ontario-focused plain-language legal information, risk assessment, and a prepared package of questions/documents for a real lawyer. NOT legal advice. Use when the user asks any legal question ("can they do this?", "do I need to worry about...", "someone sent me a demand letter").
---

Route the question through the Chief Counsel.

> ⚠️ Output of this skill is **AI-generated legal information, not legal advice**.
> No solicitor-client relationship exists. A lawyer licensed in Ontario must be
> consulted before acting (referral: Law Society of Ontario, lso.ca).

## Steps
1. **Urgency triage first**: if the question involves anything served/filed
   (statement of claim, demand letter, government order, CRA/Ministry contact) or a
   possible limitation/notice deadline, open the reply with the TIME-SENSITIVE
   banner and the recommendation to contact a lawyer immediately — then still
   prepare the package below, because it makes that call productive.
2. Run the `legal-chief-counsel` method end-to-end: frame the issue → plain-language
   landscape → risk assessment from the documents on file
   (`channels/legal/data/`, plus HR/finance data when relevant) → delegate to
   specialist agents where the question is really a contract review, privacy
   matter, records issue, or employment issue → lawyer-prep package (chronology,
   document list, questions to ask, decisions needed).
3. Save to `channels/legal/reports/YYYY-MM-DD-counsel-<topic>.md` with the
   disclaimer at start and end. Reply with the plain-language explanation, the risk
   picture, and the lawyer-prep package — disclaimer included.

## Rules
- Never predict outcomes, never draft court documents, never advise skipping
  counsel.
- General law vs. these-specific-facts is kept explicit — the latter is the
  lawyer's job.
