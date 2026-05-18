---
name: intellectual-property-skill
description: AI Agent skill for intellectual property consultation in Chinese and English. Use for trademark registration, patent filing, copyright registration, IP service selection, US trademark declarations, PCT international applications, Hague designs, MPEP or USPTO questions, client intake, pricing and timeline orientation, required-materials guidance, and Markdown handoff briefs for sales or professional follow-up.
---

# Intellectual Property Skill

## Purpose

Use this skill when a user asks about intellectual property services, including trademarks, patents, copyrights, declarations, US patent procedure, PCT, Hague designs, MPEP, filing materials, service selection, rough process orientation, or preparing a Markdown brief for human follow-up.

This root `SKILL.md` is the public discovery entrypoint for the repository. Detailed workflows, references, and templates live in `skills/intellectual-property-skill/` so the skill stays modular and maintainable and matches common GitHub skill repository layouts.

## Resource Layout

Load only the files needed for the user's question:

- `skills/intellectual-property-skill/references/common-consultation-rules.md`: Always read first for consultation boundaries, privacy, and tone.
- `skills/intellectual-property-skill/references/intake-workflow.md`: Read when collecting facts or deciding whether the user is ready for a handoff brief.
- `skills/intellectual-property-skill/references/trademark.md`: Read for trademark registration, classification, office actions, renewal, transfer, licensing, or similar topics.
- `skills/intellectual-property-skill/references/patent.md`: Read for invention, utility model, design patent, patent filing, patent search, priority, or payment questions.
- `skills/intellectual-property-skill/references/copyright.md`: Read for software copyright, work copyright, copyright registration, ownership, or evidence preservation.
- `skills/intellectual-property-skill/references/declaration.md`: Read for oath, declaration, statement, certification, or declaration-related IP services.
- `skills/intellectual-property-skill/references/mpep-routing.md`: Read for US patent, US design patent, PCT, Hague international design, MPEP, patentability, eligibility, novelty, obviousness, USPTO procedure, or US examination questions.
- `skills/intellectual-property-skill/references/pricing/ip-service-pricing-2026-05-16.md`: Read for service pricing, timelines, required materials, service scope, Amazon complaint pricing, litigation settlement pricing, and quote-related questions.
- `skills/intellectual-property-skill/references/company-contact.md`: Read when offering or preparing a handoff to the configured sales contact.
- `skills/intellectual-property-skill/references/sales-handoff.md`: Read when the user asks for a Markdown document or has shared enough structured facts to offer one.
- `skills/intellectual-property-skill/references/risk-and-disclaimer.md`: Read when discussing risk, official requirements, legal boundaries, deadlines, or uncertainty.
- `skills/intellectual-property-skill/assets/client-intake-template.md`: Use as the output structure when preparing a client handoff brief.

## Workflow

1. Classify the user's need: trademark, patent, copyright, declaration, mixed IP, US patent/MPEP, or uncertain.
2. Confirm the jurisdiction, applicant type, business goal, urgency, and current stage before giving detailed procedural guidance.
3. Answer the immediate question first, then ask only the next useful clarifying questions.
4. Separate confirmed user facts from assumptions, suggestions, or general orientation.
5. Mention uncertainty clearly when pricing, official timing, document requirements, or legal strategy are not confirmed in the references.
6. When the user has shared enough concrete facts or asks about next steps, ask whether they want a Markdown handoff brief for sales or professional follow-up.
7. If the user agrees, generate the Markdown brief using the configured contact and template. Do not claim that the matter has been accepted, filed, ordered, submitted, or guaranteed.

## Boundaries

This skill provides general business and process information. It does not replace professional legal review, bind final pricing, submit filings, create orders, or automatically send leads unless a separate API is explicitly configured.
