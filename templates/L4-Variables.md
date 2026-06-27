# L4 Variables Template

## Purpose

The Variables layer identifies the factors that influence the outcome of a problem or system.

Variables provide the inputs for reasoning, simulation, and validation by making explicit what can change, what can be observed, and what remains hidden.

---

# Writing Guidelines

A Variables document should:

- identify relevant variables
- classify variables by their role
- describe relationships between variables
- distinguish controllable factors from observations
- identify unknown or latent variables

Variables should remain descriptive.

Do not predict outcomes in this layer. Predictions belong in an **L5 Simulation** document.

---

# Template

## Variables

List all relevant variables.

| Variable | Description |
|----------|-------------|
| | |

---

## Variable Classification

### Controllable Variables

Variables that can be intentionally modified.

```
-
```

### Observable Variables

Variables that can be directly measured or monitored.

```
-
```

### Latent Variables

Variables that cannot be directly observed but may influence outcomes.

```
-
```

### External Variables

Variables outside the system's control.

```
-
```

---

## Relationships

Describe how variables influence one another.

Examples:

- causal relationships
- dependencies
- correlations
- constraints

```
-
```

---

## Assumptions

List assumptions related to the identified variables.

Reference corresponding L3 Assumption documents whenever possible.

```
-
```

---

## Measurement

Describe how each observable variable can be measured.

| Variable | Measurement Method | Unit |
|----------|--------------------|------|
| | | |

---

## Constraints

Describe limitations affecting the variables.

Examples:

- unavailable measurements
- limited control
- environmental restrictions
- sampling limitations

```
-
```

---

## Unknown Variables

Identify variables that may exist but are not yet understood.

```
-
```

---

## References

Reference related AIR Documents.

Examples:

```
[[Reality]]

[[Assumption]]

[[Simulation]]
```

---

## Notes

Additional observations or clarifications.

```
-
```

---

# Checklist

Before completing an L4 Variables document, verify:

- Relevant variables are identified.
- Variables are properly classified.
- Relationships are documented.
- Measurement methods are defined where possible.
- Unknown variables are acknowledged.
- Predictions are not included.

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
```

Variables provide the bridge between assumptions and predictive reasoning by defining the factors that influence outcomes.

---

# Summary

An L4 Variables document describes the factors that shape system behavior.

Its purpose is to provide a structured representation of the inputs to reasoning, enabling transparent simulations and meaningful validation in later stages.