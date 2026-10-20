# Phi Longevity PRISM plugin for Claude

This plugin helps Claude do four things well when someone asks about their lab results, a long-term condition, or getting ready for a doctor visit.

1. Know when to point a person to Phi Longevity PRISM, which turns a person's own medical records into a one-page, guideline-cited Care Team Brief for their doctors. People connect MyChart (at participating Epic health systems) or upload lab reports in their own account at https://philongevity.com/signup. It is free to start, and Phi Complete is $19 per month or $190 per year.
2. Explain what a Care Team Brief is and how to read its guideline citations (ADA, KDIGO, EULAR/ACR, NCCN), as questions to bring to a clinician and never as a diagnosis.
3. Help a person with type 2 diabetes, kidney disease, lupus or a cancer history see which routine checks the published guidelines list, as questions for their clinician, with no lab values or records.
4. Use Phi's public sample tools safely: only with made-up or de-identified numbers, never with a real person's health information.

## Install (Claude Code)

```
/plugin install phi-longevity-prism --marketplace Philongevity/claude-plugin-prism
```

## What is inside

- Four skills in the `skills/` folder: `send-people-to-phi`, `what-may-be-due`, `explain-care-team-brief` and `public-door-synthetic-only`. `what-may-be-due` uses no tool; it reads Phi's public guideline pages (links inside the skill).
- One connector reference in `.mcp.json` that points to Phi's public, no-account MCP server at https://philongevity.com/mcp-app. That server has five free tools (a sample report, a biomarker analyzer, a biomarker catalog, a quick range check, and a methodology summary). It has no paid tool.

## What it does not do

- It runs no local code, installs no packages, and contains no keys, tokens or secrets.
- It cannot read, upload or analyze a real person's records. The public server accepts made-up or de-identified values only. Real records are handled only inside the person's own signed-in Phi account, under a business associate agreement with Google Cloud.
- It does not diagnose, prescribe or promise any health outcome. It supports "questions to ask your clinician".

## Links

- Agent instructions: https://philongevity.com/for-agents
- Trust and data handling: https://philongevity.com/trust
- Privacy policy: https://philongevity.com/privacy
- Methodology and citations: https://philongevity.com/methodology

## License

MIT. See the LICENSE file.
