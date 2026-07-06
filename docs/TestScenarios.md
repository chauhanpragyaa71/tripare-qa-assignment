# Tripare AI - QA Assignment

# Part 1A – Test Scenarios

## System Under Test
Hotel Recommendation System

## Recommendation Rules

A hotel should be recommended only if:

- Total price is lower than the selected hotel.
- Overall score is higher than the selected hotel.
- Distance is less than or equal to 5 km.
- Inventory is available.
- Hotel is active.

---

## Selected Hotel Details

| Property | Value |
|----------|-------|
| Hotel Name | Skyline Business Hotel |
| Total Price | ₹21,000 |
| Star Rating | 4★ |
| Review Score | 8.3 |
| Distance | 0 km |

---

# Boundary Test Cases

## TS-001: Verify recommendation when all eligibility criteria are satisfied

### Preconditions
- Selected hotel price = ₹21,000
- Candidate hotel price = ₹19,500
- Candidate score is higher
- Distance = 3 km
- Inventory = 5
- Hotel is Active

### Steps
1. Select Skyline Business Hotel.
2. View recommendations.

### Expected Result
Candidate hotel appears in the recommendation list with all hotel details displayed correctly.

Priority: High
---

## TS-002: Verify hotel is recommended when distance is exactly 5 km

### Preconditions
Candidate hotel distance = 5 km.

### Steps
1. Select the hotel.
2. Load recommendations.

### Expected Result
Hotel is recommended.

Priority: High

---

## TS-003: Verify hotel is not recommended when distance is greater than 5 km

### Preconditions
Candidate distance = 5.01 km.

### Steps
1. Select hotel.
2. Load recommendations.

### Expected Result
Candidate hotel is excluded.

Priority: High

---

## TS-004: Verify hotel is recommended when price is ₹1 less than selected hotel

### Preconditions
Candidate price = ₹20,999.

### Steps
Load recommendations.

### Expected Result
Candidate hotel is recommended.

Priority: High

---

## TS-005: Verify hotel is NOT recommended when price equals selected hotel

### Preconditions
Candidate price = ₹21,000.

### Steps
Load recommendations.

### Expected Result
Candidate hotel is excluded.

Priority: High

---

## TS-006: Verify hotel with inventory = 1 is recommended

### Preconditions
Inventory = 1.

### Steps
Load recommendations.

### Expected Result
Hotel is recommended.

Priority: High

---

# Negative Test Cases

## TS-007: Verify inactive hotel is excluded

### Preconditions
Hotel status = Inactive.

### Steps
Load recommendations.

### Expected Result
Hotel is not displayed.

Priority: High

---

## TS-008: Verify sold-out hotel is excluded

### Preconditions
Inventory = 0.

### Steps
Load recommendations.

### Expected Result
Hotel is excluded.

Priority: High

---

## TS-009: Verify hotel with lower score is not recommended

### Preconditions
Candidate score is less than selected hotel.

### Steps
Load recommendations.

### Expected Result
Hotel is excluded.

Priority: High

---

## TS-010: Verify selected hotel itself is not recommended

### Preconditions
Recommendation list contains selected hotel.

### Steps
Load recommendations.

### Expected Result
Selected hotel should never appear.

Priority: High

---

## TS-011: Verify duplicate hotels are not displayed

### Preconditions
Same hotel exists twice.

### Steps
Load recommendations.

### Expected Result
Only one instance is displayed.

Priority: High

---

## TS-012: Verify system handles missing review score

### Preconditions
Review score is NULL.

### Steps
Load recommendations.

### Expected Result
System handles missing review safely without crashing and follows business rules.

Priority: High

---

# Ranking & Sorting Test Cases

## TS-013: Verify recommendations are sorted by highest Score Delta

### Preconditions
Multiple eligible hotels with different Score Delta.

### Steps
Load recommendations.

### Expected Result
Hotels are sorted by highest Score Delta.

Priority: High

---

## TS-014: Verify hotels with equal Score Delta are sorted by lowest price

### Preconditions
Same Score Delta.

### Steps
Load recommendations.

### Expected Result
Cheaper hotel appears first.

Priority: High

---

## TS-015: Verify hotels with same Score Delta and price are sorted by shortest distance

### Preconditions
Same score and price.

### Steps
Load recommendations.

### Expected Result
Nearest hotel appears first.

Priority: High

---

## TS-016: Verify hotels with same score, price and distance are sorted by highest review count

### Preconditions
Review counts differ.

### Steps
Load recommendations.

### Expected Result
Hotel with highest review count appears first.

Priority: High

---

# Data Validation Test Cases

## TS-017: Verify total price calculation is correct

### Preconditions
Nightly rate × number of nights.

### Steps
Compare displayed total price with calculated total.

### Expected Result
Displayed total price matches calculation.

Priority: Medium
---

## TS-018: Verify currency consistency

### Preconditions
One recommendation contains USD while others contain INR.

### Steps
Load recommendations.

### Expected Result
System displays prices in one supported currency or converts correctly.

Priority: Medium

---

## TS-019: Verify displayed amenities match hotel data

### Preconditions
Hotel contains Wi-Fi, Breakfast and Parking.

### Steps
Open hotel details.

### Expected Result
Displayed amenities match backend data.

Priority: Medium

---

## TS-020: Verify only Top 10 recommendations are displayed

### Preconditions
More than 10 eligible hotels exist.

### Steps
Load recommendations.

### Expected Result
Exactly 10 hotels are displayed according to ranking rules.

Priority: Medium

---