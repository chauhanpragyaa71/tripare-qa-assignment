# Tripare AI - QA Assignment

# Part 1C – Bug Report

The following issues were identified while validating the hotel recommendation results against the specified business rules.

---

# Bug-001

## Title

Hotel outside the allowed distance is recommended.

### Severity

High

### Description

Hotel **Comet Residency** is displayed even though its distance is **5.8 km**.

### Expected Result

Hotels farther than **5 km** should not be recommended.

### Actual Result

Hotel appears in the recommendation list.

### Business Impact

Users may receive recommendations that violate the defined business rules.

---

# Bug-002

## Title

Invalid review score displayed.

### Severity

High

### Description

Hotel **Nexus Park Hotel** has a review score of **10.8**.

### Expected Result

Review score should be within the supported range (for example, 0–10).

### Actual Result

A review score greater than the maximum allowed value is displayed.

### Business Impact

Users may lose trust in the recommendation quality.

---

# Bug-003

## Title

More expensive hotel marked as "Cheaper".

### Severity

Critical

### Description

Hotel **Zenith Inn** has a total price of **₹22,400**, while the selected hotel costs **₹21,000**.

### Expected Result

Only hotels with a lower total price should be recommended and tagged as cheaper.

### Actual Result

The hotel is marked as "Cheaper" despite being more expensive.

### Business Impact

This violates the core recommendation logic.

---

# Bug-004

## Title

Currency inconsistency in recommendation list.

### Severity

Medium

### Description

Hotel **Vertex Corporate Rooms** displays the price in **USD ($18,900)** while the remaining hotels use **INR (₹)**.

### Expected Result

All hotel prices should use a consistent currency or be converted before comparison.

### Actual Result

Mixed currencies are displayed.

### Business Impact

Users cannot accurately compare hotel prices.

---

# Bug-005

## Title

Duplicate hotel recommendation displayed.

### Severity

Medium

### Description

Hotel **Orbit Executive Stay** appears twice in the recommendation list.

### Expected Result

Each hotel should appear only once.

### Actual Result

Duplicate recommendation is displayed.

### Business Impact

Duplicate entries reduce recommendation quality and waste recommendation slots.

---

# Bug-006

## Title

Selected hotel appears in recommendation list.

### Severity

Critical

### Description

The selected hotel **Skyline Business Hotel** is shown as Recommendation #10.

### Expected Result

The selected hotel should never be included in recommendations.

### Actual Result

Selected hotel appears in the recommendation list.

### Business Impact

Recommendation engine fails to exclude the selected hotel.

---

# Bug-007

## Title

Recommendation tag does not match business logic.

### Severity

Medium

### Description

Zenith Inn displays the recommendation tag **"Cheaper"** even though it is more expensive than the selected hotel.

### Expected Result

Recommendation tags should accurately describe why the hotel was recommended.

### Actual Result

Incorrect recommendation tag is displayed.

### Business Impact

Misleading recommendation labels reduce user confidence.

---

# Bug-008

## Title

Recommendation ranking may be incorrect.

### Severity

High

### Description

The displayed ranking cannot be verified against the defined score calculation and ranking rules.

### Expected Result

Hotels should be ranked by:

1. Highest Score Delta
2. Lowest Total Price
3. Lowest Distance
4. Highest Review Count

### Actual Result

Displayed ranking appears inconsistent with the documented business rules.

### Business Impact

Users may not receive the best available recommendations.
