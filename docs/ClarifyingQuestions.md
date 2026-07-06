# Tripare AI - QA Assignment

# Part 1B – Clarifying Questions

Before creating detailed test cases or automation, I would clarify the following questions with the Product Manager and Engineering team to remove ambiguity and ensure the expected behavior is well understood.

## CQ-001: Price Comparison

Should the comparison use the **total booking price**, or should taxes, service charges, discounts, and coupons also be included?

---

## CQ-002: Score Calculation

How should the system calculate the score if one or more values (review score, star rating, or amenity match percentage) are missing or unavailable?

---

## CQ-003: Distance Calculation

Is a hotel located at **exactly 5 km** considered eligible for recommendation?

---

## CQ-004: Currency Handling

If hotels are returned in different currencies (for example, INR and USD), should the system convert them into a common currency before comparing prices?

---

## CQ-005: Fewer Than 10 Eligible Hotels

If only 4 or 5 hotels satisfy all recommendation rules, should the application display only those hotels or should it relax some recommendation criteria to display additional results?

---

## CQ-006: Tie-Breaking Rules

If two hotels have identical Score Delta, total price, distance, and review count, what should be the final tie-breaking rule?

---

## CQ-007: Inventory Freshness

How frequently is hotel inventory updated? What is the acceptable delay before inventory information is considered stale?

---

## CQ-008: Recommendation Tags

How should the "Why Recommended" tags be generated? Are they based on predefined business rules or dynamically calculated from hotel attributes?
