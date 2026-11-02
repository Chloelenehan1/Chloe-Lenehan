# Analytics templates review

Reviewed 02/11/2026. Two documents:
- **DR** = Fabulate Analytics Data Reference (9 pages)
- **MG** = Fabulate Analytics Managed (3 pages)

Tags: **[MUST FIX]** blocks sending, **[FIX]** wording or accuracy, **[REMOVE]** internal-only content, **[QUESTION]** needs an answer from product or data before the wording can be finalised.

---

## Start here (do these first, in this order)

1. **MG-Screenshots-p2 and p3 : [FIX, brand safety]** The data is mock, but the screenshots use real trademarks: "KFC Thailand", "Zinger Double Down Dark", "Zinger Zinger 3 Campaign". In a client-facing Fabulate document this can read as a client endorsement or as using their brand without permission, and the caption "quick-service restaurant category" reinforces it. Re-shoot on a fictional demo brand, or blur brand and campaign names.
2. **MG-Screenshots-p2 (02) and p3 (metric strip) : [MUST FIX]** The screenshots show exactly what the text says a client never sees by default: "Spend this month", "Spend", "CPM", "Cost per result THB 0.04", plus "simulated rail", "Connect ad account", "New media plan" and an "Optimiser" tab. Re-shoot in the client-facing view (agreed price mode or no amounts mode) with demo labels hidden.
3. **DR-Section 2 intro-p1 vs MG-What you see and 01 Reach-p1 : [MUST FIX]** DR says reach and impressions are never available for organic pieces. MG says organic shows "reach where published" and lists reach and impressions under Reach and attention. One of them is wrong. Most likely fix: MG says "Organic: views. Paid: impressions and reach."
4. **DR-Section 4 Reach-p3 and MG-How each measure is calculated-p3 : [MUST FIX]** "Sum of daily reach" is incorrect. Reach is unique people, so adding daily reach counts the same person many times and overstates reach (and understates frequency). Any data team will spot this. Use the platform's reach for the whole window, or label it "sum of daily reach, not de-duplicated" and do not sum it across platforms.
5. **DR-Section 10 Held by Fabulate only column-p8 to p9 : [REMOVE]** Listing "margin", "platform fee, management and production fees", "actual media buy, platform invoices", "talent agency rates" and "cost per on actual cost, for the finance view" tells the client what is being withheld and invites a commercial conversation. Delete the column, or replace it with one line: "Commercial terms, creator fees and media buying costs are held by Fabulate."
6. Then work through the rest below.

---

## Data Reference (DR)

### Audience and internal content

- **DR-Whole document-all pages : [QUESTION]** Who is this for: self-serve platform clients, managed clients, or both? Sections 4 to 6 define money measures using creator fees, settled payments and commission (for example "Cost per engagement = settled creator fees ÷ engagements", "Creator money released", "Total investment = creator money released + paid media spend"). Section 10 and the MG document say managed clients never see creator fees. If it is for both, add one sentence at the top of section 5: "In a managed campaign, money measures follow section 10." If it is only for managed clients, rewrite the money rows in sections 2, 4, 5 and 6.
- **DR-Intro-p1 : [FIX]** "Everything here is a computation over stored rows" is internal phrasing. Suggest: "Every figure is calculated from data Fabulate has collected and stored."
- **DR-Intro-p1 : [FIX]** "Nothing is modelled or estimated unless the measure's name says so" is not true as written. Brand health, Share of voice, the Fabulate Resonance Score and Earned Media Value are modelled or estimated, and only "Reach estimate" has it in the name. Suggest: "Nothing is modelled or estimated without being labelled as such."
- **DR-Section 1 Rates-p1 : [FIX]** "One division defined once in code" is developer language. Suggest: "Each rate is calculated one way and used the same way on every screen and export."
- **DR-Section 1 Money-p1 : [REMOVE or QUESTION]** The money states (proposed, approved, executing, settled, pending, estimated) are internal workflow states. Will a client ever see "executing"? If not, remove.
- **DR-Section 5 Total investment-p4 : [REMOVE]** "Fees to Fabulate are shown as their own line where the viewer may see them" contradicts section 10 ("Fabulate fee and margin: not shown"). Remove.
- **DR-Section 5 Brand health-p5 : [FIX]** "BrandSync snapshot" is an internal product name the client will not know. Explain it or rename it to something client-facing.
- **DR-Section 6 intro and Revenue by source-p5 : [REMOVE]** "Asserted by a real store, or simulated in a demonstration" and "share of rows asserted by a real store" suggest a client's report could contain simulated data. Remove from the client version.
- **DR-Section 6 Commission owed and released-p5 : [QUESTION]** Section 10 says creator commission on orders is held by Fabulate only, so why is it defined here? Also "released by a person" is internal process. Remove, or mark as not shown in managed campaigns.
- **DR-Section 7 intro and Refresh cost-p6 to p7 : [REMOVE]** Quotes, caps, monthly budget per organisation and refresh cost ("Never on a client page") are internal cost controls. Remove from a client document.
- **DR-Section 9 Custom Reports CSV columns-p8 : [REMOVE]** "Note from the build" is a developer label. Rename or drop the column.
- **DR-Section 9 Brand report export-p8 : [FIX]** "With the sample-data mark where it applies" is internal. Remove.
- **DR-Section 9 What a shared page strips-p8 : [FIX]** "Source and vendor names" suggests third-party data vendors. Suggest "source details".
- **DR-Section 10 footer note-p9 : [REMOVE]** "Fabulate's finance role controls" is internal. Suggest: "The mode is set in your agreement."
- **DR-Footer-p9 : [FIX]** It mentions "figures shown in any screen of a demonstration workspace" but this document has no screens. Also check that "v0.1" is meant to go out to clients.

### Metrics that are confusing or inconsistent

- **DR-Section 2 Hook rate, Hold rate, Retention curve-p2 : [QUESTION]** These rely on "retention as the platform publishes it", but the section 3 table shows no platform publishing retention to a public read. Where does retention come from? Creator account access? If it is not available, MG should not lead with hook and hold rate.
- **DR-Section 2 Hook rate-p2 : [QUESTION]** The grain is "creator average", which conflicts with section 1 ("never averages of averages"). Is it a simple average of pieces or weighted by views?
- **DR-Section 2 Engagement rate vs Section 7 Engagement of views-p2 and p6 : [QUESTION]** There are two engagement formulas: organic includes saves, Custom Reports excludes them. Section 7 "Performance by creator" then calls it "engagement rate" again. This conflicts with the section 1 promise that "two reports cannot disagree". Pick one name per formula and use it everywhere.
- **DR-Section 2 Engagement rate-p2 : [FIX]** Many clients assume engagement rate is over followers or reach. Name it "engagement rate (by views)" wherever it appears, and say that Instagram images and carousels will show "not measured" because they have no view count.
- **DR-Section 2 Retention curve-p2 : [FIX]** "Fewer than one usable curve" means none. Say "No usable curve". "Element-wise median" could be "the median at each second across pieces".
- **DR-Section 2 Published against plan-p2 : [FIX]** "On-time counts done, total and overdue per creator" does not read clearly. Suggest: "Per creator: deliverables done on time, total due and overdue."
- **DR-Section 2 Compliance pass rate-p2 : [QUESTION]** What is scanned for? Ad disclosure, brand guidelines, or both? "Settled compliance scans" needs a plain definition.
- **DR-Section 3 intro-p2 : [FIX]** "Checked by reading one item per platform" sounds like a sample of one. Suggest: "Platform availability verified 06/10/2026."
- **DR-Section 3 table, Creator row-p3 : [FIX]** "same" under Instagram video is unclear. Repeat the values.
- **DR-Section 3 note-p3 : [FIX]** Instagram Stories being manual-only is significant for clients. Repeat this in MG.
- **DR-Section 4 Video views-p3 : [QUESTION]** Platforms define a video view differently (for example 2 seconds, 3 seconds, ThruPlay). Which definition is used, and are views summed across platforms with different definitions? The same applies to combined cost per view in section 5.
- **DR-Section 4 Clicks-p3 : [QUESTION]** Link clicks or all clicks? This changes CTR and CPC a lot.
- **DR-Section 4 Spend against budget-p3 : [QUESTION]** What is the "tolerance ratio" for ahead, on track and behind?
- **DR-Section 4 Results-p4 : [QUESTION]** What is an "objective-weighted total"? The MG paid screenshot shows "Results 8,469,471, objective-weighted" and "Cost per result THB 0.04", which looks like views and conversions added together. A client would find this misleading. Suggest never totalling results across objectives.
- **DR-Section 4 Cost per result-p4 : [FIX]** "Compared with the account median after the learning phase": which account, and median of what? Explain or remove.
- **DR-Section 4 Creative leaderboard-p4 : [QUESTION]** Ranking ads by cost per result only works within one objective. Is it ranked within objective?
- **DR-Section 4 Optimiser marks-p4 : [QUESTION]** Should clients see "Optimiser" and "budget move"? In no amounts mode, a budget move reveals budget information.
- **DR-Section 5 Brand health-p5 : [QUESTION]** How is the 0 to 100 figure calculated, and what are the thresholds for good, watch and weak? "Read off engagement and growth" is not a definition a data team can use.
- **DR-Section 5 Share of voice-p5 : [QUESTION]** What is the "observed activity" (posts, mentions, engagement)? Who chooses the tracked competitors?
- **DR-Section 6 Code clicks, Orders-p5 : [QUESTION]** "Creator code" is defined as a click redirect, but most clients will read "code" as a discount code. Are orders attributed by discount code at checkout, by link click, or both? What is the attribution window? Is revenue before or after GST, shipping, discounts and refunds?
- **DR-Section 6 Conversion rate-p5 : [FIX]** "orders ÷ clicks" has no "× 100", unlike every other rate. Make it consistent.
- **DR-Section 6 Code clicks, Commission, Revenue by source-p5 : [FIX]** The "Not shown when" column is blank. Fill it in or add "always shown".
- **DR-Section 6 Website traffic and leads-p6 : [FIX]** "roadmap" sits in the Grain column. Move it out of the measures table into a roadmap note.
- **DR-Section 7 Followers and tier-p6 : [FIX]** "tier is then null" is data jargon and conflicts with the section 1 absence rule ("shown as a word"). Use the absence word.
- **DR-Section 7 Median views, average views-p6 : [QUESTION]** Excluding posts with zero views inflates the median and average. Is that intended? If so, say why.
- **DR-Section 7 Potential reach-p6 : [FIX]** This is the sum of followers, not reach. Rename it "Combined followers", or add "not de-duplicated, not actual reach".
- **DR-Section 7 Earned Media Value-p7 : [QUESTION]** Whose rate card is it: Fabulate's or the client's? MG says "your agreed rate card" while DR says "the organisation's rate card". Align them.
- **DR-Section 8 Fabulate Resonance Score-p7 : [QUESTION]** It is only defined "in Custom Reports", but MG presents it as a measure group for managed campaigns. Is it available on Fabulate-run campaigns?
- **DR-Section 8 Percentile ranking-p7 : [QUESTION]** With two creators, one scores 0 and the other 100 on every component. Is there a minimum number of creators before the score is shown?
- **DR-Section 8 Presence-p7 : [FIX]** "Posts per week multiplied by cadence against usual rate, capped at three times" is hard to follow. What are the units? Add a worked example.
- **DR-Section 8 Resonance component-p7 : [FIX]** A component called "Resonance" inside the "Resonance Score" will confuse people. Rename the component (for example "Lift").
- **DR-Section 9 Exports-p8 : [QUESTION]** Section 1 says a data team can join Fabulate exports to its own tables, but the only exports listed are a brand report PDF and Custom Reports CSV and Excel. Is there a paid or commerce export, or an API? A data team will ask.
- **DR-Section 10 Media spend and rates-p8 : [FIX]** CPM, CPC and CPV "computed on the agreed price" will not match the platform's own CPM. Label them "at agreed price" every time so they are not mistaken for platform rates.
- **DR-What the client connects box-p9 : [QUESTION]** It says the client connects its ad accounts, but MG says "the accounts are ours" for managed campaigns. Say which applies to which client type.

### Proofreading

- **DR-Section 10 Cost per engagement row-p8 : [FIX]** "Cost per on actual cost" is a broken phrase (and should be removed anyway, see Start here, item 5).
- **DR-Section 3 table-p2 to p3 : [FIX]** The table header repeats where it breaks across pages. Fine for a PDF, but check the table does not split awkwardly.
- Spelling is already Australian English (modelled, organisation, optimiser), dates are in DD/MM/YYYY and there are no em dashes. Nothing to change there.

---

## Managed (MG)

### Page 1

- **MG-Intro-p1 : [FIX]** "Never the creator fees, media rates or margin behind it" draws attention to a margin. Suggest: "Commercial terms behind the price stay with Fabulate."
- **MG-What you see, Organic content-p1 : [MUST FIX]** Remove "reach where published" (see Start here, item 3). Hook and hold rate depend on the retention question above.
- **MG-What you see, Paid media-p1 : [FIX]** "CPM and cost per result on your agreed price" will not match the platform CPM. Label it "at agreed price".
- **MG-What you see, Custom reports-p1 : [QUESTION]** Are Custom Reports included for managed clients, or are they an add-on?
- **MG-What you see, all columns-p1 : [FIX]** The doc uses "when you ask", "where you choose to see them" and "on request" for the same idea. Pick one.
- **MG-Measures 01 Reach and attention-p1 : [MUST FIX]** Same reach and impressions contradiction. Suggest: "Views (organic), impressions, reach and frequency (paid)..."
- **MG-Measures 03 Efficiency-p1 : [FIX]** "Never on fees or rates" reads oddly. Suggest: "Never calculated from creator fees or media rates."
- **MG-Measures 05 Fabulate Resonance Score-p1 : [FIX]** "Plus delivery, compliance, brand health and share of voice" are not part of the score but sit in the score's box. Move them to their own group (for example "06 Delivery and brand").
- **MG-Rules, match your ad manager-p1 : [FIX]** "Open your own ad manager... numbers match" conflicts with p3 ("the accounts are ours"), so a managed client has no ad manager to open. Organic figures are also latest readings, so they will differ by date. Suggest: "Every figure shows its source and read date, so it reconciles to the platform's own figures for that day."
- **MG-Rules, Nothing is estimated-p1 : [FIX]** Earned Media Value is an estimate and the Resonance Score is an index. Suggest: "Nothing is estimated without being labelled."
- **MG-Rules, rate with no agreed price-p1 : [FIX]** This reads as if engagement rate needs a price. Say "A cost-based rate..."
- **MG-Header-p1 : [FIX]** "1 OF 3" is capitalised but p2 and p3 use "2 of 3" and "3 of 3", and p1 has no section label. Make them consistent.

### Page 2

- **MG-Intro-p2 : [FIX]** "Quick-service restaurant category" next to real trademarks in mock screenshots (see Start here, item 1).
- **MG-01 Brand report screenshot-p2 : [QUESTION]** The screenshot shows an "Ask" box with suggested questions. DR says "No model writes" the summary. If there is an AI Q&A feature, mention it. If not, crop it out.
- **MG-02 Paid media screenshot-p2 : [MUST FIX]** It shows spend, cost per result, "Connect ad account", "New media plan" and an Optimiser badge (see Start here, item 2).
- **MG-03 Campaign by campaign screenshot-p2 : [FIX]** The cards show empty image placeholders ("No content thumbnail"). Use a screenshot with real demo thumbnails.
- **MG-04 Custom reports-p2 : [FIX]** "Add posts the networks do not publish" is unclear. Suggest: "add posts by hand that cannot be read automatically, such as Instagram Stories."
- **MG-04 Custom reports screenshot-p2 and p3 : [FIX]** The report is named "Test Report". Rename it in the demo.
- **MG-05 and 06 headings-p2 : [FIX]** These are styled differently from 01 to 04 (small inline number, no screenshot), and "custom" in the 06 heading should be "Custom". Make them consistent.

### Page 3

- **MG-Layout-p3 : [FIX]** The metric strip screenshot is a thin bar with a large empty space below it in the left column. Use a taller screenshot or rebalance the columns.
- **MG-Metric strip screenshot-p3 : [MUST FIX]** It shows "Spend this month", "simulated rail" and "CPM 96.12 THB" next to the "Investment" definition, which says investment is the agreed price, not spend.
- **MG-Investment-p3 : [FIX]** "Not the sum of what Fabulate paid out" implies there is a gap. Suggest: "The agreed campaign price for the window."
- **MG-Impressions, reach, frequency-p3 : [MUST FIX]** "Summed from the daily figures" has the same reach error.
- **MG-Cost per result-p3 : [FIX]** It combines cost per result, per engagement and per view in one definition. Split into three lines.
- **MG-The report head-p3 : [FIX]** "Which snapshot was read" is jargon. Suggest "the date the data was last updated".
- **MG-What you connect, Ad accounts-p3 : [QUESTION]** What happens when the client runs some media on its own accounts? Can those be connected too?
- **MG-What you connect-p3 : [FIX]** Website traffic and leads (roadmap) is missing here, though it appears on p2. Add it so this summary is complete.
- **MG-Footer-p3 : [FIX]** "Figures change with every refresh" undermines confidence. Suggest: "Screens show sample data from a demonstration workspace, not a client's results."

---

## Lize's client questions: what the templates already answer

This maps each question to what the two documents say. Anything marked **Confirm** is not in the documents, so check with product before replying. Nothing here is a commitment.

| Client question | What the templates say | Confirm with product |
|---|---|---|
| Paid and organic separately, plus a combined view? | **Yes.** Paid and organic are reported separately and never added together without a label (DR s1, s4, s5). "Organic against paid" shows each boosted piece's organic and paid views side by side. The brand report gives the combined view. | That this is in the new platform build, not only planned. |
| What more than today? | New in the templates: hook and hold rate, retention curves, creative leaderboard, delivery against plan, compliance pass rate, Fabulate Resonance Score, Earned Media Value, brand health, share of voice, commerce (orders, revenue, AOV), live-stream sales, Custom Reports for work booked elsewhere. | Which of these are already in today's platform (I cannot see it), and where hook and hold rate data comes from (open question above). |
| Media spend next to performance: CPM, CPC, cost per conversion? | **Yes, depending on the agreement.** CPM, CPC, CPV and cost per result are all defined (DR s4). Cost per conversion is cost per result where the objective is conversions. In managed campaigns they show at the agreed price, on request, or not at all (DR s10). | How to explain "at agreed price" rates, which will not match platform CPMs. |
| Outcomes: website traffic, leads, sales? What tracking? | **Sales: yes**, through creator codes plus a connected Shopify or WooCommerce store, or other stores through a custom integration or order feed. **Leads and conversions on paid**: reported where the ad set's objective is leads or conversions. **Website traffic and leads overall: roadmap**, needs tracked links on every creator code and landing page plus a site analytics feed. | Whether pixel or Conversions API setup (Meta, TikTok) is needed for paid conversions, which analytics tools the feed will support (for example GA4), and a timeframe for the roadmap item. The templates do not cover these. |
| Social commerce integrations? | Only live-stream rooms (viewers, offers, orders) are covered. Nothing about TikTok Shop, Shopee, Lazada or Instagram Shopping. | Whether any social commerce integration is planned. This matters for Southeast Asian clients. |

### Draft reply to Lize (fill the brackets before sending)

> Hi Lize, thanks for passing these on. Short answers for the client:
>
> - **Paid vs organic:** yes. Paid and organic are reported separately, with a combined campaign view, and boosted content shows its organic and paid views side by side, so paid never inflates organic.
> - **More depth:** new reporting includes [confirm list: retention (hook and hold rate), a creative leaderboard, delivery against plan, Earned Media Value, a creator performance score, brand health and share of voice].
> - **Spend alongside performance:** yes. CPM, cost per click, cost per view and cost per result (including cost per conversion where that is the objective) sit next to performance. For managed campaigns these are calculated on the agreed campaign price.
> - **Outcomes:** sales are reported today through creator codes and a connected store (Shopify, WooCommerce, or others through an order feed). Leads and conversions from paid show where the campaign objective is set to them. Website traffic and leads across the whole campaign are on the roadmap and will need tracked links plus a feed from the site's analytics [confirm timing and tools].
> - **Social commerce:** [confirm with product].
>
> Happy to walk them through it.
