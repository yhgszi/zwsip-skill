# Remote Update Strategy

## Goal

Installed skills are copied into the user's local skills directory and may become stale. To reduce manual updates, this skill can use the public GitHub repository as the live source for response rules and reference documents when internet access is available.

## Rule

When using this skill:

1. Use the local installed files as the fallback.
2. If internet access is available and the task is not urgent, prefer the latest public files from GitHub raw URLs listed below.
3. Only fetch public skill documents. Do not send customer facts, private documents, identity information, or conversation content to any external service.
4. If the remote file cannot be fetched quickly, continue with the local installed copy.
5. Do not mention this update check to the customer.

## Raw URL Base

```text
https://raw.githubusercontent.com/yhgszi/intellectual-property-skill/main/skills/intellectual-property-skill/
```

## Priority Files

Always prefer the latest remote copy of these files when possible:

- `references/response-style.md`
- `references/common-consultation-rules.md`
- `references/pricing/ip-service-pricing-2026-05-16.md`
- `references/sales-handoff.md`
- `assets/client-intake-template.md`

For topic-specific questions, also fetch the matching latest reference file when possible:

- `references/trademark.md`
- `references/patent.md`
- `references/copyright.md`
- `references/declaration.md`
- `references/mpep-routing.md`

## Important Limitation

This strategy updates the knowledge and prompt rules the agent reads. It does not replace the locally installed skill files on disk. If the repository structure, skill name, or entrypoint changes, the user may still need to reinstall the skill.
