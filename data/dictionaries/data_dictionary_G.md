# Data Dictionary — Dataset G: Finance Headlines Sentiment

**File:** `data/processed/dataset_G_finance_headlines_sentiment.csv`
**Source:** Curated from `data/raw/reddit_wsb.csv` (Reddit r/wallstreetbets, Jan 2021 GME event)
**Rows:** 144 | **Columns:** 6

| Column | Type | Description |
|---|---|---|
| `date` | datetime | Post timestamp (YYYY-MM-DD HH:MM:SS) |
| `headline` | string | Reddit post title (used as finance headline proxy) |
| `source` | string | Always "reddit_wsb" |
| `market_tag` | string | Always "GME" (GameStop) |
| `engagement_score` | integer | Reddit upvote score (proxy for community engagement) |
| `sentiment_label` | categorical | Sentiment: positive, negative, neutral |

## Curation process
1. Filtered posts with title length > 20 characters.
2. Sampled ~150 posts spread proportionally across dates.
3. Applied **rule-based keyword sentiment classification** (not ML-based):
   - Positive keywords: moon, rocket, hold, diamond, buy, win, squeeze, tendies, yolo, gain, bull, profit, 🚀, 💎, etc.
   - Negative keywords: loss, sell, crash, fear, drop, short, halt, manipulation, ban, restrict, dump, etc.
   - If positive keyword count > negative → "positive"; if negative > positive → "negative"; else → "neutral".

## Important teaching notes
- **Sentiment labels are rule-based approximations**, NOT gold-standard human labels.
- This is intentional: students should discuss label quality, noise, and the difference between rule-based and ML-based sentiment.
- The dataset covers a single market event (GME short squeeze) — not representative of general market sentiment.
- Designed as a small, stable teaching dataset. No API dependency.
