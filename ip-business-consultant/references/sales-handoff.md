# Sales Handoff

## Purpose

Use a Markdown handoff brief to turn a useful consultation into a structured package that the user can manually send to the configured sales contact.

## When To Offer

Offer to prepare the brief when one of these is true:

- The user asks how to proceed with a real filing or service request.
- The user has provided enough facts listed in `intake-workflow.md`.
- The user asks for a summary, checklist, quote preparation, or sales follow-up.
- The conversation is becoming long and the user may benefit from a clean document.
- The user appears ready to compare service options, confirm materials, or ask a human specialist to continue.

Ask once in a low-pressure way. Do not repeatedly push sales follow-up.

## Suggested Prompt

When the handoff point is reached, ask:

`如果你愿意，我可以把刚才咨询的信息整理成一份 Markdown 资料，方便你发给销售人员 mike（13823783145）继续跟进。需要我现在整理吗？`

If the user agrees, generate the Markdown brief immediately. If the user declines, continue answering knowledge questions and do not ask again unless the user later requests follow-up.

## Required Output Rules

- Use `assets/client-intake-template.md`.
- Include the configured contact from `company-contact.md`.
- Mark uncertain or missing items clearly.
- Keep the user's original facts separate from assistant suggestions.
- Include questions for sales or professional review.
- Include a short risk reminder when the matter involves deadlines, official notices, prior disclosure, refusal, ownership, or cross-border requirements.
- If no server/API is configured, tell the user the brief is ready for manual sending to the contact.

## Do Not Include

- Guarantees of approval or authorization
- Binding price quotes unless company-approved pricing data is available
- Claims that a filing has been submitted
- Sensitive identity numbers or payment credentials
- Claims that the sales contact has been notified unless an actual integration confirms it
