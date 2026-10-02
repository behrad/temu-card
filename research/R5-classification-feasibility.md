# R5: Can tariff classification be predicted from Temu product data?

Researched 2026-10-02 for ticket `wayfinder/tickets/R5-classification-feasibility.md`. It checks the PRD's "Classification, two layers" approach and open question Q3.

## Headline

- **The target is Temu's classification, not the true one.** For IOSS parcels (H7 declaration) the legal unit is one declaration line per HS6 subheading (plus description). The declarant chooses that classification, and Temu charges the buyer at checkout from its own internal codes. An external classifier has to reproduce Temu's HS6 assignments, mistakes included.
- **Published accuracy is far below 90%.** On noisy e-commerce listings, the best LLMs and agents reach about **56–62% exact HS6** and about **70–72% HS4**, against 95% for human experts. Models trained on large in-domain sets of declaration data reach about 85% HS6. Nothing public supports 90%+ per item from a title and category.
- **Q3 is legally narrowed but not answered.** Grouping across subheadings is barred when the €3 applies, so Temu cannot legally declare buckets coarser than HS6. It can split finer. No public source shows what Temu's declarant actually files.
- **The biggest opportunity is that Temu may already show its own grouping.** A single blog source (German store, Sept 2026) reports a cart tag, "No import charges with current cart", on items that share an HS category with another cart item, plus a page listing items in the same tariff class. If the NL store has these, reading Temu's signals beats predicting HS6. It also threatens the PRD's value (see the end).

---

## 1. Public classification sources: what exists and how hard each is to use

**Answer:** The EU nomenclature data is free but has no official API. EBTI can only be searched through a web form. The only free JSON API that covers the EU nomenclature is HMRC's UK Trade Tariff API, through its Northern Ireland (XI) tariff, and its search is keyword lookup, not classification. Commercial classifiers exist. Only Zonos publishes prices. **Confidence: medium-high.**

| Source | What it gives | Access | Usefulness here |
| --- | --- | --- | --- |
| **EU TARIC** | Full CN8/TARIC10 nomenclature and measures | Web consultation ([TARIC](https://ec.europa.eu/taxation_customs/dds2/taric/taric_consultation.jsp)). Raw data is "freely available in Excel format" on CIRCABC ([Commission page](https://taxation-customs.ec.europa.eu/customs/common-customs-tariff-cct/tariff-classification-goods/eu-customs-tariff-taric_en), [CIRCABC group](https://circabc.europa.eu/w/browse/0e5f18c2-4b2f-42e9-aed4-dfe50ae1263b)). The Commission page mentions no public API. | Good source for an **HS6 reference list** (labels for the LLM prompt or lookup keys). Does not classify anything. |
| **EBTI** (binding tariff information) | Past classification decisions: goods description, CN code, reasoning, sometimes images | Web search form only ([EBTI home](https://ec.europa.eu/taxation_customs/dds2/ebti/ebti_home.jsp)). The Commission page mentions no bulk download or API ([EBTI page](https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/european-binding-tariff-information-ebti_en)). Third-party scrapers exist (e.g. an Apify actor). | Useful for **hand-building the lookup table** (precedents for tricky goods). Scraping it as training data is possible but has no official route. |
| **UK Trade Tariff API** (HMRC), incl. `/xi/` | JSON commodities, measures, search. The XI tariff follows the EU CN for Northern Ireland. | Free, no auth. Verified 2026-10-02: `GET https://www.trade-tariff.service.gov.uk/xi/api/v2/commodities/3926909790` returned JSON without a key. [Developer portal](https://trade-tariff.service.gov.uk/news/stories/uk-trade-tariff-developer-portal). | Easiest programmatic HS6/CN reference. Its `search` endpoint is keyword matching (a "phone case" query returned one exact-match subheading). **It does not classify.** |
| **Zonos Classify** | HS6 or country-specific code, confidence score, up to 5 alternates, rationale | API. Public pricing: 1,000 free classifications with a Zonos account. Paid tiers are annual subscriptions billed monthly, e.g. 10,000/month for 500 USD (0.05 USD each, overage 0.10 USD) ([pricing](https://zonos.com/docs/supply-chain/classify/pricing), [features](https://zonos.com/docs/supply-chain/classify/features)) | Cheap enough as the fallback if results are cached per product ID. Accuracy claims are disputed (see §2). |
| **Avalara, Descartes/3CE CustomsInfo** | Classification services | Quote-based, no public per-item price ([Avalara](https://www.avalara.com/eu/en/solutions/cross-border/item-classification-hs-commodity-codes.html)) | Enterprise sales motion. Poor fit for a no-account extension. |
| **WCO BACUDA AI-HS** | Open-source Doc2Vec HS6 recommender | [WCO news](https://bacuda.wcoomd.org/2022/03/03/wco-bacuda-experts-develop-a-neural-network-model-to-assist-classification-of-goods-in-hs/) | Only works well when trained on a large declaration corpus (see Azerbaijan, §2). |

For scale: HS 2022 has **5,612 six-digit subheadings** and 1,228 headings ([WCO](https://www.wcoomd.org/en/media/newsroom/2021/november/the-2022-edition-of-the-harmonized-system-nomenclature-is-now-available-online.aspx)).

## 2. Reported accuracy of automated HS classification

**Answer:** On real, noisy e-commerce product data, frontier LLMs get about 56–60% of HS6 codes exactly right and about 70% of HS4. Agents with web search reach about 60–62% HS6. Systems trained on very large in-domain sets of declaration data reach about 85% HS6. Vendor claims above 90% are either self-reported or measure something else. **Confidence: high** for the ranges (several independent primary sources agree). Applying them to Temu carts is an inference.

| Study | Data | HS4 | HS6 | Notes |
| --- | --- | --- | --- | --- |
| **HSCodeComp** (Alibaba Intl., [arXiv 2510.19631](https://arxiv.org/abs/2510.19631), ACL 2026) | 632 real listings from a large global e-commerce platform (title, attributes, images), expert-labelled (2% inter-expert disagreement) | GPT-5 VLM 70.9%; Gemini-2.5-Pro 71.0%; Claude Sonnet 4 64.1% | GPT-5 VLM **60.0%**; Gemini-2.5-Pro 59.0%; GPT-4o 48.1%; Claude Sonnet 4 45.3%; best agent (SmolAgents + GPT-5 + images) **62.4%** | Closest analogue to Temu listings. Humans scored 95% at 10-digit. **Caveat:** the set is filtered to remove near-duplicate easy products, so it is harder than a typical cart. Images help (+1–4 pts HS6). |
| **ATLAS** ([arXiv 2509.18400](https://arxiv.org/abs/2509.18400), NeurIPS 2025) | 200 US CROSS rulings (clean, expert-written descriptions) | n/a | Fine-tuned Llama-3.3-70B **57.5%**; GPT-5-Thinking 55.5%; Gemini-2.5-Pro 31.0% | Even with clean ruling text, top models get just under 60% of HS6. |
| **Spichakova & Haav 2020** ([BJMC](https://doi.org/10.22364/bjmc.2020.8.4.13)) | US bill-of-lading descriptions, Doc2Vec | n/a | **61%** top-1; true code in top 8 about 80% | Classical ML baseline. |
| **Azerbaijan Customs AI-HS** ([WCO news, Nov 2023](https://www.wcoomd.org/en/media/newsroom/2023/november/advanced-ai-hs-tool-developed-by-the-azerbaijan-customs.aspx)) | 1.6M national declaration records (BACUDA-based) | n/a | **~85%** (82% at 10-digit); >95% in 11 data-rich chapters | Shows what a large set of in-domain labels buys. The PRD has no such corpus. |
| **Tarifflo benchmark** ([arXiv 2412.14179](https://arxiv.org/abs/2412.14179)) | ~102 CROSS rulings, item name only | n/a | WCO BACUDA 12.75% (HS6) | 10-digit: Tarifflo 89.2%, Avalara (manual) 80%, Zonos 44.1%. **Author works at Tarifflo.** Treat as marketing. |
| **Zonos self-claim** ([zonos.com/classify](https://zonos.com/classify)) | n/a | n/a | "99%+" | This is a *"<1% of declarations get reclassified"* rate. It measures how often customs challenges a code, not whether the code is correct. Not comparable. |

What these numbers mean for the PRD:
- Every source shows the same pattern: accuracy falls as the code gets longer. HS2 is about 80%, HS4 about 70% and HS6 about 60% (HSCodeComp Table 1).
- The PRD needs **the right partition of the cart**, not the right code labels. Two wrong codes can still give the right line count. A rough calculation still shows how hard this is: with 60% per-item accuracy and independent errors, a 5-item cart has every item right only about 8% of the time (0.6^5). Being "within ±1 line" is more forgiving but still far from 90%.

## 3. What sellers and platforms actually declare for low-value consignments (PRD Q3)

**Answer:** Legally, an IOSS/H7 declaration carries a **6-digit HS code per line**. Each line costs €3 whatever the quantity, and grouping different subheadings onto one line is **barred** while the €3 applies. So Temu cannot legally declare "coarse buckets" broader than HS6. It can declare *finer*: an "item" is goods sharing classification **and description** (and origin, where declared), and the duty is charged per declaration line. No public source shows Temu's actual practice. **Confidence: high** on the legal mechanics, **low** on what is actually filed.

Primary sources (legal detail is owned by R1. This is a cross-check only, and it agrees with R1 on branch `research/legal-mechanics`):
- Reg. (EU) 2026/382, recital: the transitional €3 applies because "the tariff classification for the goods concerned in the customs declaration is only at the level of sub-headings of the Harmonised System" ([EUR-Lex](https://eur-lex.europa.eu/eli/reg/2026/382/oj/eng)).
- Delegated Reg. (EU) 2026/1022, new Art. 1(61) UCC-DA: "'item' means one or more goods in a consignment sharing the same tariff classification, description and, if provided …, origin" ([EUR-Lex](https://eur-lex.europa.eu/eli/reg_del/2026/1022/oj)).
- Commission guidance §3.3.1: H7 needs a "6-digit HS code"; H1 needs a 10-digit TARIC code plus origin. Amended Art. 228(1) UCC-IA means "the grouping of items is not allowed where the temporary EUR 3 customs duty applies". The duty "will automatically apply per declaration line irrespective of the quantity". Its own example puts three different suits on **one** H7 line (6104 19) but **three** H1 lines ([guidance PDF](https://taxation-customs.ec.europa.eu/document/download/053e5b4e-f0be-4f20-9a23-3e3b659a6676_en?filename=Customs%20Guidance%20on%20EUR%203%20customs%20duty.pdf)). **So which declaration type is used changes the count for the same cart.**
- Commission Q&A 1(c): operators "must be encouraged to use one line per goods sharing tariff classification in H7". That is encouragement, not obligation ([Q&A PDF](https://taxation-customs.ec.europa.eu/document/download/8350b1aa-935a-4b80-a349-385b36292fbe_en?filename=Questions%20and%20answers%20on%203%20EUR%20Guidance%20MS%20and%20Economic%20operators_clean15062026.pdf)).
- Douane.nl: "€ 3 per aangifteregel" (per declaration line). Example: 1 pencil + 1 bicycle bell = €6 ([Douane](https://www.douane.nl/onderwerpen/invoer-en-uitvoer/invoer/aangifte-doen/aangifte-doen-bij-e-commerce/invoerrechten-betalen-voor-e-commerce/)).

What the data shows about practice (indirect only):
- Douane NL monthly e-commerce figures ([Douane, 2026-09-01, updated 17-09](https://www.douane.nl/webwinkels-passen-werkwijze-aan-na-invoering-3-euroheffing/)) give these declaration lines per declaration (my division of their tables): Jan–Jun **3.2–3.6**, July **2.0**, August **1.7** (to 25 Aug), September about 2.0 (partial, chart). Douane describes lines as "het aantal verschillende productcategorieën in een zending".
  - Interpretation: before July, nothing rode on line count, and declarants averaged about 3.4 lines. The roughly 45% drop per declaration fits declarants **consolidating same-HS6 goods onto fewer lines** after July. It could equally come from buyers shrinking mixed baskets, mixed baskets moving to EU stock, or coarser coding. **Public data cannot separate these causes.**
- Temu's own UI (single secondary source, German store, Sept 2026, [RefundRadar](https://refundradar.co/blog/temu-eu-import-fees/), also cited by R2):
  - Import charges are shown as a separate checkout line.
  - A green tag, **"No import charges with current cart"**, appears on an item sharing an HS category with another cart item.
  - Some carts show a **"Discover more items without additional import charges"** page that lists items in the same tariff class.
  - So Temu runs a per-product classification at cart time and exposes part of the partition. **Unverified for the NL store.**
- From 1 Nov 2026, product identifiers become mandatory per item in e-commerce declarations ([Douane news](https://www.douane.nl/vanaf-1-november-productidentificatie-verplicht-in-aangifte-e-commerce/); guidance §3.5.6). Customs will then get better data to challenge misclassification. Over time this should pull declared codes toward true HS6.

---

## PRD claims checked

| PRD assumption | Verdict | Reason |
| --- | --- | --- |
| Tariff-line key may be "HS6 **or a coarser internal bucket**" (F3; Technical approach; Q3) | **Doubtful** (coarser) / **Plausible** (HS6) | Grouping across subheadings is legally barred under the €3 (Art. 228(1) IA as amended), so declared lines are HS6 or finer. A coarser bucket would systematically undercount. |
| "Lookup table: Temu category path → tariff-line key … top ~300 Temu categories" | **Doubtful** | Category to HS6 is often one-to-many. HS6 splits by material and construction (e.g. knitted 61xx vs woven 62xx, cotton vs synthetic, plastic 3926 vs leather 4202 cases), which category paths usually don't encode. HS has 5,612 subheadings. Workable only for categories that map to a single HS6, with material read from the listing. |
| "This covers most carts with no network call" | **Unverified** | No public data on how Temu NL carts spread across categories. Coverage (a key exists) is not the same as correctness (the key matches Temu's). |
| "Fallback: LLM prompt over an HS6 reference" | **Plausible** to build, **Doubtful** on accuracy | Easy to build: HS6 reference is free (CIRCABC/TARIC Excel, UK XI API); Zonos costs about $0.05/item. Expected accuracy is only about 56–62% HS6 on noisy listings (HSCodeComp, ATLAS). Fine as a low-confidence fallback, not as a source of trusted lines. |
| "Confidence is returned with the result" | **Plausible** | Zonos returns confidence plus alternates. LLMs can give alternatives. Calibration is unproven in the sources above. |
| "Match Temu's checkout total within €3 on ≥90% of carts" / "ship only when test-set accuracy ≥ 90%" | **Doubtful** | Published per-item HS6 accuracy is about 60% (about 85% only with millions of in-domain labels). Per-cart correctness compounds over items. From about Nov 2026 the €2/item handling fee (R1) makes each line cost about €5, so "within €3" becomes "exact line count". Only realistic if the extension reads Temu's own signals (cart tag, checkout charge) or learns Temu's per-product assignments through feedback. |
| "The tariff-line key deliberately follows … the declared tariff heading, not the true HS6" | **Plausible** (and key) | Correct framing, and stronger than the PRD treats it. The ground truth is Temu's own classifier, whose output Temu partly shows in the cart (if the DE observation holds in NL). |
| Feedback loop corrects the lookup table weekly | **Plausible**, weak signal | A reported total duty only gives a line *count*, not which items were grouped together. The per-item Temu tag would be a far richer label. |

## What threatens the PRD

1. **Temu may already show the grouping** ("No import charges with current cart", the same-tariff-class page). If so, the "which item shares a line" insight is partly built in. The extension's unique value shrinks to "which removal saves the most", and classification should come from Temu's DOM rather than a model. Verify on the NL store as part of the Q1 test orders.
2. **The ≥90% bar is not reachable with title-and-category classification alone**, based on every independent benchmark found.
3. **The declaration type and line-splitting are invisible to the buyer** (H7 vs H1, splitting by description), so even a perfect HS6 classifier can be off by declarant behaviour.

## Suggested next checks (not done here)

- On the NL test orders (PRD Q1–Q4): look for the "No import charges with current cart" tag and the same-tariff-class page. Record which item pairs Temu groups.
- Score a cheap LLM and Zonos's free tier on about 50 real Temu NL cart items, using Temu's own grouping as ground truth.

## Sources

- Council Regulation (EU) 2026/382: https://eur-lex.europa.eu/eli/reg/2026/382/oj/eng
- Delegated Regulation (EU) 2026/1022: https://eur-lex.europa.eu/eli/reg_del/2026/1022/oj
- Commission guidance on the EUR 3 duty (PDF): https://taxation-customs.ec.europa.eu/document/download/053e5b4e-f0be-4f20-9a23-3e3b659a6676_en?filename=Customs%20Guidance%20on%20EUR%203%20customs%20duty.pdf
- Commission Q&A (30.6.2026, PDF): https://taxation-customs.ec.europa.eu/document/download/8350b1aa-935a-4b80-a349-385b36292fbe_en?filename=Questions%20and%20answers%20on%203%20EUR%20Guidance%20MS%20and%20Economic%20operators_clean15062026.pdf
- Douane NL, €3 rules: https://www.douane.nl/onderwerpen/invoer-en-uitvoer/invoer/aangifte-doen/aangifte-doen-bij-e-commerce/invoerrechten-betalen-voor-e-commerce/
- Douane NL, declaration statistics: https://www.douane.nl/webwinkels-passen-werkwijze-aan-na-invoering-3-euroheffing/
- Douane NL, PID requirement: https://www.douane.nl/vanaf-1-november-productidentificatie-verplicht-in-aangifte-e-commerce/
- TARIC: https://taxation-customs.ec.europa.eu/customs/common-customs-tariff-cct/tariff-classification-goods/eu-customs-tariff-taric_en · CIRCABC: https://circabc.europa.eu/w/browse/0e5f18c2-4b2f-42e9-aed4-dfe50ae1263b
- EBTI: https://taxation-customs.ec.europa.eu/online-services/online-services-and-databases-customs/european-binding-tariff-information-ebti_en
- UK Trade Tariff developer portal: https://trade-tariff.service.gov.uk/news/stories/uk-trade-tariff-developer-portal
- WCO HS 2022 edition: https://www.wcoomd.org/en/media/newsroom/2021/november/the-2022-edition-of-the-harmonized-system-nomenclature-is-now-available-online.aspx
- HSCodeComp: https://arxiv.org/abs/2510.19631
- ATLAS: https://arxiv.org/abs/2509.18400
- Spichakova & Haav 2020: https://doi.org/10.22364/bjmc.2020.8.4.13
- Tarifflo benchmark (Judy): https://arxiv.org/abs/2412.14179
- WCO, Azerbaijan AI-HS: https://www.wcoomd.org/en/media/newsroom/2023/november/advanced-ai-hs-tool-developed-by-the-azerbaijan-customs.aspx
- WCO BACUDA HS model: https://bacuda.wcoomd.org/2022/03/03/wco-bacuda-experts-develop-a-neural-network-model-to-assist-classification-of-goods-in-hs/
- Zonos Classify: https://zonos.com/classify · pricing: https://zonos.com/docs/supply-chain/classify/pricing
- Avalara item classification: https://www.avalara.com/eu/en/solutions/cross-border/item-classification-hs-commodity-codes.html
- RefundRadar (secondary; Temu DE checkout observations): https://refundradar.co/blog/temu-eu-import-fees/
