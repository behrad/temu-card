# R2: How Temu has responded to the €3 duty

Researched 2026-10-02 for wayfinder ticket R2 (PRD open questions Q1, Q2, Q8).

**Caveat on evidence quality.** Temu has made no public statement on the €3 duty that I could find. The primary sources are Temu's own NL Terms of Use, PDD's Q2 2026 earnings call, the European Commission's guidance, and Douane.nl statistics. Everything about Temu's checkout UI (labels, promos, cart hints) comes from consumer and SEO blogs, mostly about the German store, so this note marks those claims low confidence. The live-inspection ticket (Inspect Temu NL cart and checkout) still has to confirm them. Web search hit a session limit before I could collect post-July ad-spend data.

---

## 1. Share of EU/NL orders shipped from EU warehouses; labels; duty status

**Answer.**
- **The "~80%" figure is an old aspiration with no date attached.** It was reported in January 2025 as "Temu says it will *eventually* process as much as 80 percent of European sales through these local warehouses" ([Ecommerce News EU, 2025-01-20](https://ecommercenews.eu/temu-80-of-european-sales-via-local-warehouses/)). The "by end of 2026" deadline appears only in SEO/drop-shipping blogs.
- **Neither Temu nor PDD has published an actual EU or NL local-fulfilment share.** On the Q2 2026 call (2026-08-24), PDD said only that it is "accelerating the build-out of local warehousing and fulfillment infrastructure and expanding the coverage of local fulfillment" and will "onboard and support more high-quality local merchants". It also said the EU duty will have "a considerable impact on those parts of our business" ([transcript, TradingKey](https://www.tradingkey.com/news/transcripts/262128548-tradingkey); [Supply Chain Dive, 2026-09-03](https://www.supplychaindive.com/news/temu-owner-invests-in-local-fulfillment-in-face-of-de-minimis-changes/829446/)). Supply Chain Dive also notes merchants still source mainly from China.
- **Market-wide NL evidence of the shift is strong.** Douane.nl (2026-09-01) reports that e-commerce declarations in July–August fell 46% against the H1 2026 average, declaration lines fell 70%, and regular (bulk) declarations rose 20%. Douane attributes this to webshops switching to bulk import and storage inside the EU ([Douane.nl](https://www.douane.nl/webwinkels-passen-werkwijze-aan-na-invoering-3-euroheffing/)). The figures cover all platforms, not Temu alone.
- **Labels.** Blogs report a "Local warehouse" tag or truck icon on listings, a search filter, and a "Lokal" tag in the German store ([monsterdealz, 2026-09-09](https://www.monsterdealz.de/magazin/temu-zoll); [Letem světem Applem, 2026-07-02](https://www.letemsvetemapplem.eu/en/2026/07/02/temu-eu/)). No Temu help page confirming this was found.
- **Duty-free?** Legally yes for the consumer parcel. Goods already in free circulation in the EU are not a low-value import, so the €3 does not apply to them. The duty is paid upstream on the bulk import, at normal rates. Blogs say EU-stock listings carry higher prices (for example €2.79 vs €4.49 for the same phone case, per landedcosthub), but this is unverified.

**Confidence.** Medium that a strong shift to EU stock is under way (Douane data plus PDD statements). Low on any Temu-specific share: none is published. Low on the label wording.

## 2. How Temu shows the duty to NL buyers; absorption; consignments

**Answer.**
- **Collected at checkout, not at the door.** Temu's NL Terms of Use (effective 2026-04-19; [Wayback snapshot 2026-08-30](http://web.archive.org/web/20260830153807/https://www.temu.com/nl-en/terms-of-use.html)) say: "Unless otherwise specified at checkout … all prices displayed … are inclusive of all applicable VAT, customs-related duties, taxes and fees". For products where duties are not included, Temu "offer[s] … Import Fees estimation during checkout" and may require an "Import Fee deposit". The buyer authorises a forwarder to act as their direct representative.
- **Itemized or lump sum?** No reliable source settles this. One blog with screenshots of the German store, a new account, September 2026, says import charges appear "as its own line item in the order summary before you pay" ([RefundRadar, 2026-09-14](https://refundradar.co/blog/temu-eu-import-fees/)). It does not say the line is broken down per tariff line. This remains **open for the live test**.
- **Partial absorption: yes, in two ways.**
  1. *Contractual cap (primary source).* The ToS say: "If the actual Import Fees are more than the Import Fees deposit, you will not be charged any additional amounts. If … lower …, you will be automatically refunded the difference". Temu therefore absorbs under-estimates and refunds over-estimates after the carrier invoices.
  2. *Promo (blog only).* "Temu covers X% of import charges for orders over €30, up to €20". The rate is personalised ("automated decision-making") and was 40% on one German account ([RefundRadar](https://refundradar.co/blog/temu-eu-import-fees/)).
- **Consignments.** By law, one order dispatched in several parcels counts as **several consignments**. EC guidance §3.3: "goods covered by the one order placed by the same person, but dispatched separately, should be considered as separate consignments". The duty applies "per declaration line" within each declaration, and grouping lines into one is disallowed ([EC guidance](https://taxation-customs.ec.europa.eu/news/guidance-and-legal-text-temporary-flat-fee-low-value-imports-which-will-apply-until-1-july-2028-2026-06-08_en)). A tariff line that appears in two parcels of the same order is therefore charged twice. I found **no source** on whether Temu NL splits orders more or less since July. Also, the legal "item" is same tariff classification **+ description + origin (where declared)**, not only HS code (EC guidance §3.3.1).
- **Line-count context.** Douane figures show average e-commerce declaration lines per declaration fell from 3.24 (June) to 2.02 (July) and 1.70 (Aug, to 25 Aug). Across all platforms, the typical non-EU parcel now carries about 2 duty lines, roughly €6–7 including VAT.

**Confidence.** High on collection at checkout, the deposit and the refund (Temu ToS). High on the per-parcel rule (EC). Low on the UI line format and the promo. Unknown on Temu's splitting behaviour.

## 3. Has Temu shipped its own tools that already solve the PRD's problem?

**Answer: partly, if the blog report holds.**
- Per RefundRadar (German store, September 2026), Temu tags items in the cart **"No import charges with current cart"** when they share an HS category with something already in the cart. That is Temu itself pointing out marginal €0 lines, which overlaps PRD F5 for adding items, though not for removing them.
- There is a "Local warehouse" filter and tag (blogs). The ToS guarantee no surprise top-up, and there is a "Temu covers X%" promo.
- I found no evidence of a per-tariff-line breakdown, a "remove this to save €3" hint, or an NL-specific free-duty threshold.

**Confidence.** Low until the live NL test confirms it. If it is confirmed, the PRD's core differentiation narrows to explaining the whole cart and advising removals.

## 4. Ad spend, pricing and strategy shifts

- **Strategy.** PDD (Q2 2026 call) is prioritising local merchants, local and transit warehousing, and merchant-cost support. It reported net income down 12% year on year, citing reinvestment and the EU duties ([BigGo summary](https://finance.biggo.com/news/US_PDD_2026-08-24); [Yahoo highlights](https://finance.yahoo.com/markets/stocks/articles/pdd-holdings-inc-pdd-q2-190037573.html)). In answer to an analyst, management stressed quality, merchant costs and profitability over an immediate rise in advertising.
- **Ad spend.** The last hard data predates the duty: in April 2025, after the US de minimis ended, Temu raised digital ad spend in France by 115% and in the UK by 20% (Reuters exclusive via [Yahoo Finance](https://finance.yahoo.com/news/exclusive-shein-temu-ramp-advertising-204328837.html)). **I found no post-July-2026 EU ad-spend data** (unverified).
- **Demand signals (NL).** Temu's NL monthly active users per its DSA reports were 4.8M in H2 2025 and 4.6M in H1 2026 ([Ecommerce News NL, 2026-09-08](https://www.ecommercenews.nl/aliexpress-shein-en-temu-verliezen-bereik-in-nederland/)), mostly before the duty. In an RTL Nieuws panel survey, 46% of Dutch respondents say they order less from Chinese webshops since July ([NL Times, 2026-08-10](https://nltimes.nl/2026/08/10/half-dutch-ordering-shein-temu-less-frequently-since-eus-import-tariff)). This 46% is a different statistic from the Douane 46% and the two should not be conflated.
- **Pricing.** No primary evidence of Temu repricing. Blogs claim EU-stock listings cost more (unverified).
- **How long the €3 problem lasts.** The €3 regime runs to 2028-07-01. Its relevance to Temu carts shrinks as the EU-stock share rises, and both PDD's stated direction and the Douane data point that way. The rate of change for Temu NL specifically is unknown.

---

## PRD claims checked

| PRD claim | Verdict | Reason |
|---|---|---|
| "Temu shows the full total at checkout, but only as a lump sum." | **Unverified** | ToS confirm duties are estimated and collected at checkout. One blog says it is a separate line, but no source shows whether it is broken down per tariff line. Needs the live test. |
| "Buyers see a €23 basket become €52" | **Unverified** | No source found. The PRD's cited De Buren article gives a different anecdote (€34 → €64). Douane data suggest about 2 lines per parcel on average, so this is an outlier example. |
| "Dutch reviews since July are full of this complaint" | **Unverified** | No review corpus checked. The RTL survey shows dissatisfaction, but about value and quality, not itemization. |
| "Dutch customs saw e-commerce declarations fall 46% in July–August" | **Confirmed** (wrong citation) | Douane.nl, 2026-09-01: −46% against the H1 average, with lines down 70% and August counted only to 25 Aug. The PRD's cited source (De Buren) does not contain the figure; cite Douane.nl instead. |
| Duty applies "per tariff line" per order (F4: €3 × distinct tariff lines) | **Partly wrong** | The legal unit is per declaration line **per consignment**, and an item is classification + description + origin. One order shipped in several parcels pays separately per parcel (EC guidance §3.3). |
| Risk: "Temu itself adds a per-item duty breakdown at checkout — Medium" | **Unverified, likely understated** | Temu reportedly already shows "No import charges with current cart" on same-HS items (DE store, blog), which is part of the PRD's value. |
| Risk: "Temu moves most NL volume to EU stock — Medium, rising" | **Confirmed directionally** | PDD Q2 call (accelerating local fulfilment) and Douane data (lines −70%, bulk declarations +20%). No Temu NL share has been published. |
| Implied ~80% EU-warehouse target (ticket brief) | **Wrong as a dated target** | The only primary-ish wording is "will eventually" (Jan 2025). "By end of 2026" appears only in low-quality blogs, and no actual share has been disclosed. |
| F10 premise: Temu's own duty figure may be readable at checkout | **Likely confirmed** | ToS describe an "Import Fees estimation during checkout" and deposit. Note that it is an estimate or deposit that may be partly refunded later, and may be discounted by the "Temu covers X%" promo. |
| Success metric: "Match Temu's own checkout total within €3 on ≥90% of carts" | **At risk** | Temu's displayed figure is an estimate with possible personalised promo discounts and later refunds, so the "actual" figure is ambiguous. F11 should capture the deposit, the promo and the refund separately. |
| Q8 premise: EU-stock listings are duty-free | **Confirmed in law; labels unverified** | Goods in free circulation do not attract the €3 on delivery. Reliability of the "Local warehouse" label in NL is unverified. |
| "€2 EU handling fee per consignment expected from November 2026" | **Unverified** (out of scope) | Low-quality sources conflict between per consignment and per line. Leave to Q9. |

## Sources

Primary:
- Temu NL Terms of Use, effective 2026-04-19 — [Wayback 2026-08-30](http://web.archive.org/web/20260830153807/https://www.temu.com/nl-en/terms-of-use.html)
- European Commission, guidance and Q&A on the temporary €3 duty (guidance §3.3 and §3.3.1; Q&A updated 2026-06-30) — [taxation-customs.ec.europa.eu](https://taxation-customs.ec.europa.eu/news/guidance-and-legal-text-temporary-flat-fee-low-value-imports-which-will-apply-until-1-july-2028-2026-06-08_en)
- Douane.nl, "Webwinkels passen werkwijze aan na invoering 3 euroheffing" (2026-09-01) — [link](https://www.douane.nl/webwinkels-passen-werkwijze-aan-na-invoering-3-euroheffing/)
- PDD Holdings Q2 2026 earnings call (2026-08-24) — [transcript, TradingKey](https://www.tradingkey.com/news/transcripts/262128548-tradingkey)

Reputable press and trade:
- Supply Chain Dive (2026-09-03) — [link](https://www.supplychaindive.com/news/temu-owner-invests-in-local-fulfillment-in-face-of-de-minimis-changes/829446/)
- NL Times on the RTL Nieuws survey (2026-08-10) — [link](https://nltimes.nl/2026/08/10/half-dutch-ordering-shein-temu-less-frequently-since-eus-import-tariff)
- Ecommerce News NL, DSA MAU figures (2026-09-08) — [link](https://www.ecommercenews.nl/aliexpress-shein-en-temu-verliezen-bereik-in-nederland/)
- Ecommerce News EU, 80% "eventually" (2025-01-20) — [link](https://ecommercenews.eu/temu-80-of-european-sales-via-local-warehouses/)
- Reuters exclusive on 2025 EU ad spend (via Yahoo) — [link](https://finance.yahoo.com/news/exclusive-shein-temu-ramp-advertising-204328837.html)
- Euronews (2026-07-01): no Temu statement — [link](https://www.euronews.com/my-europe/2026/07/01/eu-slaps-3-duty-fee-on-shein-temu-and-aliexpress-imports)
- Consumentenbond (updated 2026-09-29) — [link](https://www.consumentenbond.nl/acties-claims/nieuws/2026/nieuwe-douaneregel-voor-pakketjes)
- De Buren (2026-07-14), the PRD's cited source — [link](https://www.deburen.nl/2026/07/14/2-weken-nieuwe-douaneregels-dit-merk-je/)

Low-quality (flagged; use only as leads for the live test):
- RefundRadar (2026-09-14): "No import charges with current cart", "Temu covers X%", line item — [link](https://refundradar.co/blog/temu-eu-import-fees/)
- monsterdealz (2026-09-09): "Lokal" tag, ToS summary — [link](https://www.monsterdealz.de/magazin/temu-zoll)
- Letem světem Applem (2026-07-02): user reports of EU-warehouse shipping — [link](https://www.letemsvetemapplem.eu/en/2026/07/02/temu-eu/)
- landedcosthub (EU-stock price premium) — [link](https://landedcosthub.com/guide/temu-import-costs-eu/)
- Various SEO blogs asserting "80% by end of 2026" (forestshipping, amzprep, factually.co): not relied on.
