---
name: intellectual-property-skill
description: AI Agent skill for intellectual property consultation in Chinese and English. Use for 知识产权 skill, 专利 skill, 商标 skill, 版权 skill, trademark registration, patent filing, copyright registration, IP service selection, US trademark declarations, PCT international applications, Hague designs, MPEP or USPTO questions, client intake, pricing and timeline orientation, required-materials guidance, and Markdown handoff briefs for sales or professional follow-up.
---

# Intellectual Property Skill

## Purpose

Use this skill when a user asks about intellectual property services, including trademarks, patents, copyrights, declarations, US patent procedure, PCT, Hague designs, MPEP, filing materials, service selection, rough process orientation, or preparing a Markdown brief for human follow-up.

This root `SKILL.md` is the public discovery entrypoint for the repository. Detailed workflows, references, and templates live in `skills/intellectual-property-skill/` so the skill stays modular and maintainable and matches common GitHub skill repository layouts.

## Resource Layout

Load only the files needed for the user's question:

- `skills/intellectual-property-skill/references/response-style.md`: Always read first for customer-facing tone, brevity, banned internal wording, and answer templates.
- `skills/intellectual-property-skill/references/common-consultation-rules.md`: Read for consultation boundaries and privacy rules.
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
3. Reply like a concise sales or service specialist, not like a research assistant. Give the customer-facing answer first.
4. Answer the immediate question first, then ask only one useful next question when needed.
5. Separate confirmed user facts from assumptions only when the distinction affects the next step.
6. Mention uncertainty clearly when pricing, official timing, document requirements, or legal strategy are not confirmed in the references.
7. When the user has shared enough concrete facts or asks about next steps, ask whether they want a Markdown handoff brief for sales or professional follow-up.
8. If the user agrees, generate the Markdown brief using the configured contact and template. Do not claim that the matter has been accepted, filed, ordered, submitted, or guaranteed.

## Customer Reply Style

Always apply `skills/intellectual-property-skill/references/response-style.md` before writing a customer-facing answer. The short version: answer the question first, keep routine replies compact, do not expose internal sources or retrieval process, and ask only one practical next question.

## Boundaries

This skill provides general business and process information. It does not replace professional legal review, bind final pricing, submit filings, create orders, or automatically send leads unless a separate API is explicitly configured.
