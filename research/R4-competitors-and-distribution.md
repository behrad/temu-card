# R4: Existing tools, Temu ToS, and Chrome Web Store risk

Ticket: `wayfinder/tickets/R4-competitors-and-distribution.md`. Answers PRD Q10.
Researched 2026-10-02. Chrome Web Store (CWS) figures were read from the live listing pages that day.

## Headline

The Phase 1 niche (a per-tariff-line "what to remove" panel on the Temu cart) is **open**. No CWS extension or web tool does it today. The adjacent "group order to share the €3" idea is **already live in Cyprus** (GroupShip EU, which has its own Temu-cart-reading extension).

Distribution through the CWS is **feasible**. CWS policy does not enforce third-party site terms, and it already hosts many Temu DOM-reading extensions, including openly named "Temu Scraper" tools.

Temu's EU Terms of Use **do technically prohibit** using "manual or automated software" to "scrape" any page. The remedies fall on the *user's Temu account*. I found no instance of Temu acting against any extension.

The PRD's Phase 2 plan to **monetize through the Temu affiliate program is effectively barred**: Temu's Affiliate Policy forbids using referral links in any browser extension unless Temu approves it.

---

## Sub-question 1: Is the space open? (existing tools)

**Answer:** Yes for Phase 1, with low barriers to entry.
- Every EU €3 calculator I found is either a manual web form (you enter the value and the number of categories) or a product-page landed-cost estimator.
- None reads the Temu cart, groups items by tariff line, or computes the marginal saving of removing each item.
- The closest tools are:
  - **GroupShip EU** (Cyprus): group-import pooling of the €3 per HS6 line, with a read-only Temu cart exporter extension. This is the PRD's Phase 2 "group cart" idea, already shipped by someone else.
  - **Temu+ Lite**: reads the user's own Temu account to track real cost and refunds.
- All direct competitors have tiny install bases (4 to 40 users). The largest Temu helpers are coupon and price trackers, in the low thousands of users.

**Confidence: medium-high.** The CWS search covered "temu", "temu duty", "temu customs", "temu cart", "customs duty calculator", "import duty", "eu customs", "douane", "invoerrechten", "shein" and "aliexpress customs". I did not search Firefox/Edge stores or mobile apps exhaustively.

### Competing and adjacent tools

| Tool | Type | What it does | Overlap with Phase 1 | Users / updated | Source |
| --- | --- | --- | --- | --- | --- |
| GroupShip Temu Cart Exporter + GroupShip EU | CWS extension + web app | Reads your own Temu cart (read-only, `activeTab` + `scripting`, host `www.temu.com` only) into a group-import tool that pools the €3 per HS6 line; €0.69 per member; "Live beta in Cyprus" | **High for Phase 2** (group carts); medium for Phase 1 (reads cart, but no per-item removal advice) | 6 users; 2026-07-28 | [CWS](https://chromewebstore.google.com/detail/pgolcanlocpmnnnjmcdahodphfhjmeph), [web app](https://groupship-eu.netlify.app) |
| Temu+ Lite · Real Cost & Refund Tracker | CWS extension | Reads the user's own Temu order/credit history locally; real cost per item after refunds. Listing carries a "Not affiliated with … Temu or PDD Holdings" disclaimer | Low (post-purchase), but same "reads your own Temu account" pattern, accepted by CWS | 37 users; 2026-10-02 | [CWS](https://chromewebstore.google.com/detail/iehnodlgkoimdohpcjjlhhfehblcfaea) |
| EU Import Cost Calculator ("Dutix") | CWS extension | Scrapes the price on any shopping product page and adds EU VAT, duty and handling. Duty only above €150; no €3 per-line logic stated | Low to medium (product page, not cart) | 4 users; 2026-07-31 | [CWS](https://chromewebstore.google.com/detail/plfmghlhlbomphbjjkiddmfmkcjhapbd) |
| EU Tariff & Landed Cost Calculator | CWS extension (popup) | Manual: enter value, number of HS6 categories and country to get €3 × categories plus VAT. Aimed at sellers; freemium | Low (manual, seller-oriented) | not shown; 2026-08-07 | [CWS](https://chromewebstore.google.com/detail/bjbkfhccmdolchjlpddkpkgdllcckigp) |
| AliExpress Tariffs (AliTariffs) | CWS extension | Landed cost (duty + VAT) on AliExpress product pages, 30+ countries; listing says "Auto-applies affiliate links" | Low (AliExpress, product page) | 82 users; 2026-05-18 | [CWS](https://chromewebstore.google.com/detail/mpbpjlpehhlhpnnhnahjkheccgdnhngj) |
| AliExpress Landed Cost & Profit Radar | CWS extension | Landed cost and margin for dropshippers on AliExpress | Low | 2026-08-06 | [CWS](https://chromewebstore.google.com/detail/egobolgimnedlhalmpglmaodggpddjhc) |
| Tariff Lens | CWS extension | US (Trump) tariff impact on Amazon, eBay, Temu, AliExpress and Etsy product pages | Low (US tariffs) | 63 users; 2025-09-09 | [CWS](https://chromewebstore.google.com/detail/bennafndpodmnmifmagklpbmbnffphgb) |
| euparcelfee.com | Web calculator | Manual: country + declared value; €3 per category + VAT; no item grouping, no cart import | Low | n/a | [site](https://euparcelfee.com/en/platform/temu) |
| whatduty.com, calcforlife, berekenen.org, tariffdutycalculator.com | Web calculators / articles | Manual duty/VAT calculators, some with NL pages | Low | n/a | [whatduty](https://www.whatduty.com/nl/temu-invoerrechten-nederland), [calcforlife](https://calcforlife.com/nl/invoerrechten-berekenen/), [tariffdutycalculator](https://tariffdutycalculator.com/ecommerce-import-tools/shein-temu-duty-calculator/) |
| RefundRadar | iOS/Android app | Monitors Temu orders and files price-adjustment claims | None (adjacent: Temu money-saving) | n/a | [blog](https://refundradar.co/blog/temu-eu-import-fees/) |
| Seller Price & Coupon Monitor (AliPrice; slug still `temu-price-tracker`) | CWS extension | Coupons, 6-month price history, similar-product search. **Rebranded away from "Temu" in its name** (reason unknown) | None | 8,000 users; 2026-08-27 | [CWS](https://chromewebstore.google.com/detail/hjabehanjpcmfhnjmjogpdddcaceimda) |
| Temu Coupon Finder | CWS extension | On Temu checkout, finds and auto-tests coupons on click | None (checkout DOM access precedent) | 1,000 users; 2025-11-26 | [CWS](https://chromewebstore.google.com/detail/debdpihbfklmfbhbdkonjggeocffcoog) |
| TEMU Hide Local Products | CWS extension | Hides EU-local-warehouse items on Temu (offered in Dutch) | None, but shows demand for steering local versus global stock | 2,000 users; 2026-02-13 | [CWS](https://chromewebstore.google.com/detail/eahpdbpdonhoddncfbodpjaegkhcfalc) |
| TonyCartoni, Price Watcher, Temu Price Comparison, Temu Product Finder | CWS extensions | Price tracking and comparison including Temu | None | 81 to 801 users | e.g. [TonyCartoni](https://chromewebstore.google.com/detail/mgklglclddhigaecelkobgdafamdcbai) |
| T-Bargain Scraper, Temu Extractor, Temu Scraper 2.0 | CWS extensions | Openly market scraping Temu products, **cart items** and order history to CSV | None (precedent only) | 793 / 263 / 109 users | [T-Bargain](https://chromewebstore.google.com/detail/adbaegbhiiibfaopbdpbbomfgcffdmmh), [Extractor](https://chromewebstore.google.com/detail/nbmpkondglocgmhlhbainabeocjjjlbe), [Scraper 2.0](https://chromewebstore.google.com/detail/fgjgbfbnohpgcbjkmlilpbfkdhcdlomn) |

I found no Shein-specific duty helper. The Shein CWS results are image-search and image-download tools.

---

## Sub-question 2: Temu Terms of Use (NL/EU) on extensions, scraping and affiliates

**Answer:**

**Contract.** The NL Terms of Use are between the user and Whaleco Technology Limited (Dublin), effective 19 April 2026. They are governed by the law of the user's EU country of residence.

**Scraping clause.** §3.5 forbids "use of manual or automated software or other means to access, 'crawl,' 'scrape,' or 'spider' any page, data, or portion of or relating to the Services" (item 12). It also forbids copying or storing "any significant portion" of content without consent (item 13), and assisting a third party to do either (item 17).
- The terms never mention browser extensions explicitly.
- Read literally, item 12 is broad enough to cover a content script that reads the cart page.
- The stated remedies hit the **user**: removal of submissions, cancelled purchases, cancelled Rewards, and account suspension.

**Licence.** §10.4 grants a "personal and non-commercial" licence to use the Services.

**Affiliate Policy.** This is a "Policy" under the Terms of Use, last updated 9 Feb 2026. The archived EU copy is the Germany-resident version, and the NL site has an Affiliate and Influencer Program entry page.
- Clause (ix) forbids using referral links or codes, or anything associated with the Program, "on or in connection with any client-side software application (e.g., a browser plug-in, helper object, toolbar, extension … except for those approved by Temu".
- Clause (x) forbids reading or interpreting "the contents of any electronic form or other material submitted to Temu".
- Plugin-generated traffic is listed as invalid traffic.

**Precedents.**
- I found **no** case of Temu suing, sending a takedown to, or technically blocking a browser extension.
- Temu's known litigation targets cybersquatting domains and fake apps (trademark), e.g. temuh.com and temumore.com (N.D. Ill., 2024).
- Temu does run an active bot challenge: plain HTTP fetches of temu.com get a JS challenge page. That defends against server-side scraping, not a content script reading an already-rendered page.

**Confidence: high** on the clause text (read from the archived NL-EN page, 30 Aug 2026 capture). **Medium** on "no enforcement precedent", since absence of evidence comes from web search only.

**Sources:**
- [Temu NL Terms of Use, archived 2026-08-30](http://web.archive.org/web/20260830153807/https://www.temu.com/nl-en/terms-of-use.html). Live URL: https://www.temu.com/nl-en/terms-of-use.html, which serves a bot challenge to non-browsers.
- [Temu Affiliate Policy, archived 2026-03-03](http://web.archive.org/web/20260303103632/https://www.temu.com/affiliate_policy.html)
- [Temu NL affiliate/influencer entry page, archived 2026-08-30](http://web.archive.org/web/20260830153807/https://www.temu.com/nl-en/affiliate_influencer_program.html)
- [Temu cybersquatting/fake-app lawsuit, Domain Name Wire, 2024](https://domainnamewire.com/2024/03/13/temu-fights-back-against-cybersquatters-and-unauthorized-apps-with-federal-lawsuit/) (secondary)

**Side finding for other tickets.** ToS §13.2 says Temu estimates "Import Fees" at checkout, may take an **Import Fee deposit**, never charges more than the deposit, and **automatically refunds** any overestimate once carrier invoices arrive. So the "actual charge" a user can report (F11) is the deposit minus a later refund, not a single checkout number.

---

## Sub-question 3: Chrome Web Store policy and precedents

**Answer:** No CWS policy objects to a read-only extension that reads a shopping site's DOM. The relevant constraints are below.

1. **Single purpose.** The policy says "a single purpose that is narrow and easy to understand". The duty panel fits.
2. **User data.** Cart titles and categories are "website content" and "user activity" data. They need:
   - an accurate privacy policy;
   - privacy-practices disclosures;
   - Limited Use compliance, meaning data goes to third parties only when "necessary to providing or improving your single purpose".

   The PRD's design (titles to the classifier only for unmapped items, anonymous feedback) fits this, provided both are declared.
3. **Remote code.** MV3 forbids remotely hosted executable logic, but "external resources may provide data". A remotely updated **JSON selector config is allowed**, as long as it stays data (no eval and no injected functions).
4. **Affiliate Ads policy** (updated 2025-03-11, enforced from 2025-06-10 after the PayPal Honey scandal). Affiliate use must:
   - be disclosed on the listing, in the UI, and before install;
   - give a direct user benefit;
   - require a related user action for **each** link, code or cookie.
5. **Impersonation / IP.** You must not imply endorsement by another company. Many listings use "Temu" in the name, and Temu+ Lite adds an explicit non-affiliation disclaimer. AliPrice dropped "Temu" from its 8,000-user tracker's name; the reason is unknown.
6. **EU trader status.** Since Feb 2024 every developer declares trader or non-trader status. Traders have their legal name and contact details shown publicly. Monetizing later would likely make the publisher a trader.

**Precedents.**
- The CWS currently hosts ≥ 15 Temu DOM-reading extensions, including ones that advertise scraping "cart items" and checkout coupon testers. The store does **not** police third-party site ToS.
- The documented CWS enforcement in this space is about **affiliate injection** (the Honey policy), not DOM reading. Honey itself was not removed.
- US analogue: in Amazon v. Perplexity (Comet), a district court enjoined the agentic browser in March 2026. The **Ninth Circuit vacated the injunction on 5 Aug 2026**, finding the tool acts on the user's instructions and Perplexity "itself did not access Amazon's computer systems". This is US CFAA law, persuasive at most, and concerns a far more invasive tool (logged-in automation).

**Confidence: high** on policy text (primary). **Medium** on the precedents (listing observations are primary; the court outcome comes from secondary news).

**Sources:**
- [CWS Program Policies (updated 2025-05-22)](https://developer.chrome.com/docs/webstore/program-policies/policies)
- [CWS Affiliate Ads policy (updated 2025-03-11)](https://developer.chrome.com/docs/webstore/program-policies/affiliate-ads)
- [CWS Limited Use](https://developer.chrome.com/docs/webstore/program-policies/limited-use)
- [CWS trader disclosure](https://developer.chrome.com/docs/webstore/program-policies/trader-disclosure)
- [9to5Google on the Honey-driven policy change](https://9to5google.com/2025/03/11/google-chrome-affiliate-extension-policy-honey/) (secondary)
- [GeekWire on the March 2026 injunction](https://www.geekwire.com/2026/judge-blocks-perplexitys-ai-bot-from-shopping-on-amazon-in-early-test-of-agentic-commerce/) (secondary)
- [Retail Insight Network on the 9th Cir. vacatur](https://www.retail-insight-network.com/news/us-court-overturns-amazon-injunction-perplexity/) (secondary)

---

## PRD claims checked

| PRD claim / assumption | Verdict | Reason |
| --- | --- | --- |
| Q10 premise: Temu ToS and CWS policy may object to a cart-reading extension | **Partly confirmed** | CWS: no objection. Temu ToS §3.5(12) literally bans "manual or automated software" to "scrape" any page. The risk is to users' accounts; no enforcement precedent found. |
| Risks table: "Temu blocks or throttles the extension: Low" | **Unverified, plausibly right** | No precedent against any of the ≥ 15 Temu extensions, including open scrapers. The ToS gives Temu the contractual right, and an injected side panel is visible to Temu's page scripts. Using Chrome's `sidePanel` API instead of in-page DOM injection would reduce detectability. |
| Mitigation: "Read-only DOM access, no automation, no scraping beyond the user's own cart" | **Confirmed as best practice, not a ToS safe harbour** | It matches the GroupShip and Temu+ Lite pattern accepted by the CWS, but ToS item 12 says "manual … or other means", so read-only does not take it outside the clause. |
| "Requests host permission for temu.com only" | **Confirmed feasible** | GroupShip ships with just `https://www.temu.com/*`. Calls to your own classifier and feedback API work without extra host permissions if that API sends CORS headers. NL storefront paths sit under `www.temu.com/nl…`. |
| "Selectors live in a remotely updatable JSON config" | **Confirmed** | MV3 policy allows remote *data*, not remote *logic*; keep the config declarative. |
| "No cart contents leave the browser except item title+category for unmapped items and the optional feedback" | **Confirmed compatible, needs disclosure** | This counts as user data under the CWS; it needs a privacy policy, privacy-practices declarations and a Limited Use statement. |
| Distribution: "Chrome Web Store, unlisted at first" | **Confirmed** | Unlisted items still go through normal review and policies; nothing here blocks approval. |
| Problem statement: the "why, and what can I remove" gap is unserved | **Confirmed** | No tool found does per-tariff-line grouping or a marginal-removal saving on the Temu cart. |
| Phase 2: "Shareable cart link / group carts" is a future differentiator | **Wrong as a differentiator** | GroupShip EU already does group pooling of the €3 per HS6 line with a Temu cart reader (live in Cyprus, waitlist for other EU countries). |
| Phase 2: "Affiliate monetization via the Temu affiliate program" | **Wrong** | Temu Affiliate Policy (ix) bans referral links in any browser extension "except for those approved by Temu"; plugin traffic is invalid. The CWS Affiliate Ads policy adds disclosure and per-action consent requirements. |
| Product name "Temu Cart Optimizer" | **Unverified risk** | Using Temu's trademark in the title risks CWS impersonation review and a Temu trademark complaint. Safer: "Cart duty helper for Temu" plus a non-affiliation disclaimer, as Temu+ Lite does. |
| F11 "actual duty charged" | **Needs rework (side finding)** | ToS §13.2: Temu takes an Import Fee deposit and auto-refunds any overestimate later, so the actual charge appears only after the refund. |

## Open items not resolved here

- Whether Temu's anti-bot scripts detect content-script DOM injection on the cart page. Testing needs a real logged-in session; a local repro is the only safe way.
- The Dutch-language (`/nl/`) Terms of Use were not compared clause by clause. The NL-EN version is the one served to NL English users.
- I did not re-read the CJEU *Ryanair v PR Aviation* (C-30/14, 2015) ruling, which held that site terms can contractually restrict use of unprotected data. It is relevant if Temu ever enforces item 12 against a user in the EU.
