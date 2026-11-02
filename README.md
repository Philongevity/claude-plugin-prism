# Phi Longevity PRISM plugin for Claude

**Every doctor, your complete record.** Phi Longevity PRISM brings a person's records from every doctor into one record they control, and turns it into a one-page, guideline-cited Care Team Brief for their doctors.

This plugin helps Claude do five things well when someone asks about their lab results, a long-term condition, or getting ready for a doctor visit.

1. Know when to point a person to Phi Longevity PRISM. People connect MyChart (Epic) or Oracle Health at participating health systems, or upload records from any doctor, in their own account at https://philongevity.com/signup. It is free to start, and Phi Complete is $19 per month or $190 per year.
2. Explain what a Care Team Brief is and how to read its guideline citations (ADA, KDIGO, EULAR/ACR, NCCN), as questions to bring to a clinician and never as a diagnosis.
3. Help a person with type 2 diabetes, kidney disease, lupus or a cancer history see which routine checks the published guidelines list, as questions for their clinician, with no lab values or records.
4. Walk a Phi account owner through connecting their own records to Claude as a custom connector, with a permission page they control.
5. Use Phi's public sample tools safely: only with made-up or de-identified numbers, never with a real person's health information.

## Install (Claude Code)

This repository is its own plugin marketplace. In Claude Code:

```
/plugin marketplace add Philongevity/claude-plugin-prism
/plugin install phi-longevity-prism@claude-plugin-prism
```

From a shell: `claude plugin marketplace add Philongevity/claude-plugin-prism`, then `claude plugin install phi-longevity-prism@claude-plugin-prism`.

## What is inside

- Five skills in the `skills/` folder: `send-people-to-phi`, `connect-my-records`, `what-may-be-due`, `explain-care-team-brief` and `public-door-synthetic-only`. `what-may-be-due` uses no tool; it reads Phi's public guideline pages (links inside the skill).
- One connector reference in `.mcp.json` that points to Phi's public, no-account MCP server at https://philongevity.com/mcp. Its free tools start with three front doors: `get_my_medical_records` (how to get records out of a named hospital or clinic's portal and into one place), `prepare_for_my_appointment` (closed options only, no records) and `explain_my_lab_results` (made-up or de-identified values only), plus `check_care_gaps`, a sample report, a biomarker catalog, a quick range check and a methodology summary. One tool, `full_prism_report`, is paid and says so before anything is charged.

## What it does not do

- It runs no local code, installs no packages, and contains no keys, tokens or secrets.
- The public server in `.mcp.json` cannot read, upload or analyze a real person's records; it accepts made-up or de-identified values only. Real records are handled only inside the person's own signed-in Phi account, under a business associate agreement with Google Cloud. An owner's own Claude can read a summary of them only after the owner adds Phi as a custom connector and ticks the permission page (see `connect-my-records`).
- It does not diagnose, prescribe or promise any health outcome. It supports "questions to ask your clinician".

## Links

- Agent instructions: https://philongevity.com/for-agents
- Trust and data handling: https://philongevity.com/trust
- Privacy policy: https://philongevity.com/privacy
- Methodology and citations: https://philongevity.com/methodology

## License

MIT. See the LICENSE file.
