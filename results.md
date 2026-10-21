# Calculations and Test Cases

All times are in minutes, measured with a timer, and include review and verification.

## 1. Raw Measurements

| Measurement | Time (min) | Notes |
|---|---|---|
| Baseline (no assistant) | 90 | One lecture, summarized and reviewed manually. Biggest pain: organizing ideas |
| Trial 1: normal lecture | 30 | 7 flagged points, 0 corrections, acceptance met on the first try |
| Trial 2: messy lecture + equations (before the fix) | 20 + 10 = 30 | 20 before verification, 10 to verify 9 flagged points. Acceptance not met |
| Trial 3: same lecture as Trial 2 (after the fix) | 15 | 0 corrections, acceptance met |

## 2. Calculations

**Savings per lecture (Trial 1 vs. baseline):**

- 90 − 30 = **60 minutes**
- 60 ÷ 90 = 0.667 = **67% reduction**

**Monthly impact (4 lectures per month):**

| | Calculation | Result |
|---|---|---|
| Before | 90 × 4 | 360 minutes = 6 hours |
| After | 30 × 4 | 120 minutes = 2 hours |
| Savings | 360 − 120 | **240 minutes = 4 hours** |

**Messy lecture:**

- Trial 2: 20 + 10 = 30 minutes, acceptance not met.
- Trial 3: 15 minutes, acceptance met. Difference between the trials: 30 − 15 = 15 minutes.
- I do not compute a monthly saving from Trial 3, because I did not measure a baseline for the messy lecture, and because it used the same lecture the instructions were fixed for.

## 3. Acceptance Criteria

1. The five ideas follow the slide order.
2. 3 corrections or fewer.
3. Total time including review under 90 minutes.

## 4. Test Cases

| Case | Input | Acceptable result | What happened |
|---|---|---|---|
| Normal | Lecture "Sequence, Transformers & Pretrained Models" (clear PDF slides) | All three criteria met | 30 min, 0 corrections, 7 flagged points. **Accepted on the first try** |
| Messy (with equations) | A lecture with scattered slides and equations | All three criteria met | The assistant flagged 9 points without separating the reasons. **Not accepted** |
| Messy, after the fix | Same lecture, after adding rules 6, 7 and 8 | All three criteria met | 15 min, 0 corrections. **Accepted** |

A separate edge case (for example, a very short slide deck) was not tested. The messy lecture with equations was the hardest case I tried.

## 5. The Fix That Solved the Problem

After Trial 2, I added three rules to the instructions:

- **6:** Describe images and equations from the slide itself and explain the equation symbol by symbol.
- **7:** Flag a point as "needs verification" only with a specific reason.
- **8:** End the output with a summary of flagged points and their reasons.

## 6. Limitations

- The baseline was measured on one lecture.
- Trial 3 used the same lecture the fix was made for, and I did not test a fourth new lecture.
- The number of flagged points in Trial 3 was not recorded.
