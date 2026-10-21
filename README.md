# Capstone: A Custom Study Assistant for Natural Language Processing Lectures

**AI Productivity Course · SDAIA Academy**
**Name:** Sarah Mohammed Alhammad
**Track:** Custom assistant (Project) · **Approved app:** Claude

## Summary

A weekly task: summarizing and reviewing one lecture from a Natural Language Processing (NLP) course (PDF slides). I built a custom assistant with fixed instructions inside a Claude Project, then measured the time before and after.

Full slides (in Arabic): [`slides_nlp_sara.pdf`](slides_nlp_sara.pdf)
Calculations and test cases: [`results.md`](results.md)

## Task and Baseline

| Item | Value |
|---|---|
| Task | Summarize and review one lecture from PDF slides |
| Time today | 90 minutes per lecture (timed, no AI) |
| Frequency | 4 times per month (about 6 hours) |
| Biggest pain point | Organizing the ideas |

## What I Built

A custom assistant (a Claude Project) holding the instructions below. I upload the lecture slides and write: "Summarize this lecture."

**Fixed output:** top 5 ideas in slide order · glossary table with slide numbers · 5 review questions with short answers and slide numbers · a "needs verification" list with a reason for each item.

**Acceptance criteria:** the five ideas follow the slide order, 3 corrections or fewer, and total time including review under 90 minutes.

## Instructions (reusable)

The assistant works in Arabic, so the instructions are in Arabic as used:

```
أنت مساعد مذاكرة لمقرر "معالجة اللغات الطبيعية" (NLP).
مهمتك: تحويل شرائح المحاضرة المرفقة إلى ملخص مراجعة مرتب.

القواعد:
1. اعتمد فقط على الشرائح المرفقة. لا تضف معلومة من خارجها.
2. إذا كانت نقطة غير واضحة أو ناقصة في الشرائح، اكتب بجانبها [تحتاج تحقق] ولا تخمّن.
3. لا تحل واجبات أو اختبارات بدل الطالب. دورك الشرح والتلخيص فقط.
4. حافظ على تسلسل المحاضرة، لا تعيد ترتيب الأفكار عشوائياً.
5. اكتب بالعربية وأبقِ المصطلحات التقنية بالإنجليزية بين قوسين.
6. إذا كانت الشريحة صورة أو معادلة أو رسم: اكتب ما يظهر فيها بدقة، واشرح المعادلة
   رمزاً رمزاً من الشريحة نفسها، وإذا لم تستطع قراءتها اكتب [الشريحة رقم X صورة،
   لم أستطع قراءتها] بدل أن تعلّم النقطة فقط.
7. لا تعلّم نقطة "تحتاج تحقق" إلا وبجانبها سبب محدد (ناقصة، متناقضة، صورة غير مقروءة).
8. في آخر المخرج، اكتب ملخصاً بعدد النقاط المعلّمة وأسبابها.

شكل المخرج (ثابت كل مرة):
- عنوان المحاضرة
- أهم 5 أفكار مرتبة حسب تسلسل الشرائح
- جدول المصطلحات: المصطلح | تعريفه | رقم الشريحة
- 5 أسئلة مراجعة، وجوابها المختصر بجانب كل سؤال مع رقم الشريحة
- قائمة "تحتاج تحقق" للنقاط الغامضة

إذا كان الملف فارغاً أو غير مفهوم أو ليس محاضرة، قل ذلك ولا تلخّص.
```

**English translation of the rules:**

1. Rely only on the attached slides. Add nothing from outside them.
2. If a point is unclear or incomplete in the slides, mark it [needs verification] and do not guess.
3. Do not solve assignments or exams for the student. Only explain and summarize.
4. Keep the lecture's order. Do not reorder ideas.
5. Write in Arabic and keep technical terms in English in parentheses.
6. If a slide is an image, equation, or diagram: describe exactly what appears, explain the equation symbol by symbol from the slide itself, and if it cannot be read, write [slide X is an image, could not read it] instead of just flagging the point.
7. Flag a point as "needs verification" only with a specific reason (incomplete, contradictory, unreadable image).
8. At the end, add a summary of the number of flagged points and their reasons.

If the file is empty, unclear, or not a lecture, say so and do not summarize.

## Delegation Card

| | |
|---|---|
| Delegated to the assistant | Extracting and ordering ideas, writing definitions and questions, flagging unclear points instead of guessing |
| Stays with me | Checking the summary against the slides, verifying flagged points, and the final decision to accept |
| Data | Course slides only, no names or personal data |

## Measured Results

Time includes review and verification, and was measured with a timer.

| Metric | Before (no assistant) | Trial 1: normal lecture | Trial 2: messy + equations | Trial 3: same lecture as Trial 2, after the fix |
|---|---|---|---|---|
| Time with review (minutes) | 90 | 30 | 30 (20 + 10 verification) | 15 |
| Flagged points [needs verification] | - | 7 | 9 | not recorded |
| Corrections I made to the output | - | 0 | acceptance not met | 0 |
| Acceptance criteria met? | - | Yes, first try | No | Yes, after the fix |

**Monthly impact:** 90 to 30 minutes in Trial 1 = 60 minutes saved × 4 lectures = **4 hours per month** (a 67% reduction).

## What Failed and How I Fixed It

In Trial 2 (a messy lecture with equations), the assistant flagged 9 points without distinguishing between reasons, and the acceptance criteria were not met. I added one fix (rules 6, 7 and 8) and re-ran the same lecture: 0 corrections and 15 minutes, and acceptance was met.

## Limitations (honestly)

- The baseline was measured on one lecture (the same one as Trial 1). I did not measure a baseline for the messy lecture.
- Trial 3 used the same lecture the instructions were fixed for, so the result may be tuned to it. I did not test a fourth, new lecture.
- The monthly impact is computed from Trial 1 only.
- Slide numbers in the output are sometimes approximate, so I check them against the file.

## Risks and Controls

| Item | Answer |
|---|---|
| Worst case | Studying from a summary that contains an error or an invented fact |
| Control | The "nothing outside the slides" rule, the [needs verification] flag, and my own review against the slides |
| Disclosure | Summaries are AI-generated and reviewed by me |
| If the app changes | The instruction text above stays, and works in any app |

## 30-Day Plan

- **Day 1:** Save the updated instructions in the Project.
- **Week 1:** Try a new lecture, measuring time and number of corrections.
- **Month 1:** Collect 4 measurements and compare them to the 90-minute baseline.

**Decision after one month:** continue if average time stays under 45 minutes with 3 corrections or fewer; otherwise adjust the instructions.

---

*All numbers in this project were measured with a timer on lectures from an NLP course. Only course slides were used.*
