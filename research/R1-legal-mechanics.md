# R1: Legal mechanics of the €3 duty and €2 handling fee

Ticket: `wayfinder/tickets/R1-legal-mechanics.md` · Researched 2026-10-02 · Sources are primary unless marked *(secondary)*.

## TL;DR

- **One "item" is one declaration line**: goods in one consignment that share the same tariff classification, the same description and (where declared) the same origin. The classification level depends on which declaration is filed: **HS6 in H7** (the IOSS super-reduced declaration Temu-type flows use), CN8 in H6, TARIC10 plus origin in H1. Quantity on a line doesn't matter. Identical goods put on separate lines pay twice.
- It is counted **per consignment**, and each consignment has its own declaration. It is **not counted per order**: one order shipped in two parcels is two consignments.
- **€150 is the "intrinsic value" of the consignment**: the net price actually paid (after discounts), excluding transport/insurance *if shown separately* on the invoice, excluding VAT. Above €150 the €3 regime stops, IOSS can't be used, and normal ad-valorem duty plus import VAT are collected at the border.
- **IOSS and non-IOSS both pay €3** for distance sales ≤ €150. The one exception is non-IOSS goods that claim a preferential tariff in an H1 declaration. The **legal debtor is the declarant**: the IOSS holder (i.e. the platform as deemed supplier) or its indirect representative, usually the carrier/broker. The consumer pays only economically, and is never the debtor under IOSS.
- **The €2 handling fee is set but not yet in force.** Its legal basis is adopted (Reg. (EU) 2026/2108, Art. 20(2)). The amount is set by Commission Delegated Regulation C(2026) 6694 of 21.9.2026 at **€2 per item, not per consignment**. It is under a 30-day Parliament/Council objection period. It applies 10 days after OJ publication, and "1 Nov 2026" is the target, not a fixed legal date. It is **uniform EU-wide**, applies to **all distance sales regardless of value** (also above €150), is **outside VAT** at import, and is non-refundable. **The Netherlands decided on 12 June 2026 not to add a national handling fee.**

---

## 1. What is one "item" for the €3? — Confidence: **high**

**Legal chain**

- Council Regulation (EU) 2026/382 of 11 Feb 2026, Art. 2: *"From 1 July 2026 until 1 July 2028, a customs duty of EUR 3 per item in a consignment the intrinsic value of which does not exceed a total of EUR 150 shall apply…"*. It does not define "item" itself. Recital 7 notes that e-commerce declarations classify only "at the level of sub-headings of the Harmonised System" (= HS6).
- Commission Delegated Regulation (EU) 2026/1022 (OJ 1.7.2026) adds Art. 1(61) to Delegated Reg. 2015/2446: *"'item' means one or more goods in a consignment sharing the same tariff classification, description and, if provided in accordance with the data requirements applicable to the relevant customs declaration […], origin."* Recital 4: *"This also occurs when two or more identical items are declared on separate lines in a declaration, although it is allowed to group these identical items and declare them in one line."* The same definition is in the new UCC, Reg. (EU) 2026/2108, Art. 5.
- Commission Implementing Regulation (EU) 2026/1200 (OJ 8.6.2026): Art. 222 IA says each item = a separate declaration. Art. 228(1) IA as amended **forbids** the usual "group everything under the highest-duty subheading" simplification when the €3 applies.

**Commission guidance (non-binding but authoritative)**, *Guidance for Member States and Trade*, version 2 June 2026, §3.3.1:

- *"the EUR 3 customs duty will automatically apply per declaration line irrespective of the quantity (number of the articles) in that declaration line"*
- Classification level by dataset: **H1 = 10-digit TARIC + origin; H6 = CN8; H7 = 6-digit HS**. Worked example: three different women's suits (different fibres) under HS 6104 19 cost **€3 once in H7 and H6**, but **€9 in H1**, because H1 splits them into three TARIC codes.
- Q&A (30.6.2026) item 1c: operators are "encouraged to use one line per goods sharing tariff classification in H7".
- Douane.nl puts it as: "per soort product … € 3 per aangifteregel". Example: 1 pencil + 1 bicycle bell = €6; a box of pencils = €3.

**What this means for a Temu cart**

- For IOSS consignments declared in H7, the minimum count is the **number of distinct HS6 subheadings in the consignment**. It cannot legally be coarser: one line carries one classification, and grouping across subheadings is barred.
- It can be **finer**, if the declarant splits same-HS6 goods into separate lines (different descriptions, or simply separate lines). That is the declarant's choice and is invisible to the buyer. **Q3 and Q4 still need the empirical test-order check.**
- Variants (size/colour) of the same product share HS6 and can legally be one item. Product identifiers (mandatory from 1 Nov 2026) don't force a split: the guidance (§3.5.6) says that where "an item includes several products", each product's PID is listed under that one item.

## 2. Per consignment, per order or per declaration? — Confidence: **high**

- The duty is **per item per consignment** (Art. 2, Reg. 2026/382). In practice the declaration *is* the consignment's declaration: the Q&A (1d) says orders of two consumers "must always be … declared in two different customs declarations".
- "Consignment" = goods from one consignor to one consignee, same transport contract (Guidance §3.3.1). **"Goods covered by the one order placed by the same person, but dispatched separately, should be considered as separate consignments."** Separate orders shipped together form a single consignment.
- On a marketplace, each underlying seller's part of an order is normally a separate supply and a separate consignment (VAT e-commerce Explanatory Notes, Q22–23).
- **Implication:** cart-level "€3 × distinct lines" is right only if the whole cart ships as one parcel. If Temu splits an order (by seller or warehouse), a category that appears in two parcels is charged twice. This is the legal side of Q2. The empirical side (does Temu split?) still needs test orders.

## 3. How is €150 valued, and what happens just above it? — Confidence: **high** (valuation) / **medium** (above-threshold cost)

- The threshold is the **intrinsic value** (Art. 1(48) UCC-DA, quoted in Guidance §3.3.1): "the price of the goods themselves when sold for export … excluding transport and insurance costs, unless they are included in the price and not separately indicated on the invoice, and any other taxes and charges".
- **Discounts:** the intrinsic value is *"the net price paid by the customer at the time of supply"* (VAT e-commerce Explanatory Notes, Q20). So **net, after discounts/coupons, excluding VAT, excluding separately-stated shipping.**
- The €3 itself is a specific duty: it does not depend on price, and no customs value is computed (Guidance §3.2.3). So Q5's "is the €3 applied before or after discounts" is moot. Only the €150 test uses price, and it uses net price.
- **Just above €150 for a consignment:**
  - IOSS can't be used, so import VAT is collected at the border, typically by the carrier from the buyer. The €3 regime doesn't apply, so the **normal Common Customs Tariff** applies on the customs value. Customs value, unlike intrinsic value, includes transport/insurance to the EU border.
  - This is a cliff, but not necessarily a more expensive one: duty can be lower or higher than €3/item depending on rates.
  - From Nov 2026 the €2/item handling fee **still applies** above €150 (see §5).
  - Consignments above €150 can't use the H7 declaration.
- *Undervaluation:* customs may reassess. If the corrected value exceeds €150, the buyer may face VAT and duty at import (Explanatory Notes Q18).

## 4. IOSS vs non-IOSS; who declares and pays? — Confidence: **high**

- **Scope** (Art. 2 Reg. 2026/382, plus the redefined "goods in postal consignment" in Art. 1(24) DR 2026/1022). The €3 applies to all distance sales ≤ €150:
  - (a) IOSS imports (VAT-exempt under Art. 143(1)(ca) VAT Directive);
  - (b) non-IOSS distance sales ≤ €150 (special arrangements or standard VAT), **except goods claiming a preferential rate**, which must use H1 (Guidance §3.3.2–3.3.3).
  - All IOSS goods pay €3 regardless of preference. For China-origin goods, preferences rarely apply. *(Inference: China is not a GSP beneficiary, and this was not verified per product.)*
- **Where declared:** IOSS goods can be declared in any Member State. Non-IOSS ≤ €150 must be declared in the Member State of destination (Art. 221(4) IA as amended).
- **Who declares (cascade, Guidance §3.4.3):**
  - (a) IOSS holder or its indirect representative;
  - (b) special-arrangements user (in practice the postal operator/carrier) or its indirect rep;
  - (c) indirect representative of the importer, normally found by the carrier;
  - (d) the consumer, only where a Member State offers a free online declaration, and never with an IOSS number.
- **Who pays:** the declarant is the main debtor (Art. 77(3) UCC); with indirect representation, the represented person is also a debtor. DR 2026/1022 recital 10: responsibility lies "first and foremost … with the declarant, i.e. the platforms and sellers, or with the carrier or agent". For a Temu IOSS order the **legal** payer is Temu (deemed supplier/IOSS holder) or its customs agent. The buyer pays only if Temu passes it through in the price.
- **VAT on the €3** (Commission VAT addendum, rev. 21.8.2026):
  - Under IOSS, the €3 is *not* in the VAT base, **unless it is charged to the consumer at the moment of sale, in which case it is part of the consideration and VAT applies** (21% in NL → about €3.63 per item if passed through as a charge).
  - Under special arrangements or standard VAT, the €3 is always in the import-VAT base.
- **Returns:** the €3 is no longer refundable by invalidating the declaration (Art. 148(3) DA amended, Guidance §3.4.7).

## 5. The €2 handling fee — Confidence: **high** (basis, unit, uniformity, NL) / **medium** (exact start date)

- **Adopted? The legal basis is adopted; the amount is adopted but not yet in force.**
  - Regulation (EU) 2026/2108 (new Union Customs Code), adopted 16 Sept 2026, OJ 19.9.2026, Art. 20(2): customs "shall collect a Union handling fee of a fixed amount per item" for release of goods sold in distance sales.
  - Art. 287(4): it applies "from 10 days after the entry into force of the delegated act".
  - Commission Delegated Regulation C(2026) 6694 final of 21.9.2026, Art. 1: *"The amount of the Union handling fee … shall be EUR 2 per item."* It was transmitted to the Council on 22.9.2026 (ST 13480/26).
  - First-act objection period: **30 days** (Art. 282(7)), i.e. to about 21–22 Oct 2026 unless both institutions waive it earlier. After that comes OJ publication: the act enters into force on publication and applies 10 days later.
  - So **"1 Nov 2026" is a target** used by the Dutch government and the Commission ("November 2026 at the earliest"), **not a fixed legal date**. Verify OJ publication in late October.
- **Unit:** **per item.** It uses the same "item" definition as the €3 (Reg. 2026/2108 Art. 5). It is **not per consignment.**
- **Scope:** all distance sales, **with no €150 cap**. The explanatory memorandum says distance sales above €150 "are also subject to the handling fee". A lower fee for goods sold from customs warehouses for distance sales applies only from 1 July 2028, and its amount is not yet set.
- **Varies by Member State?** **No.** It is a single Union amount, collected by the customs authority competent for release (Art. 20(5)). Member States may still charge for *other* specific services (out-of-hours attendance, analyses, exceptional controls: Art. 20(9)).
- **Debtor:** the debtor of the customs debt, i.e. the declarant/IOSS holder or indirect rep. Recital: "the consumer should not be a debtor". It is paid monthly at minimum and is **non-refundable** (Art. 20(6)).
- **VAT:** it is outside the scope of VAT and not in the import-VAT base (VAT addendum, 21.8.2026). Whether VAT applies if Temu re-charges it to the buyer at sale is **not addressed**. By analogy with the €3 reasoning it plausibly would *(low confidence, inference)*.
- **NL national fees on top:** **none.** Kamerbrief of 12 June 2026 (Kamerstukken II 31 934, nr. 113): the cabinet decided **not** to introduce a national *handelingskostenvergoeding* and relies on the Union fee. Douane.nl (updated 22.9.2026) lists no national fee. France has had a national fee since 1 March 2026 (cited in the same Kamerbrief). Carriers' private clearance charges (e.g. for non-IOSS parcels) are commercial, not legal fees, and were not researched.
- **Combined effect per item (IOSS, ≤ €150, from about Nov 2026):** €3 duty + €2 fee = **€5 per declaration line**, plus VAT on the €3 (and possibly the €2) if Temu itemises them as charges at checkout.

## Watch items (could change the rules mid-project)

- **Art. 3(1) Reg. 2026/382:** from **1 Oct 2026, monthly**, the Commission assesses diversion away from IOSS and may propose extending the €3 to *all* goods ≤ €150. No proposal was found as of 2 Oct 2026 (unverified absence).
- **Art. 3(2):** by 1 Dec 2027 the Commission may propose extending the €3 regime beyond 1 July 2028 if the EU Customs Data Hub isn't ready.
- **Handling-fee OJ publication date** (expected late Oct 2026).
- Context only: the Commission's cost report (ST 13480/26 ADD 1) records **60% fewer distance-sale items imported EU-wide in July 2026 vs July 2025**.

---

## PRD claims checked

| PRD claim (location) | Verdict | Reason |
|---|---|---|
| "Since 1 July 2026 every Temu order from outside the EU pays a €3 customs duty per tariff line (product category)" (Problem & context) | **Wrong in detail** | The unit is per item (declaration line: HS6 + description in H7) **per consignment**, not per order or "product category". The legal payer is the declarant (Temu/its agent), not the buyer. Preferential-tariff and >€150 consignments are outside the €3. |
| "…on top of 21% VAT" (Problem & context) | **Confirmed, incomplete** | NL VAT is 21%. But if Temu charges the €3 to the buyer at sale, VAT is also due *on the €3* (VAT addendum 21.8.2026). |
| "A €2 EU handling fee **per consignment** is expected from November 2026" (Problem & context) | **Wrong** | The delegated act C(2026) 6694 sets **€2 per item**. Start is about Nov 2026 but depends on OJ publication after a 30-day objection period. |
| "the €3 regime runs until 1 July 2028, after which ordinary percentage duties apply" (Problem & context) | **Confirmed** | Art. 2 Reg. 2026/382; Guidance §3.1. Caveat: Art. 3(2) allows a proposal to extend it. |
| "Dutch customs saw e-commerce declarations fall 46% in July–August" (Problem & context) | **Unverified** | A statistical claim outside this legal ticket. EU-wide, the Commission reports −60% items in July 2026 y/y. |
| F4 "duty = €3 × distinct tariff lines" (per cart) | **Partly wrong** | Valid per *consignment* only. Split parcels repeat lines. The count can exceed distinct HS6 if the declarant splits lines. |
| F3/Tech approach: key may be "a coarser internal bucket" than HS6; "declared tariff heading" | **Wrong as a legal basis** | In H7 the minimum granularity is the HS6 *subheading* (not the HS4 "heading"). Grouping across subheadings is barred (Art. 228(1) IA). A bucket coarser than HS6 will systematically undercount. |
| F5 "€0 if another item shares its line" | **Confirmed (conditionally)** | True when goods share HS6 + description and are declared on one line. Not guaranteed, because the declarant may split identical goods into separate lines (DR 2026/1022 recital 4). |
| F8 / Tech: €150 guard "on summed item prices excluding shipping" | **Partly confirmed** | Correct basis: net price paid (after discounts), excl. VAT, excl. separately-invoiced shipping. But the threshold is per **consignment**, so summing a multi-seller cart can trigger the warning falsely. |
| €150 guard copy "Above €150 the flat rate no longer applies" | **Confirmed, incomplete** | True for the €3. Above €150, IOSS is lost, normal duty + import VAT apply at the border, and the €2/item handling fee still applies. |
| Q2 (legal side): per order vs per parcel | **Answered** | Per consignment (parcel/transport contract). One order shipped separately = separate consignments (Guidance §3.3.1). |
| Q4 (legal side): variants = one line? | **Answered (law) / open (practice)** | Legally they can be one item (same HS6 + description). Whether Temu's declarant groups them needs test orders. |
| Q5 (legal side): €3 on list or net price? | **Answered** | The €3 is price-independent. The €150 test uses the net price paid after discounts (Explanatory Notes Q20). |
| Q9: €2 per consignment or per line? | **Answered** | Per item (same unit as the €3) under the delegated act of 21.9.2026. Uniform EU amount. No NL national fee. Whether Temu shows it separately remains empirical. |

## Sources

Primary, EU law (texts read in full via Publications Office CELLAR; EUR-Lex links given):

- Council Regulation (EU) 2026/382 of 11 Feb 2026, OJ L 18.2.2026: https://eur-lex.europa.eu/eli/reg/2026/382/oj/eng
- Commission Delegated Regulation (EU) 2026/1022 (C(2026) 2760), OJ L 1.7.2026: https://eur-lex.europa.eu/eli/reg_del/2026/1022/oj
- Commission Implementing Regulation (EU) 2026/1200 of 5 June 2026, OJ L 8.6.2026: https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202601200
- Regulation (EU) 2026/2108 (new Union Customs Code) of 16 Sept 2026, OJ L 19.9.2026 (Arts. 5, 20, 282(7), 286, 287): http://publications.europa.eu/resource/celex/32026R2108
- Commission Delegated Regulation C(2026) 6694 final of 21.9.2026 (Union handling fee amount): https://ec.europa.eu/transparency/documents-register/api/files/C(2026)6694_0/090166e533d2f58a
- Council cover note ST 13480/26 (22.9.2026) and ADD 1 (cost report): https://data.consilium.europa.eu/doc/document/ST-13480-2026-INIT/en/pdf · https://data.consilium.europa.eu/doc/document/ST-13480-2026-ADD-1/en/pdf

Primary, Commission guidance:

- News item, guidance and legal text on the €3 duty (8.6.2026): https://taxation-customs.ec.europa.eu/news/guidance-and-legal-text-temporary-flat-fee-low-value-imports-which-will-apply-until-1-july-2028-2026-06-08_en
- *Guidance for Member States and Trade: EUR 3 temporary customs duty*, version 2 June 2026: https://taxation-customs.ec.europa.eu/document/download/053e5b4e-f0be-4f20-9a23-3e3b659a6676_en?filename=Customs%20Guidance%20on%20EUR%203%20customs%20duty.pdf
- Q&A on the €3 guidance (30.6.2026): https://taxation-customs.ec.europa.eu/document/download/8350b1aa-935a-4b80-a349-385b36292fbe_en?filename=Questions%20and%20answers%20on%203%20EUR%20Guidance%20MS%20and%20Economic%20operators_clean15062026.pdf
- EU Customs Reform page (handling-fee status): https://taxation-customs.ec.europa.eu/customs/eu-customs-reform_en
- VAT addendum, *VAT treatment of the EUR 3 customs duty and of the announced Union handling fee* (rev. 21.8.2026): https://vat-one-stop-shop.ec.europa.eu/document/download/3086db0e-7b4a-4202-9f38-d32bd774f5a8_en?filename=20260821_VAT%20guidelines-3%20EUR%20Customs%20duty_revised.pdf
- VAT e-commerce Explanatory Notes (Q17–24 on intrinsic value, discounts, consignments): https://vat-one-stop-shop.ec.europa.eu/document/download/3372e2f2-d5ec-46ea-a2ac-97bc4f5ec634_en?filename=vatecommerceexplanatory_notes_28102020_en.pdf

Primary, Netherlands:

- Douane.nl, *Invoerrechten betalen voor e-commerce* (last update 22.9.2026): https://www.douane.nl/onderwerpen/invoer-en-uitvoer/invoer/aangifte-doen/aangifte-doen-bij-e-commerce/invoerrechten-betalen-voor-e-commerce/
- Kamerbrief, Staatssecretaris van Financiën, 12 June 2026, Kamerstukken II 31 934, nr. 113 (no national handling fee): https://zoek.officielebekendmakingen.nl/kst-1254416.pdf

Secondary (corroboration only, not relied on): SRA, *Nog geen nationale handling fee in Nederland* (Mar 2026), https://www.sra.nl/nieuws/004501/2026/03/nog-geen-nationale-handling-fee-in-nederland · Flavorcloud, *EU Sets Union Handling Fee at €2 Per Item*, https://flavorcloud.com/resources/commerce-intelligence-alerts-blog/eu-union-handling-fee-2-euro-per-item
