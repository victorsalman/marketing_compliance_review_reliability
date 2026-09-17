# Marketing Compliance Review Reliability

Independent AI systems case study exploring a marketing compliance review workflow that separates deterministic lexical controls, semantic interpretation, exact source evidence, uncertainty preservation, and deterministic business outcome mapping.

## What this project tests

The workflow reviews synthetic SaaS marketing copy against frozen business rules covering prohibited phrases, measurable outcome claims, absolute superiority claims, negative named competitor claims, unclear customer statement attribution, ordinary product descriptions, and untrusted instructions inside source content.

The project focuses on prompt engineering and AI reliability evaluation rather than production software deployment.

## Architecture

The smallest candidate architecture uses one semantic model call surrounded by deterministic processing. Deterministic preprocessing supplies exact RULE_1 lexical candidates. The language model performs semantic interpretation and evidence selection. Deterministic software is responsible for JSON parsing, schema enforcement, allowed values, exact evidence verification, duplicate handling, rule mapping, and final APPROVED, REVIEW, or REJECTED calculation. Human review handles unresolved semantic ambiguity and policy judgment.

## Controlled results

Development Benchmark V1 contained 31 synthetic submissions. The controlled same conversation development run matched 31 of 31 expected semantic submission decisions and 24 of 24 expected individual issues. Raw JSON was valid for 27 of 31 responses.

A separate unseen synthetic holdout contained 10 new submissions whose expected answers were not supplied to the Veteran AI before execution. The holdout matched 10 of 10 expected semantic submission decisions, 9 of 9 expected individual issues, and 9 of 9 expected evidence selections. Raw JSON was valid for 9 of 10 responses.

No high risk false approvals were observed in either controlled set. This is a limited benchmark finding, not a production accuracy claim.

## Main reliability finding

Strong semantic performance did not guarantee machine readable output. Five of 41 raw responses across development and holdout were syntactically invalid JSON, primarily because quotation marks inside exact evidence spans were not escaped correctly. The architecture therefore treats serialization and schema validity as deterministic responsibilities rather than problems to solve by continually expanding prompt wording.

## Repository contents

`prompts` contains the frozen semantic reviewer prompt.

`data` contains development and holdout execution prompts, raw outputs, and an experiment summary.

`docs` contains the problem definition, architecture, experiment design, findings, responsibility split, limitations, and the portfolio case study PDF.

## Limitations

All marketing examples were synthetic. Testing was conversational rather than independent API execution. No production traffic, cost, latency, privacy, monitoring, throughput, or deployment evidence was collected. This project does not establish production readiness, security guarantees, or externally validated compliance accuracy.
