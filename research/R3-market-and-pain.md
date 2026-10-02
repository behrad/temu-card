# R3 — Is the "why is my cart expensive" pain real and big enough?

Ticket: `wayfinder/tickets/R3-market-and-pain.md` · Researched 2026-10-02 · PRD: "Temu Cart Optimizer, Phase 1"

## TL;DR

- **The pain exists, but it is thin and mostly "too expensive", not "confused about why".** In Dutch Trustpilot reviews of Temu (about 56k reviews), keyword searches turn up only about 5 reviews from after July 2026 about the duty. The latest page of 18 NL reviews contains none. Most duty complainants know exactly what the charge is. A few are confused, and one explicitly asks for the PRD's feature.
- **Volume is collapsing, and Douane says that is mostly a routing shift, not demand.** NL e-commerce (H7) declarations fell 46% and declaration lines fell 70% (Jul–Aug vs. the Jan–Jun average). Douane attributes this to bulk import and EU warehousing. The duty-bearing cart, which is the extension's whole surface, is shrinking quickly.
- **The reachable segment is small and unmeasured.** No public NL app/desktop split for Temu exists. Proxies (DK: 51% of Temu purchases via mobile; NL desktop browsing is 33% of page views, of which Chrome is 57%) put desktop-Chrome monthly Temu buyers in the low hundreds of thousands at most. That is an upper bound before the EU-warehouse shift.
- **Buyers and the market are already batching or trimming.** Lines per NL declaration halved (3.2–3.7 → 1.7–2.0). In Belgium the average declared value per consignment almost doubled. There are a few verbatim cases of people consolidating orders by hand.

---

## 1. Order volumes after July 2026

**Answer.** Douane Nederland's own table, published 2026-09-01:

| Month 2026 | E-commerce declarations | Declaration lines | Lines/decl. |
|---|---|---|---|
| Jan | 17,627,516 | 58,512,854 | 3.32 |
| Feb | 14,159,983 | 48,978,784 | 3.46 |
| Mar | 19,576,640 | 66,234,415 | 3.38 |
| Apr | 18,869,220 | 66,698,152 | 3.53 |
| May | 19,172,116 | 69,898,657 | 3.65 |
| Jun | 21,995,636 | 71,173,696 | 3.24 |
| **Jul** | **12,541,096** | **25,389,827** | **2.02** |
| **Aug (to 25 Aug)** | **7,651,673** | **13,010,602** | **1.70** |

- Douane: −46% average declarations and −70% lines in Jul–Aug vs. the Jan–Jun monthly average. In the same period regular (non-e-commerce) declarations rose 20% and their lines rose 30%. NL collected about €35M for the treasury in July.
- **My recomputation:** the 46% only reproduces if the partial August (25 days) is averaged as if it were a full month. Pro-rated to 31 days, the drop is about **−41%** for declarations and **−67%** for lines. July alone was −32% vs. the H1 average (−43% vs. June).
- **Douane's stated cause:** *"Steeds meer bedrijven lijken te kiezen voor bulkinvoer en opslag binnen de EU om van daaruit hun spullen door te verkopen aan de consument."* In other words, this is a channel shift into the EU, not purely lost demand.
- **Consumer side (RTL Nieuws Nieuwspanel, reported 10 Aug 2026):**
  - 46% of Dutch respondents order *less* from Chinese webshops (Temu/Shein/AliExpress) since July.
  - 47% have ordered from one recently, and 20% order at least monthly.
  - Reasons given: 73% say the price/quality ratio is no longer worth it, 64% cite quality, 33% cite safety.
  - The Nieuwspanel is an opt-in panel, not a representative sample. I could not reach the RTL original (rtl.nl returns 403 to fetches), so the figures come via NL Times / IamExpat.
- **Belgium as a comparator (FOD Financiën, ministers Jambon/Clarinval):**
  - −53% H7 declarations in July 2026 vs. July 2025.
  - +102% H1 (>€150) declarations.
  - Average declared value per consignment went from €5.73 to €10.85.
  - €223.7M collected between 29 Jun and 16 Aug.
- **Commission EU-wide post-July data:** none found. The Commission only cites the pre-reform baseline (about 4.6–5.9 bn low-value items in 2025).
- **Coincidence warning:** two different "46%" figures circulate. One is Douane's declarations figure; the other is RTL's "ordering less" figure. NL Times also mislabels the Douane figure as "parcels from China fell 46%". In fact it counts declarations, from all non-EU origins.

**Confidence:** high for the Douane numbers (primary source); medium for RTL (secondary reporting, non-representative panel).

**Sources:**
- Douane, "Webwinkels passen werkwijze aan na invoering 3 euroheffing" (2026-09-01): https://www.douane.nl/webwinkels-passen-werkwijze-aan-na-invoering-3-euroheffing/
- NL Times on Eerenberg's Kamerdebat figures: https://nltimes.nl/2026/09/02/sharp-drop-packages-china-since-new-eu-import-duty
- TaxLive: https://www.taxlive.nl/nl/documenten/nieuws/douane-ziet-na-nieuwe-invoerheffing-fors-minder-pakjes-uit-china-komen/
- NL Times on the RTL survey: https://nltimes.nl/2026/08/10/half-dutch-ordering-shein-temu-less-frequently-since-eus-import-tariff
- IamExpat: https://www.iamexpat.nl/expat-info/dutch-news/temu-and-shein-orders-drop-netherlands-after-eu-tax
- Belgium: https://news.belgium.be/nl/de-eerste-resultaten-van-het-tijdelijke-douanerecht-van-3-eu-bevestigen-de-impact-ervan-op-niet

## 2. Buyer complaints: "confused about why" vs. "just too expensive"

**Answer.**
- **The complaint is real but rare.** Nearly all duty complaints are "too expensive" and come from people who know it is the €3 duty.
- **"Confused about why" exists but is a minority.** It is also partly a misunderstanding of the *mechanism*: people think it is per item, or per parcel, or already included in the price. They are not asking which item caused the charge.
- **One review asks Temu for exactly the PRD's feature:** show each item's category so the buyer can avoid extra lines.

**Volume check (Trustpilot NL, temu.com, 1.8★, ~56,200 reviews, `languages=nl`):**
- `invoerrechten`: 6 hits in total, 3 dated after 1 Jul 2026.
- `heffing`: 0 hits.
- `douanekosten`: 1 hit (an older review edited later).
- `3 euro`: 4 hits after July, of which 1 is cost-related.
- `categorie`: 1 hit after July.
- The most recent 18 NL reviews (to 2 Oct 2026) contain **zero** duty mentions. They are dominated by refunds, non-delivery and quality.

### "Too expensive" (knows the cause)

- **Trustpilot, JPM Havermans, 18 Sep 2026, 1★:** "Echt niet, €3 extra betalen. Invoerrechten, Maakt Temu duurder dan EU bedrijven. Bedrijven werkzaam in Nederland moeten de totale prijs vermelden." — https://nl.trustpilot.com/reviews/6aad994c1a2577c582ee1900
- **Trustpilot, Yoke, 3 Sep 2026, 1★:** "Je koopt iets voor 25 euro en met invoerrechten is het 50 euro. Sorry maar ik shop liever de sales bij Zara" — https://nl.trustpilot.com/reviews/6a99afe85b530fffb48389ad
- **Reddit r/europeanunion, u/Kak6u9, 1 Jul 2026:** "want to buy a 0.10€ pack of resistors? fuck you, now its 3.10€" — https://www.reddit.com/r/europeanunion/comments/1ukqm64/new_law_for_any_orders_outside_the_eu_under_150/
- **Reddit r/europeanunion, u/AiggyA, 2 Jul 2026:** "Pulleys that were 1€ are now 8€." — https://www.reddit.com/r/europeanunion/comments/1ukqm64/new_law_for_any_orders_outside_the_eu_under_150/ov3vbb0/

### "Confused about why" / wants control

- **Trustpilot, Jo Smit, 20 Jul 2026, 1★.** This is the closest match to the PRD:

  > "…nu met de nieuwe regeling cq invoer en verzendingskosten is het minder aantrekkelijk geworden. Speciaal met de verschillende categorieën Waarom niet bij elk te kiezen artikel een code tot welke categorie deze behoord en zo de klant de mogelijkheid bied om een te wensen productserie te kiezen om niet met torenhoge invoerrechten en verzendkosten geconfronteerd te worden."

  https://nl.trustpilot.com/reviews/6a5df6276e7ae32a79e33175
- **Trustpilot, O. Schreuder, 26 Jul 2026:** "Er stond bij mijn bestelling 'gratis verzenden'. Ik heb voor 23 euro gekocht, moest toch 7 euro bij betalen."
  - The buyer attributes the charge to shipping. The €7 matches 2 tariff lines × €3 + 21% VAT (€7.26).
  - Search URL: https://nl.trustpilot.com/review/temu.com?languages=nl&search=3%20euro
- **Reddit r/europeanunion, u/Snoo-35855, 1 Jul 2026 (OP):** "The order was 20€ and i tried ordering . In checkout i see 50€ . I wonder why and i check to see there customs service fre for 29€!!!. Then i search up and saw the new law" — https://www.reddit.com/r/europeanunion/comments/1ukqm64/new_law_for_any_orders_outside_the_eu_under_150/
  - This is a single lump-sum line, which matches the PRD's description.
  - The post's title itself misstates the rule ("3€ for every item").
- **Reddit r/europeanunion, u/lawrotzr, 14 Aug 2026:** "Yes, but the tax is per parcel." This is a misconception; the duty is per tariff line. — https://www.reddit.com/r/europeanunion/comments/1vnzm47/half_of_dutch_ordering_from_shein_temu_less/p3mglo4/
- **Trustpilot, John Koch** (review dated 29 Aug 2026; the ID suggests it was first written in Jan 2025 and edited later): "de douanekosten zijn al berekend in de prijs." This is another misconception, and it may predate the levy. — https://nl.trustpilot.com/reviews/678b82ba9d6d2b5c783576be
- **The media is confused too.** Several outlets describe the charge as "€3 per item" (hwbusters, euro2day). One NL tip article tells readers to split categories into *separate orders* to save money, which saves nothing.

### Not sampled

- **Tweakers:** returns 403 to both curl and fetch.
- **Facebook koopjes groups:** login wall.
- **Reddit r/thenetherlands:** searched via RSS and returned no post-July Temu threads. Reddit rate-limited (429) most queries, so coverage is partial.

**Confidence:** medium that complaints are sparse and mostly price-driven (consistent across sources). Low on exact proportions (small sample; Trustpilot quotes were extracted through a fetch tool, so spot-check them at the links).

## 3. Temu NL traffic: app vs. desktop web (PRD Q6)

**Answer.** **No public NL-specific split exists.** Similarweb's free page does not show device split or the NL share. The best proxies:
- **Denmark (Dansk Industri, Aug 2025):** *"Temu er også app-fokuseret, men her foregår kun 51% af købene via mobil"*. Shein is at 84%. Temu's buyer base skews older and more computer-based. The figure is not specific to the app (mobile may include mobile web), and the data source is not stated.
  - https://www.danskindustri.dk/vi-radgiver-dig/ecommerce/nyhedsarkiv/nyheder/2025/08/temu-vs.-shein-to-lavprisgiganter--to-vidt-forskellige-malgrupper
- **NL all-web device share (StatCounter, Sep 2026):** mobile 65.0%, desktop 33.2%, tablet 1.9%. Among desktop browsers, Chrome has 56.8% and Edge 18.3%. Edge can run Chrome extensions from the Chrome Web Store if the user allows it.
  - https://gs.statcounter.com/platform-market-share/desktop-mobile-tablet/netherlands
  - https://gs.statcounter.com/browser-market-share/desktop/netherlands
- **Temu NL users:** about 4.6M (Emerce, secondary). Temu EU DSA average monthly active recipients: about 124M for H1 2026 (search snippet; Temu's DSA page did not render for fetching).
  - https://www.emerce.nl/nieuws/omslagpunt-meer-shoppers-temu-amazon
- **Rough reachable segment (upper bound, low confidence):**
  - 20% monthly buyers × ~14.6M NL adults ≈ 2.9M monthly buyers. This covers all Chinese webshops, not Temu alone.
  - × 33–49% of purchases on desktop × ~57–75% Chrome or Chrome-compatible browser ≈ **0.5–1.1M**.
  - That figure is before excluding non-Temu shoppers, EU-warehouse items (no duty) and single-category carts (nothing to optimize). The realistic addressable segment is likely an order of magnitude smaller.

**Confidence:** low. No primary NL data exists; Q6 still needs the cohort poll the PRD proposes.

## 4. Do buyers already batch or trim carts by hand?

**Answer.** Yes, at market level. At individual level there is anecdotal evidence only.
- **NL:** lines per declaration fell from 3.2–3.7 (H1) to 2.0 in July and 1.7 in August. Remaining direct-ship parcels carry about half as many tariff lines.
  - This is consistent with buyers trimming categories, and also with platforms declaring coarser headings or moving multi-category baskets to EU stock.
  - The two causes cannot be separated from public data. This is relevant to PRD Q3 and ticket R5.
- **Belgium:** average declared value per consignment went from €5.73 to €10.85, which suggests consolidation into fewer, bigger parcels.
- **Verbatim:**
  - u/lawrotzr describes the batching logic ("buy 1 parcel with 3 items in it every 3 weeks"), though with the wrong per-parcel model.
  - Jo Smit asks Temu for category codes so he can choose a single "productserie".
  - Consumer guides (Hart van Nederland, HCC, Seniorweb) actively teach "combine items in the same category".
- **No Temu-specific hand-trimming community was found** (Reddit/Tweakers/Facebook coverage limited, see above).

**Confidence:** medium (aggregate data primary; individual behaviour anecdotal).

---

## PRD claims checked

| PRD claim | Verdict | Reason |
|---|---|---|
| "Dutch customs saw e-commerce declarations fall 46% in July–August" | **Confirmed (number), misleading in context** | Douane's own figure, measured against the Jan–Jun monthly average with a partial August (about −41% pro-rated). Douane attributes it to bulk import and EU warehousing, not demand. The PRD places it next to "complaints", which implies demand loss. |
| "Dutch reviews since July are full of this complaint" | **Wrong** | Only about 5 post-July NL Trustpilot reviews (of ~56k) mention the duty; the latest 18 NL reviews mention it zero times. Refunds, delivery and quality dominate. |
| "Buyers see a €23 basket become €52" | **Unverified but plausible** | Close real cases exist: €20→€50 (Reddit, €29 "customs service fee"), €25→€50 (Trustpilot). This implies about 8 tariff lines. The typical post-July parcel has about 2 lines (about +€7), as in the "€23 + €7" review. |
| "Temu shows the full total at checkout, but only as a lump sum…do not know which items caused it" | **Partly supported** | The Reddit OP saw a single "customs service fee" line, and Jo Smit asks for per-item categories. The Temu checkout itself was not inspected here (that is ticket T2). |
| Target user "orders from Temu at least monthly" is a real population | **Confirmed (with caveat)** | RTL: 20% of Dutch order monthly from Chinese webshops (all platforms, opt-in panel). |
| Q6: share of Dutch Temu orders on desktop Chrome vs. app | **Unverified (no public data)** | Only proxies: DK 51% mobile purchases; NL desktop is 33% of page views; Chrome is 57% of desktop. |
| Risk: "Most Dutch Temu buying happens in the app" (Medium) | **Unverified; likely "about half or more on mobile"** | The DK proxy suggests Temu is less mobile-heavy than Shein, but the NL web is 65% mobile. |
| Risk: "Temu moves most NL volume to EU stock" (Medium, rising) | **Confirmed directionally; underrated** | Douane explicitly cites bulk import and EU storage, and declaration lines fell 70%. Consider rating it High. |
| Pain is about "which items caused it / what to change" (vs. price) | **Mostly wrong** | Most complainants know it is the duty and object to the price. RTL reasons are dominated by price/quality (73%) and quality (64%). |
| Hold-list / batching is a real behaviour (Phase 2 idea) | **Supported** | Lines per declaration halved in NL, BE parcel value doubled, and consumer guides teach batching. |

## Gaps / follow-ups

- **RTL original article:** rtl.nl blocks fetches, so sample size and dates are unverified.
- **Tweakers, Facebook koopjes groups, r/thenetherlands:** not effectively sampled because of blocks and rate limits.
- **Lines-per-declaration collapse:** worth passing to R5/Q3. It may mean Temu now declares coarser headings, which would change what the extension must predict.
