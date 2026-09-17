# Findings

## Development

31 of 31 expected semantic submission decisions matched.

24 of 24 expected individual compliance issues were found.

27 of 31 raw responses were valid JSON.

No high risk false approvals were observed in this controlled synthetic set.

## Unseen holdout

10 of 10 expected semantic submission decisions matched.

9 of 9 expected individual issues matched.

9 of 9 expected evidence selections matched.

9 of 10 raw responses were valid JSON.

No high risk false approvals were observed in this small synthetic holdout.

## Reliability finding

The semantic reviewer performed consistently on these controlled examples, but raw JSON serialization remained imperfect. The repeated failure mode involved quotation marks inside exact source evidence. This supports moving JSON parsing, schema enforcement, exact evidence verification, rule mapping, and malformed output rejection into deterministic infrastructure rather than continuing semantic prompt tuning.
