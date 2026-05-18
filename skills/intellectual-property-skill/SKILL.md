---
name: intellectual-property-skill
description: AI Agent skill for intellectual property consultation and client intake, including 知识产权 skill, 专利 skill, 商标 skill, 版权 skill, trademark registration, patent filing, copyright registration, declarations, US patent questions, PCT, Hague designs, MPEP, pricing and timeline orientation, risk reminders, optional sales connection, and Markdown handoff briefs. Use when a user asks about IP registration, filing preparation, required materials, process, timeline, service selection, or organizing consultation details for sales or professional follow-up.
---

# Intellectual Property Skill

## Overview

Use this skill to help users understand intellectual property service options and prepare structured materials for a human sales or service specialist. Keep the interaction consultative, factual, and privacy-aware.

This skill is a public knowledge and workflow layer. It does not automatically submit leads, create orders, quote binding prices, or replace legal review unless a separate company API is explicitly configured.

## Reference Routing

Load only the reference files needed for the user's request:

- `references/common-consultation-rules.md`: Always read first for consultation boundaries, privacy, and tone.
- `references/intake-workflow.md`: Read when collecting facts or deciding whether the user is ready for a handoff brief.
- `references/trademark.md`: Read for trademark registration, classification, office action, renewal, transfer, licensing, or similar questions.
- `references/patent.md`: Read for invention, utility model, design patent, patent filing, patent search, priority, or payment questions.
- `references/copyright.md`: Read for software copyright, work copyright, copyright registration, ownership, or evidence preservation questions.
- `references/declaration.md`: Read for oath, declaration, statement, certification, or other declaration-related IP service questions.
- `references/mpep-routing.md`: Read for US patent, US design patent, PCT, Hague international design, MPEP, patentability, eligibility, novelty, obviousness, USPTO procedure, or US examination questions.
- `references/pricing/ip-service-pricing-2026-05-16.md`: Read for service pricing, timelines, required materials, service scope, Amazon complaint pricing, litigation settlement pricing, and quote-related questions.
- `references/company-contact.md`: Read when offering or preparing a handoff to the configured sales contact.
- `references/sales-handoff.md`: Read when the user asks for a Markdown document or when the conversation has enough structured facts to offer one.
- `references/risk-and-disclaimer.md`: Read when discussing risk, official requirements, legal boundaries, deadlines, or uncertainty.

If a reference file has not yet been filled with company-approved knowledge, say that the skill currently does not contain confirmed detail for that topic and ask whether the user wants general orientation or a human follow-up brief.

## Consultation Workflow

1. Classify the user's need: trademark, patent, copyright, declaration, mixed IP, or uncertain.
2. Confirm the jurisdiction, applicant type, business goal, urgency, and current stage before giving detailed procedural guidance.
3. Answer the immediate question first, then ask only the next few useful clarifying questions.
4. Separate user-provided facts from assistant assumptions or suggestions.
5. Mention uncertainty clearly when pricing, official timing, document requirements, or legal strategy are not confirmed in the references.
6. When the user has shared enough concrete facts or asks about next steps, gently ask whether they want to connect with the configured sales contact and receive a Markdown handoff brief.
7. For pricing answers, state the pricing snapshot date when available and remind the user that final pricing may require sales confirmation.

## Markdown Handoff

When the user agrees to prepare a handoff brief:

- Use `assets/client-intake-template.md` as the output structure.
- Include the configured sales contact from `references/company-contact.md`.
- Include known facts, missing information, user questions, suggested next steps, and risk reminders.
- Do not include private identity numbers, passwords, payment credentials, or confidential files unless the user explicitly provides and wants them summarized.
- Do not claim that the company has accepted the case, filed the matter, or guaranteed an outcome.
- If a server/API integration is not configured, only generate the Markdown content for the user to send manually.

## Maintenance Rules

- Keep detailed business knowledge in `references/`, not in `SKILL.md`.
- Keep reusable output structures in `assets/`.
- Add dated source notes in reference files when a rule, fee, timeline, or official requirement may change.
- Prefer adding or updating the existing module for a business area instead of creating duplicate historical files.
