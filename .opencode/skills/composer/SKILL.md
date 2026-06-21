---
name: composer
description: Compose multi-intent responses — merge multiple answers into one coherent customer reply
---

## When to Use
When customer asks multiple questions in one message, or when answers span multiple categories.

## Rules
1. Order answers from most critical to least critical
2. Separate each topic with a blank line (no explicit separator text)
3. Keep opening and closing only once (not repeated per answer)
4. Deduplicate blog links (if same link appears twice, reference it once)
5. Merge overlapping content (if two answers cover the same topic, combine them)

## Composer Pattern
```
เรียน ผู้ใช้บริการ

[Answer to question 1 — the most urgent/critical]

[Answer to question 2 — supporting/relevant]

[Answer to question 3 — if any]

[Any follow-up questions to customer, e.g. asking for instance name/IP/time]

ขอบคุณครับ
```

## Style Consistency
- Same tone throughout (not mixing styles)
- All links follow same format: "รายละเอียดตามลิงก์แนบ: [URL]"
- Use "ครับ" consistently (not mixing with "ค่ะ")
