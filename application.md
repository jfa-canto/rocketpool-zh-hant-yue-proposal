## Name of Grant

**Rocket Pool rETH Guide for Traditional Chinese & Cantonese Readers (Hong Kong / Taiwan): zh-Hant guide, Cantonese quick-start, HK/TW on-ramp safety notes and a shared glossary**

### What is the work being proposed?

A small, fully public, task-focused education pack for **Traditional Chinese (zh-Hant)** readers in **Hong Kong and Taiwan**, with a **Cantonese** spoken-register quick-start for Hong Kong. It takes a reader from "what is rETH?" to "I practised staking on Hoodi and I know the risks", **without re-translating the official docs**.

Why this is not a duplicate of the other language packs in this round:

* The official docs (`docs.rocketpool.net/zh/`) and the Round 42 Chinese onboarding pack proposal both target **Simplified Chinese / mainland usage**. HK and TW readers use Traditional characters and partly different vocabulary (e.g. 智能合約 in HK vs 智慧合約 in TW, 網絡 in HK vs 網路 in TW). They also face different regulators and on-ramps. A mechanical character conversion (OpenCC) of Simplified text keeps mainland word choices and reads unnaturally to HK/TW users. This pack is written for these readers directly, and the HK Cantonese material is written and reviewed by a native Cantonese speaker.
* It is **scoped by artifact, not by word count**. Every deliverable has a fixed size and a checklist (see Acceptance criteria), so the GMC can verify it in under an hour.
* It **coordinates with, rather than competes with,** the Simplified-Chinese pack. We will publish the glossary as a CSV with a zh-Hans column, so both packs and any future docs translation use one consistent term list. We will contact that applicant after posting, in public in the discussion thread.
* It includes **jurisdiction-specific safety notes**. For example: "how to check whether an exchange is on the SFC's licensed VATP list (HK) or the FSC's VASP AML-registration list (TW) before you buy ETH", and "rETH is not on most of these platforms, so here is the self-custody step and its risks". These are written neutrally and link only to the regulators' own pages, with no platform endorsements.

Deliverables (all in one public GitHub repo, CC BY 4.0):

| # | Artifact | Size / definition |
|---|---|---|
| D1 | **zh-Hant rETH guide** (`guide/zh-Hant/`) | 6 sections, ~4,000–5,000 Chinese characters total: (1) what rETH is and how its exchange rate grows, (2) risks, (3) four ways to get rETH (protocol route, CoW Swap route in the stake UI, L1 DEX, L2 DEX) and when each makes sense, (4) using and storing rETH safely, (5) exiting rETH (liquidity caveats), (6) where to get help. Every protocol fact links to the English source page with an "as of" date |
| D2 | **Cantonese quick-start** (`guide/yue-HK/`) | 1 page in spoken Hong Kong Cantonese (書面粵語): "rETH 三分鐘講清楚" plus a 10-step Hoodi testnet practice walkthrough with screenshots |
| D3 | **Glossary** (`glossary.csv` + rendered page) | ≥ 60 terms. Columns: English, zh-Hant (TW), zh-Hant (HK), Cantonese colloquial (where different), zh-Hans (for alignment with the Simplified pack and docs), one-line definition, source link |
| D4 | **HK/TW on-ramp & scam checklist** | 1 printable page (PDF + Markdown): 12 checks before you buy ETH or sign anything (licensed-platform lookup via SFC / FSC lists, official rETH contract addresses on L1/Arbitrum/Optimism, fake "rETH airdrop" patterns, approval hygiene, fake support DMs) |
| D5 | **FAQ** | 15 Q&As drawn from real questions (Rocket Pool Discord and forum, plus Chinese-language threads), each answered with a source link |
| D6 | **Maintenance log + review record** | `REVIEW.md` (who reviewed what, issues found and fixed) and `CHANGELOG.md` with the docs commit each section was checked against |

Out of scope: re-translating the official docs, node-operator setup guides, video production, paid promotion, price or APR claims.

### Is there any related work this builds off of?

* Official docs, English source of truth: `docs/en/liquid-staking/{overview,via-rp,via-l1,via-l2}.mdx` and `docs/en/protocol/{faq,glossary}.mdx` in `rocket-pool/docs.rocketpool.net` (MIT). The existing `docs/zh/` (Simplified) will be used **only** for terminology alignment.
* The Round 42 Simplified-Chinese practical onboarding pack proposal (this thread, post #7). This application is complementary: different script, region and register, plus a shared glossary.
* Regulators' public lists used as references, not endorsements: the SFC "Lists of virtual asset trading platforms" (HK) and the FSC/SFB list of VASPs with completed AML registration (TW).

### Will the results of this project be entirely open source?

Yes. All text, the glossary, the checklist and screenshots are released under **CC BY 4.0** in a public GitHub repo. Any helper scripts (e.g. a glossary-consistency checker) are released under **MIT**. Rocket Pool and the community may reuse, adapt or merge any part into the official docs.

## Benefit

| Group | Benefits |
|---|---|
| Potential rETH holders | HK/TW readers get a guide in their own script and vocabulary. It explains how rETH's exchange rate (not its balance) grows, compares the four acquisition routes (including fees: 0.05% protocol deposit fee vs DEX slippage), and gives jurisdiction-specific safety checks before buying ETH. |
| rETH holders | Clear guidance on storage, approvals, using the official contract addresses on L1/L2, and how exiting works when the deposit pool lacks liquidity (protocol route vs CoW Swap / DEX). |
| Potential NOs | A short "from rETH to running a node" pointer page in zh-Hant, linking to the official node docs (4 ETH megapool bond). It is an on-ramp to the docs, not a setup guide. |
| NOs | Chinese-speaking NOs get a glossary and FAQ they can point friends to, instead of re-explaining basics. |
| Community | One shared, versioned multi-script glossary that the Simplified-Chinese pack, future docs translators and Discord helpers can all use. Plus an audit trail (REVIEW.md) showing how the content was checked. |
| RPL holders | Indirect: more informed rETH demand from a high-crypto-adoption region, without speculative marketing. |

### Which other non-RPL protocols, DAOs, projects, or individuals, would stand to benefit from this grant?

Traditional-Chinese Ethereum communities (e.g. ETHTaipei / Taipei Ethereum Meetup) gain a reusable liquid-staking explainer. DeFi venues that list rETH (Balancer, Uniswap, CoW Swap) benefit from better-informed users, but none is endorsed. The glossary CSV is useful to any project localizing staking terms into zh-Hant.

## Work

### Who is doing the work?

**JFA**, a native Cantonese speaker, bilingual in Chinese and English, working solo with AI assistance. If funded, I personally review every Cantonese deliverable line by line. A Taiwanese reader I know personally reviews the TW-specific wording (see Testing).

**AI-assistance disclosure:** research, first drafts and consistency checks are done with an AI writing assistant. Every sentence in the published pack is reviewed and edited by a human before release. Protocol facts are taken only from the official Rocket Pool docs and contracts and linked inline. AI output is never used as a source. The repo README will carry this same disclosure.

### What is the background of the person(s) doing the work? What experience do they have with such projects in the past?

I am a **native Cantonese speaker**, bilingual in Chinese and English, and personally review and edit all Cantonese (yue-HK) material and the HK column of the glossary.

This is my first grant of this kind: I have no previous Rocket Pool or crypto-education work to link to. I have not used rETH or staking myself, which is why the guide is built strictly on the official docs (every claim linked) and the walkthrough is tested end-to-end on the Hoodi testnet.

The **sample section** (D1 §1 "rETH 是什麼？匯率為何只升不降（通常）" plus 20 glossary rows) is attached below, so the GMC can judge quality before funding.

### What is the breakdown of the proposed work, in terms of milestones and/or deadlines?

| Milestone | Contents | Due (after award, 29 Nov) | Payment |
|---|---|---|---|
| **M1** | Repo public; D3 glossary (≥60 terms, 5 script/register columns); D1 sections 1–3; REVIEW.md opened | +3 weeks | **$300** |
| **M2** | D1 sections 4–6; D2 Cantonese quick-start with Hoodi screenshots; D4 checklist (MD + PDF); D5 FAQ (15 Q&As); independent native review completed and fixes logged | +6 weeks | **$300** |
| **M3** | Maintenance: one update pass after the next protocol/UI change or at +3 months (whichever comes first), with the docs commit hash re-checked and the CHANGELOG updated; glossary PR offered to the docs repo | +3 months after M2 | **$100** |

**Total: $700 USD**, paid in RPL (or LUSD, if the GMC prefers) at the rate on each payment date.

### How is the work being tested? Is testing included in the schedule?

Yes, testing is part of M1 and M2:
1. **Fact check:** every protocol claim carries an inline link to the English docs page and an "as of" date. The final review re-checks each link against the current docs commit. Contract addresses are checked against the docs and Etherscan/Arbiscan/Optimistic Etherscan.
2. **Walkthrough test:** the Hoodi testnet steps in D2 are performed end-to-end (testnet only, no real funds) and screenshotted on the date of writing.
3. **Language review:** I (native Cantonese speaker) review all yue-HK and HK-Traditional text line by line. A Taiwanese reader I know personally reviews TW wording in D1/D3/D4. Issues and fixes are logged in REVIEW.md. HK vs TW wording differences are kept in the glossary rather than "averaged".
4. **Consistency check:** a small script checks that every glossary term is used consistently across all files and flags Simplified characters leaking into zh-Hant files.

### How will the work be maintained after delivery?

* M3 is a paid maintenance pass (above).
* After M3, I will keep the repo open for issues for at least 12 months and fix factual errors within 14 days of a report, at no extra cost.
* Each section's header records the docs commit it was checked against, so staleness is visible.
* All content is CC BY 4.0, so the community or the docs team can fork or merge it at any time.

## Costs

### What is the acceptance criteria?

* **M1:** public repo with LICENSE (CC BY 4.0); `glossary.csv` with ≥60 rows and all columns filled (the Cantonese column may be "same as zh-Hant (HK)"); D1 §1–3 published, every protocol claim linked; REVIEW.md exists.
* **M2:** D1 §4–6, D2 (with ≥8 dated Hoodi screenshots), D4 (MD + PDF), D5 (15 Q&As, each with a source link) published; REVIEW.md shows a completed independent review with issues resolved; the consistency script passes.
* **M3:** CHANGELOG entry showing a re-check against a newer docs commit; any outdated statements fixed; glossary PR or issue opened on `rocket-pool/docs.rocketpool.net`.

### What is the proposed payment schedule for the grant? How much USD $ and over what period of time is the applicant requesting?

$700 USD total over about 4.5 months: $300 at M1, $300 at M2, $100 at M3, each paid on GMC verification.

### Who will directly receive the payment?

Ethereum address `0xa8342Db88A1b1B4A6ed0E4805eC4A80992CB561e` (MetaMask), belonging to the applicant. It will be confirmed via the GMC's designated Discord process.

### How will the GMC verify that the work delivered matches the proposed cadence?

Each milestone is announced with a reply in this thread linking a tagged GitHub release (`m1`, `m2`, `m3`) and a checklist mapping each acceptance criterion to a file. Verification takes no Chinese reading for the structural checks (file counts, links, review log), plus optional spot checks by any Chinese-reading community member.

### What alternatives or options have been considered in order to save costs for the proposed project?

* **Machine-converting the Simplified docs to Traditional (OpenCC):** rejected as the main deliverable, because it gets HK/TW terminology wrong. It will still be used to align glossary terms.
* **Full docs translation:** rejected because it is expensive and goes stale. This pack links to the docs instead.
* **Video or events:** rejected because they cost more and are harder to verify. Screenshots cover the walkthrough.
* **Merging with the Simplified pack:** offered. If the GMC prefers one Chinese grant, I am happy to deliver D1–D3 as a zh-Hant/yue add-on to that pack at a reduced scope and cost ($450).

### Have you already been compensated by the RP protocol in any way for this work?

No.

## Conflict of Interest

### Does the person or persons proposing the grant have any conflicts of interest to disclose?

No. I am not a GMC member, no GMC member benefits financially, and I hold no RPL or rETH.

### Will the recipient of the grant, or any protocol or project in which the recipient has a vested interest (other than Rocket Pool), benefit financially if the grant is successful?

No. No exchange, wallet or DeFi venue is endorsed and no referral links are used.

---

### Attachment: sample deliverable (D1 §1 + 20 glossary rows)

See `sample-section-zh-Hant.md` and `glossary-sample.csv` in this draft folder. In the forum post, paste the section inline and link the CSV via a public gist or the repo.
