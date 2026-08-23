# AIP-C01 War Room

A self-contained study workspace for the **AWS Certified Generative AI Developer – Professional
(AIP-C01)** exam, built from the [official exam guide](https://docs.aws.amazon.com/aws-certification/latest/ai-professional-01/ai-professional-01.html).

Everything lives in a single file: `index.html`. No build step, no dependencies, no server.
Open it in a browser and it works offline (web fonts are the only external request).

## What is in it

| Section | Contents |
|---|---|
| Overview | Exam facts, official domain weightings, exam-taking strategy, AWS cost guardrails |
| 30-day plan | 30 sequenced day-cards, 133 checkable tasks, roughly 2–3 hours a day |
| Domain deep dives | All 22 official task statements with notes, decision tables, and trap callouts |
| Decision playbook | 10 "choose the right thing" comparison tables |
| Numbers | Limits, quotas, and exact service names worth memorising |
| Hands-on labs | 12 labs for your own AWS account, with cost estimates and mandatory teardown |
| Question bank | 120 authored scenario questions with full distractor analysis |
| Mock exam | 65 questions in 156 minutes, drawn at the official domain weighting |
| Flashcards | 75 recall cards; missed cards re-queue |

## Exam facts

- 75 questions (65 scored, 10 unscored), 180 minutes
- Passing score 750 of 100–1000, compensatory scoring
- Domain weights: D1 31%, D2 26%, D3 20%, D4 12%, D5 11%

## Progress tracking

Plan checkboxes, lab progress, question answers, and flashcard stats are stored in
`localStorage` under the key `aipc01.v1`. Progress is per browser and per device, and is
**not** synced or committed. "Reset all progress" in the sidebar clears it.

## Practice questions

The 120 questions are original, written against the official task statements to mirror the
real exam's format, weighting, and trap patterns. They are not recalled exam content — real
AIP-C01 items are protected by the AWS certification agreement.

## Cost warning

Two lab resources bill continuously and are easy to forget:

- **OpenSearch Serverless collections** — per OCU-hour, with a minimum floor even when idle
- **Provisioned Throughput model units** — hourly, and commitment terms cannot be cancelled

Delete both as soon as a lab ends. Set a budget alarm before starting Lab 1.

## Editing

`index.html` is a single ~345 KB file: `<style>` block, static markup for the overview,
playbook and reference pages, then one `<script>` holding the content data
(`DOMAINS`, `PLAN`, `LABS`, `Q`, `CARDS`) followed by the rendering and quiz logic.
To add questions, append to the `Q` array — each entry needs `d`, `s`, `t`, `stem`, `ask`,
`opts`, `a`, `why`, and a `no` array explaining every incorrect option.
