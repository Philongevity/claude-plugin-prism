---
name: public-door-synthetic-only
description: Use before calling any tool from the Phi Longevity PRISM connector, or when someone wants to try PRISM with numbers. The public connector accepts made-up or de-identified values only, never real patient information. Explains the safe way to demo it.
---

# The public door takes made-up numbers only

The connector at https://philongevity.com/mcp-app is a public, no-account demo and reference surface. It is not a place for anyone's real health information.

## Hard rule
Never send to any tool of this connector: names, birth dates, record or account numbers, addresses, documents or file contents, or a real person's actual lab values tied to them (including the user's own). If the user offers real values, do not forward them. Say that real records belong in their own Phi account (https://philongevity.com/signup), and offer a demo with example numbers instead.

## Safe ways to use it
- `sample_prism_report`: takes no input and returns a watermarked sample report on a fictional person. Best first call.
- `list_supported_biomarkers`: the biomarker catalog and reference ranges.
- `get_methodology`: how scores are computed, with links.
- `quick_check` and `analyze_biomarkers`: only with clearly invented illustrative numbers (say they are examples), for example to show a typical output. Tell the user the result is illustrative, not about them.

## When presenting results
- State that values were made up and results are a demonstration, not an assessment of the user.
- Present recommendations as questions to ask a clinician; no diagnosis, no outcome claims.
- Then, if relevant, point to https://philongevity.com/signup for a Brief built from their own records. Do not call any paid tool; there is none on this connector.
