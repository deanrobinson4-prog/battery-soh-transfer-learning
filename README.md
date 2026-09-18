# Transfer Learning for Lithium-Ion Battery State-of-Health Estimation

**Good Teacher, Bad Student: The Hidden Asymmetry of Transfer Learning Across Batteries**

Final-year engineering thesis — UNSW Canberra
Author: Dean Robinson · Supervisors: Huadong Mo, Runpu Wang

---

## Overview

This project asks a simple question with a surprising answer: **can a machine-learning
model trained to predict one battery's State-of-Health (SOH) be reused on a completely
different battery — and does it actually help, or only look like it does?**

Using the BatteryLife benchmark, an LSTM model was tested across **12 battery datasets**
spanning multiple chemistries (including non-lithium sodium- and zinc-ion cells), as both
the *source* (teacher) and the *target* (student) — giving **130 directed transfer pairs**,
each repeated over 5 random seeds.

## Key findings

- **Measure it fairly.** Against an equivalent same-feature control, transfer helps on the
  majority of pairs (73 of 130, ~56%). Against an unfair full-feature baseline it appears to
  fail — the choice of comparison inverts the conclusion.
- **Good teachers ≠ good students.** A dataset's value as a source is independent of its value
  as a target (e.g. XJTU: strong teacher, worst student; UL_PUR: best student, weak teacher).
- **Shared features drive success.** Transfer reuses only what two datasets share — governed by
  data format more than battery chemistry.
- **Fine-tuning is essential;** zero-shot reuse fails.
- **Data-scarce batteries gain most** — the real deployment case (e.g. second-life EV batteries).

## Application

Retired EV batteries leave vehicles at ~80% SOH but remain suitable for grid and home
battery storage. These second-life systems mix chemistries, ages and formats with little
data to build a health model for each — exactly the cross-dataset problem this work
addresses, enabling one battery's health model to be safely reused on another.

---

*School of Engineering and Technology, UNSW Canberra.*
