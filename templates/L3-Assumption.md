# L3 Assumption Template

## Purpose

The Assumption layer records statements that are believed to be true but have not yet been verified.

Assumptions provide the foundation for reasoning, prediction, and decision-making under uncertainty.

Every assumption should be explicit so that it can later be validated, revised, or discarded.

---

# Writing Guidelines

An Assumption document should:

- clearly state each assumption
- distinguish assumptions from observed facts
- explain why the assumption is reasonable
- identify uncertainty where applicable
- define how the assumption could be validated

If a statement has already been verified, it belongs in an **L1 Reality** document.

If the assumption is being tested, create a corresponding **L6 Validation** document.

---

# Template

## Assumptions

List each assumption explicitly.

```
-
```

---

## Rationale

Explain why these assumptions are considered reasonable.

Possible sources include:

- prior experience
- domain knowledge
- literature
- intuition
- design decisions

```
-
```

---

## Supporting Evidence

List any evidence that supports the assumptions.

Supporting evidence increases confidence but does not make an assumption a fact.

```
-
```

---

## Confidence

Estimate the confidence level for each assumption.

| Assumption | Confidence | Reason |
|------------|------------|--------|
| | | |

Suggested confidence levels:

- Low
- Medium
- High

---

## Risks

Describe what could happen if an assumption is incorrect.

Possible impacts include:

- invalid conclusions
- failed implementation
- inaccurate predictions
- wasted resources

```
-
```

---

## Validation Plan

Describe how each assumption can be tested.

Examples:

- experiment
- benchmark
- observation
- user study
- measurement

```
-
```

---

## Dependencies

Identify related assumptions or external conditions.

```
-
```

---

## References

Reference related AIR Documents.

Examples:

```
[[Reality]]

[[Simulation]]

[[Validation]]
```

---

## Notes

Additional remarks or context.

```
-
```

---

# Checklist

Before completing an L3 Assumption document, verify:

- Every assumption is explicit.
- Assumptions are clearly separated from facts.
- Supporting rationale is documented.
- Risks are identified.
- A validation approach exists.
- Confidence is communicated.

---

# Related Layers

Typical relationships include:

```text
Reality

↓

Problem

↓

Assumption

↓

Variables

↓

Simulation

↓

Validation
```

Assumptions connect observed reality to future reasoning and should eventually be confirmed, refined, or rejected through validation.

---

# Summary

An L3 Assumption document captures the beliefs and hypotheses that guide reasoning before evidence is available.

Its purpose is to make uncertainty visible, allowing both humans and AI systems to reason transparently and evaluate assumptions through later validation.