# dodonai-assets

Public image host for Dodonai social media campaigns.

Images here are referenced by URL from the [buffer-toolkit](https://github.com/likke/buffer-toolkit) (private). Buffer's API requires publicly reachable media URLs; this repo provides them via `raw.githubusercontent.com`.

## Cards

The `/social-cards/` directory holds the 6-card series repurposed from Dodonai blog posts. Pattern:

```
https://raw.githubusercontent.com/likke/dodonai-assets/main/social-cards/<id>.png
```

| ID | Theme | Source blog post |
|---|---|---|
| 01-eighty-pages | 80-page deposition summarized in seconds | `/blog/80-pages-in-seconds-a-real-transcript-walkthrough` |
| 02-hidden-cost | $1,000+ per deposition review | `/blog/how-many-hours-do-you-lose-reading-transcripts` |
| 03-outsourcing-cost | $15/page → $0.02/page | `/blog/real-cost-of-outsourcing-medical-record-summaries` |
| 04-verify-not-trust | Verify AI summaries, don't trust them | `/blog/how-review-teams-verify-ai-deposition-summaries-before-use` |
| 05-contradictions | Find contradictions without re-reading | `/blog/find-contradictions-in-deposition-transcripts-without-re-reading-the-transcript` |
| 06-without-burnout | Chronologies without burnout | `/blog/medical-chronologies-without-burnout-how-teams-save-hours-every-week` |

## Visual system

Light theme: ghost-white background, midnight-blue headlines, royal-blue accent word, medium-slate concentric-rings motif top-right. Plus Jakarta Sans throughout. Distinct from the GeoLocally dark theme (see `likke/geolocally-assets`).

## Regenerating

Cards are code-rendered, not hand-designed. To change copy or layout:

1. Edit `src/cards/dodonai/cards.json` or `src/cards/dodonai/template.html` in the buffer-toolkit repo
2. `node bin/buffer.js render-cards --brand dodonai`
3. `cp assets/social-cards/dodonai/*.png ../dodonai-assets/social-cards/`
4. `cd ../dodonai-assets && git add . && git commit -m "Regenerate cards" && git push`
