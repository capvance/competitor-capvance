# Deals tracker — how to use

One row per deal you spot in the feeds. Fill in what you can from the headline/article, look up the website manually (~30 sec per deal), skip fields you don't know.

## Column definitions

| Column | What goes here | Example |
|--------|----------------|---------|
| `deal_date` | Date the deal was announced (from the press release) | `2026-04-22` |
| `date_spotted` | Date you saw it in your aggregator | `2026-04-23` |
| `source_feed` | Which feed surfaced it | `Modern Healthcare M&A` |
| `industry` | Healthcare / Accounting / Manufacturing | `Healthcare` |
| `geography` | US / UK / AU | `US` |
| `acquirer_name` | Who bought it | `Smile Brands` |
| `acquirer_type` | `PE platform` / `PE add-on` / `strategic` / `family office` / `unknown` | `PE add-on` |
| `acquired_company` | Who was sold | `Denver Family Dental` |
| `acquired_website` | **The whole point** — their website | `denverfamilydental.com` |
| `acquired_city` | City/region | `Denver, CO` |
| `acquired_country` | Country | `US` |
| `sub_segment` | Specific niche (dental, bookkeeping, F&B manufacturing, etc.) | `Dental DSO` |
| `deal_size` | If disclosed (you said you'd handle this side) | `$12M` or `undisclosed` |
| `headline` | Copy-paste the press release title | `Smile Brands acquires Denver Family Dental` |
| `source_url` | Link back to the press release / article | `https://...` |
| `already_pe_owned` | Was the target already PE-owned before this deal? `yes`/`no`/`unknown` | `no` |
| `fits_pitch_criteria` | Does this deal produce useful lookalikes to pitch? `yes`/`no`/`maybe` | `yes` |
| `priority` | `A` / `B` / `C` — how strong is the pitch trigger | `A` |
| `lookalike_list_built` | Have you built the prospect list yet? `yes`/`no` | `no` |
| `outreach_sent` | Has outreach gone out? `yes`/`no` | `no` |
| `notes` | Anything else — owner age, why it's interesting, which comp it's like | `Owner 58yo, 3 locations, great DSO comp` |

## Suggested workflow (~10 min/day)

1. **Morning:** open ⭐ Closed Deals in your aggregator
2. For each relevant deal:
   - Add a row with `date_spotted` = today
   - Copy the headline + source URL straight from the RSS item
   - Google the acquired company's name → grab their site → drop it in `acquired_website`
   - Quick gut check on `fits_pitch_criteria` (wrong size / already PE-owned / wrong sub-segment = `no`)
3. **Weekly:** filter to `fits_pitch_criteria = yes` and `outreach_sent = no` — that's your actionable backlog

## What to skip filling in

- **`deal_size`** — you said you'd handle this side. Leave blank or put `handled separately`.
- **`already_pe_owned`** — if unclear from the press release, leave as `unknown` and don't dig further unless you're about to pitch. Saves 5 min per deal.
- **`lookalike_list_built` / `outreach_sent`** — blank until you kick off that phase.

## Calibration — what to watch for in week 1

After 5-7 days of this, you'll have 30-100 rows. Ask yourself:

1. **Which `source_feed` produces the most `fits_pitch_criteria = yes`?** That's where to tune alerts and noise rules first.
2. **Which `source_feed` produces mostly `no`?** Either tighten its filter or drop it.
3. **What `sub_segment` is over- or under-represented vs. what you actually want to pitch?** Adjust the Google Alert strings accordingly.
4. **How often is `acquired_website` not findable?** If it's frequent (>20%), that's when Option 2 (LLM extraction) becomes worth building.

Tell me what you learn after a week and I'll help tune.

## Tips for finding the website fast

- Google: `"[acquired company name]" [city]` — top result is usually their site
- If the target is tiny/local: try `"[company name]" site:linkedin.com/company` → their LinkedIn usually links their website
- If the deal press release is on BusinessWire/PRN: scroll to the bottom — "About [Target Company]" paragraph often has the URL
- Companies House (UK) and ASIC (AU) lookups can backfill for UK/AU deals where the press release is thin
