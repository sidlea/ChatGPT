# KPIs, cash-flow template, labour, stock, suppliers and service standards

> Part of the Hallgate playbook for Cassiel Bar & Kitchen and Raph's Lounge, Cottingham. Prices, dates and margins are working assumptions (Oct 2026): check them against real recipe costs, licences and calendars before use.

## 4. Financial KPIs and benchmarks: UK independent bar-restaurants, 2026

### 4.1 Benchmarks and targets

| KPI | Target for you | Amber | Red | Evidence |
|---|---|---|---|---|
| **Food GP % (actual, stock-adjusted)** | **≥68%** | 64–67.9% | <64% | Gastropub 65–70%, casual dining 68–72% ([Nory 2026](https://www.nory.ai/blog/what-is-a-good-profit-margin-for-restaurants)); food cost 28–35% equals 65–72% GP ([NetSuite](https://www.netsuite.co.uk/portal/uk/resource/articles/erp/restaurant-benchmarks.shtml); [Stocktake Online](https://blog.stocktake-online.com/good-gross-profit-margin-uk-restaurant-2026)) |
| **Wet GP %** | Cassiel (cocktail-led) **≥70%**; Raph's (beer-led) **≥65%** | −3 points | −5 points | Beverage GP in the mid-70s to low-80s depending on programme (vendor sources above). Wet-led community pubs historically much lower ([BBPA 2013, dated](https://www.morningadvertiser.co.uk/Article/2013/11/14/BBPA-Benchmarking-survey-2013)). [consultant targets] |
| **Theoretical vs actual GP gap** | ≤2 pts | 2–4 | >4 | [consultant] |
| **Labour % of net sales** (all-in: wages, NIC, pension, holiday; excludes owners) | **≤30%** | 30–35% | >35% | Hospitality wages above 30% of turnover ([CBI](https://www.cbi.org.uk/media/bkdl4v2b/business-costs-hospitality-cbi-deep-dive.pdf)); pubs 27% in 2025 ([CBI pubs](https://www.cbi.org.uk/media/extlnkk2/business-costs-beer-pubs-breweries-cbi-deep-dive.pdf)); staffing 40–45% of operating costs ([Caterer Licensee](https://catererlicensee.com/average-pub-faces-78-business-rates-rise-as-wage-inflation-and-vat-stagnation-push-sector-to-breaking-point/)) |
| Kitchen labour % of net food sales | ≤25% | 25–30% | >30% | [consultant] |
| **Prime cost** (cost of goods + labour) | ≤60% | 60–65% | >65% | [consultant; see NetSuite on prime cost] |
| **Rent % of net sales** | ≤10% | 10–13% | >13% | RICS: new pub lease rent averaged 8.4% of turnover ([Morning Advertiser, 2016](https://morningadvertiser.co.uk/Article/2016/02/16/RICS-Average-new-lease-rent-up-3-year-on-year)); BBPA rent typically 45–55% of divisible balance ([BBPA Running a Pub](https://admin.beerandpub.com/media/03ld0xta/running-a-pub-2026-final.pdf)). Dated; [consultant target] |
| Total occupancy (rent, rates, service charge, insurance) | ≤15% | 15–18% | >18% | [consultant] |
| Utilities % | ≤5% | 5–7% | >7% | Pubs 5.4% in 2025 ([CBI pubs](https://www.cbi.org.uk/media/extlnkk2/business-costs-beer-pubs-breweries-cbi-deep-dive.pdf)) |
| **Four-wall EBITDA** | ≥10% | 5–10% | <5% | [consultant] |
| **Spend per head** (net, evening, food and drink) | Cassiel £28–34; Raph's £26–32; lunch £13–17 | — | — | UK average eating-out visit spend was £18.35 in Q1 2026, up 5.5% (all channels including quick-service) ([Lumina Intelligence](https://www.lumina-intelligence.com/?p=41673)). [consultant targets] |
| Seat turns (evening) | Mon–Thu 0.8–1.2; Fri–Sat 1.5–2.0 | — | — | [consultant] |
| Sales per labour hour (SPLH) | ≥ loaded hourly rate ÷ target labour %. At £16 an hour and 30%, that is **£53** | £45–53 | <£45 | Formula |
| Waste % of food sales | ≤2% | 2–4% | >4% | [consultant]; restaurants that measured and cut waste reduced it 26% on average and almost all increased profit ([The Grocer / Champions 12.3](https://thegrocer.co.uk/news/restaurant-food-waste-improvements-shown-to-hike-profits/576629.article)) |

**Loaded hourly cost of a National Living Wage worker in 2026** (30 hours a week) **[my arithmetic; verify with payroll]**:

| Element | £/hour |
|---|---|
| Base rate (NLW) | £12.71 |
| Holiday accrual at 12.07% | +£1.53 |
| Employer NIC at 15% above about £96/week | about +£1.43 |
| Auto-enrolment pension at 3% on qualifying earnings | about +£0.26 |
| **Total loaded cost** | **about £15.93** |

Chefs above the wage floor cost about **£17–20 an hour loaded**.

**Note:** if the two companies are "connected", only **one** may be able to claim the £10,500 Employment Allowance. Check with your accountant.

### 4.2 Breakeven calculation (per venue)
`Breakeven net sales/week = weekly fixed costs ÷ contribution ratio`, where
`contribution ratio = 1 − (COGS% + variable/hourly labour% + card fees% + other variable%)` ([Toast](https://pos.toasttab.com/blog/on-the-line/how-to-calculate-break-even-point)).

**Illustrative Raph's** (replace with actuals):

| Line | £/week |
|---|---|
| Fixed: rent, rates, utilities base, insurance, licences and software, salaried head chef and GM share, repairs | **£3,050** |
| Variable % (COGS 32% + hourly labour 20% + card fees 1.5% + other 3%) | **56.5%** |
| Contribution ratio | 43.5% |
| **Breakeven net sales** | **£7,011** a week (about £8,413 incl. VAT) |
| At £25 net spend per head | **about 280 covers a week**: 40 a day over 7 days, or 56 a day over 5 trading days |

Run this for each venue, then run the **group** version, where shared costs are counted once. That shows the true benefit of consolidation.

### 4.3 One-page weekly KPI dashboard spec
**Format:** a Google Sheet with one tab per venue and a group tab, filled automatically by n8n from the EPOS export, SV Tables, the payroll or rota app, and the Google review feed. It is reviewed in a **60-minute Monday meeting** with the owners, ops manager and head chef.

| Block | Metric | Source | Target / RAG |
|---|---|---|---|
| **Sales** | Net sales vs target and vs same week last year (food, wet, total) | EPOS | G ≥100% of target · A 90–99% · R <90% |
| | Covers; spend per head (food and wet); wet:dry mix | EPOS | vs target |
| | Sales by daypart (heat-map) | EPOS | Flags sessions failing the session P&L test |
| **Demand** | Bookings for the next 14 days vs the same point last month; no-shows | SV Tables | G up · A flat · R down >10% |
| | Google: new reviews, average stars (rolling 30 days), % replied within 48 hours | Google Business Profile | G ≥4.5 and 100% replied · A 4.0–4.4 · R <4.0 or any 1-star unreplied after 48 hours |
| **Margin** | Food GP% actual (weekly A-item count; monthly full count) | Purchases + stock | ≥68 / 64–68 / <64 |
| | Wet GP% actual (monthly independent stocktake) | Stocktaker | Per-venue target ±3 points |
| | Wet stock variance (stocktaker, % of wet sales) | Stocktaker | G ≤1% loss · A 1–2% · R >2% **[confirm tolerance with stocktaker]** |
| | Waste £ and % of food sales | Waste log | ≤2 / 2–4 / >4 |
| **Labour** | Labour % (all-in) by venue; kitchen labour % of food sales; SPLH | Rota or payroll + EPOS | ≤30 / 30–35 / >35 |
| | Hours scheduled vs worked vs forecast | Rota app | Variance ≤5% |
| **Controls** | Post-send voids, refunds, discounts and comps as % of sales, by user | EPOS | G <1% total and no outlier user · R >2% or any user above 2× average |
| | No-sale drawer opens; cash over/under | EPOS + cash-up | G ≤ £5 a shift variance |
| **Quality & safety** | % of main courses out within 20 minutes; complaints; allergen incidents; SFBB diary complete | Kitchen display or tickets; logs | G ≥90% · zero incidents · 100% complete |
| **Cash** | Closing cash vs minimum buffer; 13-week low point; overdue creditors (HMRC, rates, utilities) | 13-week cash flow | G buffer held all 13 weeks · A breach in weeks 5–13 · R breach within 4 weeks or any statutory arrears |

### 4.4 13-week cash-flow template (structure)
- **One sheet per company** ([Cassiel's company] / [Raph's company]) plus a consolidated view.
- **Columns:** W1 (w/c **19 Oct 2026**) to W13 (w/c **11 Jan 2027**), plus a total. Each week has Forecast / Actual / Variance.
- **Update:** every Monday. Roll forward one week, and explain any variance over £500.

```
OPENING CASH (bank + cash on premises)
RECEIPTS
  Card settlements – Dojo (by venue)          [settlement lag: next-day? verify]
  Card settlements – Paynt (by venue)
  Cash takings banked
  Delivery platform payouts (Deliveroo/Uber Eats – weekly, net of commission)
  Christmas/event deposits & pre-orders        [major Nov receipts – VAT due on deposits]
  Intercompany receipts (kitchen labour recharge etc. – documented)
  Other (insurance claims, grants)
TOTAL RECEIPTS
PAYMENTS
  Food suppliers (one line per supplier, by terms)
  Drinks suppliers / brewery / wine merchant
  Net wages (weekly/monthly payroll dates)
  PAYE/NIC to HMRC (22nd of month: 22 Oct, 22 Nov, 22 Dec)
  Pension contributions
  VAT (quarter-end per stagger; note any payment falling in Jan)
  Rent (quarter days – 25 Dec falls in W10 if paid quarterly in advance) + service charge
  Business rates (instalments typically 1st of month Apr–Jan)
  Utilities (incl. any payment plans)
  Insurance, licences (PRS/PPL music licence), EPOS/software subscriptions
  Repairs & maintenance
  Finance: loans, equipment leases, any cash advance (model as % of card receipts)
  Professional fees (accountant – accounts due 31 Oct; stocktaker; legal)
  Intercompany payments
  Owner drawings (explicit line – make it visible)
TOTAL PAYMENTS
NET CASH FLOW
CLOSING CASH
Minimum buffer (e.g., 2 weeks' payroll + next VAT + next rent quarter accrual)
HEADROOM (closing – buffer)  → RAG
```

**Notes on the cash flow:**
- **File statutory accounts on time.** Companies House late-filing penalties start at £150 and double if the previous year was also late.
- **Model any merchant cash advance before signing.** Repayments taken as a % of card takings will squeeze the January low point, so compute the effective annualised cost against alternatives.

---

## 5. Labour and rota, stock control and shrinkage, suppliers

### 5.1 Right-sizing the shared kitchen team
**Sizing method:** list each venue's trading sessions, the cooks each needs at the forecast covers per hour (staffing guide below), plus prep hours. Compare the total with rostered hours, and check that kitchen labour lands at 25% or less of net food sales.

**How to get there lawfully and humanely** **[verify each step with an employment adviser]**:
- Freeze recruitment.
- Don't replace leavers.
- Ask for volunteers to reduce hours.
- End agency or casual cover first.
- Consult before changing contracted hours.
- The Employment Rights Act 2025 is phasing in new obligations (e.g. restrictions on "fire and rehire", and future rights on guaranteed hours and shift notice). Don't assume 2024 rules.
- Tips must be allocated fairly and in full under a written policy (Employment (Allocation of Tips) Act 2023, in force since Oct 2024).

**Rota rules:**
1. **Forecast-led.** Forecast each day and daypart as the average of the last 4 equivalent days, adjusted for bookings and events. The **labour budget is forecast sales × target %**, minus salaried cost.
2. **Staffing guide** **[consultant guide]**:
   - Kitchen: 1 cook up to about 20 covers an hour, 2 cooks up to about 45, 3 cooks up to about 70.
   - Front of house: 1 server per 20–25 seated covers.
   - Bar: 1 bartender per 60–80 drinks an hour.
3. **One rota, two cost centres.** Staff clock in to the venue they work at. Recharge between the two companies monthly with a written agreement.
4. **"Cut sheet" at 15:00 and 20:00.** If sales are 20% or more below forecast, finish the next scheduled cut early.
5. **Prep in quiet windows** (Mon–Wed mornings) to avoid split shifts. Cross-train cooks across both venues.
6. **Single accountability:** appoint a **Group Head Chef** for menus, specs, GP, ordering and the kitchen rota. Pay a monthly bonus funded from improvement, separate from tips: for example, if food GP is 67% or more, the 30-day average Google rating is 4.5 or more, and there are zero allergen incidents.
7. **Tools:**
   - A rota and time-and-attendance app integrated with the EPOS (RotaCloud, Planday, Deputy, Bizimply, Tanda and similar). Typical cost is a few pounds per user per month **[verify pricing]**.
   - Publish the rota at least 2 weeks ahead.

### 5.2 Stock control and shrinkage

**Weekly and monthly cadence:**
| When | What | Who |
|---|---|---|
| Daily | Delivery check (count, weight, temperature, use-by, product code) by **two people**; credit notes logged; waste log per shift; cash-up with blind count | Shift lead / chef |
| Weekly (Monday a.m.) | **Food "A-item" count**: the top 20 lines by value (proteins, cheese, oil, prawns, halloumi), about 30 minutes. Calculate the theoretical usage of each from the EPOS product mix × spec grams, and compare. | Head chef plus one witness |
| Weekly | EPOS controls review (list below) | Ops manager |
| Monthly | **Full food stocktake** (valued) → actual food GP | Head chef + ops manager |
| Monthly (first 3 months), then 4–6 weekly | **Independent wet-stock audit** per venue: line-by-line yields, surplus or deficit at retail value, by category. Staff counting their own stock is a conflict of interest ([Morning Advertiser, "Setting the standard"](https://www.morningadvertiser.co.uk/Article/2006/11/30/Setting-the-standard/); a monthly drinks-audit model is described in [RGIS](https://www.rgis.co.uk/case-study/restaurant-monthly-drinks-audit/)). Budget about £80–£200 per venue per visit **[consultant estimate; get 2–3 quotes from Hull and East Riding stocktakers]**. | Independent stocktaker |

**Wet stock specifics:**
- Yields: 11-gallon keg = 88 pints; 50 L keg ≈ 88 pints.
- Record **line-cleaning losses** on a sheet.
- Return ullage for brewery credit.
- Cocktails are built to **spec with jiggers**; no free-pouring.
- Premium spirits locked away, with bottle-for-bottle empty exchange.
- A written staff-drinks policy, with every staff drink rung on the EPOS under a staff key.
- Consider flow-monitoring technology for draught once volumes justify it **[verify cost]**.

**Inter-venue transfers.** Every item that moves between Cassiel and Raph's (kegs, bottles, food prep) goes on a **transfer note**: a simple Google Form with date, item, quantity, from, to and initials. **Without this, both venues' GP figures are fiction, and theft is invisible.**

**EPOS and payment reports to check weekly** (by user and by hour):
1. **Voids**, especially post-send and post-payment.
2. **Refunds**, especially cash refunds.
3. **Discounts and comps**, by user and reason code.
4. **No-sale** (drawer opens).
5. **Cash over/under** by drawer and shift.
6. **Open-price items and price overrides.**
7. Bills **re-opened after payment**, and deleted or merged tables.
8. Staff food and drink vs allowance.
9. Bar **wastage** entries vs stocktake losses.
10. Sales by hour vs clock-ins: is labour on when sales are not?
11. **Card terminal settlements (Dojo and Paynt) vs EPOS card totals, daily.** Standalone, non-integrated terminals let card and cash tallies drift. Integrate payments with the EPOS where possible.
12. Tips report and distribution, for Tips Act compliance.

**Controls:**
- **Manager PIN** required for voids, refunds, discounts and no-sales, with mandatory reason codes.
- CCTV covering tills, cellar and stores.
- A key log for the cellar and stores.
- Rotate the cash-up person.
- Investigate any user whose voids or refunds exceed **2× the team average**.

### 5.3 Supplier consolidation

| Supplier | What we found | Best use | Watch-outs |
|---|---|---|---|
| **Turner Price** | Hull-based foodservice wholesaler (founded 1992) with depots in Hull and Newton Aycliffe; multi-temperature fleet; ambient, chilled, frozen, fresh meat, fruit and veg; Country Range own-brand; an Advanced Order service for about 3,000 additional lines ([Better Wholesaling](https://www.betterwholesaling.com/interview-turner-price/); [NACC](https://thenacc.co.uk/partners/premier_partners/turner-price)) | **Primary broadline candidate:** local, multi-temperature, one drop for most lines | Negotiate fixed prices on the top 40 lines; get spec and allergen sheets for every product |
| **JJ Foodservice** | National foodservice wholesaler with branches including Leeds and Doncaster ([JJ history](https://www.jjfoodservice.com/blog/events/the-history-of-jj-food-service-limited-1988-to-2015)); a historic online minimum of £79 ([Wholesale Manager, dated](https://wholesalemanager.co.uk/jj-encourages-independent-retailers-to-take-advantage-of-chef-quality-foods-and-bulk-savings/)) | Competitive on chicken thigh, Mediterranean, Turkish and Greek lines, and frozen goods | **[verify]** Hull delivery days and the current minimum |
| **Makro** | Cash & carry and delivery (UK terms not verified in this pass) | **Emergency top-up only**, capped at a weekly £ limit | Hidden labour (staff driving and shopping); **brand switching breaks the allergen matrix**; impulse buys |
| **Brakes / Bidfood** | National broadliners. Brake lists Maris Piper at £24.24 per 25 kg ([Brake](https://www.brake.co.uk/fresh-produce/potatoes/white-red/white/maris-piper-potatoes/p/450066)). | Good spec and allergen data; a benchmark quote | Often pricier for small independents; drop minimums **[verify]** |
| **Current local butcher** | — | Fresh beef mince, steaks, lamb mince and shoulder. Ask for **pre-portioned** smash balls and steaks. | Fix the price per kg for 3 months |

**Process: a 2-week "basket tender".**
1. Take the **top 40 lines by spend** from the last 8 weeks of invoices.
2. Send the same basket to Turner Price, JJ and one of Brakes or Bidfood.
3. Ask for price per kg, delivery days to HU16, drop minimum, credit terms (target 30 days), fixed-price periods on proteins, cheese and oil, and a spec and allergen sheet for every line.
4. **Target:** one broadline supplier, one butcher, one drinks supplier, and Makro by exception.
5. Align delivery days with the hub prep days (Mon, Wed, Fri).

**Expected saving:** 3–8% on food purchases from consolidation and fixed pricing **[consultant estimate]**, plus fewer staff hours spent shopping.

### 5.4 Waste log
- **Fields:** date, shift, venue, item, quantity or weight, reason (over-production, spoilage or out-of-date, returned by customer, dropped or burnt, staff error, comp), £ value (auto-calculated from spec cost) and initials.
- **Format:** a Google Form on a tablet in each kitchen and bar.
- **Review:** weekly. The top three reasons each get one fix, such as par levels, batch sizes or FIFO.

---

## 6. Service and experience standards

### 6.1 The 10 "moments of truth" (with a standard for each)
| # | Moment | Standard |
|---|---|---|
| 1 | **Find & choose** (Google, website, socials) | Menu uploaded to Google Business Profile and the website; hours correct, including kitchen and lunch hours; booking link works; phone answered within 5 rings |
| 2 | **Arrival** | Acknowledged within **30 seconds**, even when busy |
| 3 | **Seating & first drink** | Seated within 2 minutes; drinks order within **3 minutes** |
| 4 | **The allergy question** | **Every table:** "Does anyone have any allergies or dietary requirements I should know about?" |
| 5 | **Drinks delivered** | Beer and wine within 5 minutes; cocktails within 7, built to spec |
| 6 | **Order & recommendation** | Recommend one star dish and one drink pairing per table, in the server's own words |
| 7 | **Food arrives** | Small plates and starters within 12 minutes; mains within 20; matches the photo spec; hot; announced by name |
| 8 | **Check-back** | Within 2 minutes or two bites. Fix problems immediately; servers are **empowered** to replace a dish or offer a drink up to £X. |
| 9 | **Bill & payment** | Bill within 2 minutes of the request; no pressure on tips |
| 10 | **Farewell & follow-up** | Thank the guest by name if booked and invite them back (e.g. "Gig night Friday"). Reply to every review within **48 hours**, using the existing approval workflow. |

### 6.2 Simple training plan (6 weeks; owners delegate it to the ops manager)
- **Format:** two 15-minute pre-shift huddles a week plus one 60-minute session a week. Each person gets a buddy and a **sign-off checklist** stored on the Trade Hub.

| Week | Topic | Output |
|---|---|---|
| 1 | **Allergens & food safety.** Every food handler and server completes the FSA's free online allergy training; certificates are filed. | Allergen script, EPOS flagging and walkthrough; 100% completion |
| 2 | **Menu knowledge** (new menus): tasting session, spec cards, describing three dishes | Server menu quiz ≥90% |
| 3 | **Steps of service** and the 10 moments | Role-play; timings |
| 4 | **Drinks & suggestive selling** (cocktail specs, wine ladder, measures) | Jigger use; spec test |
| 5 | **Complaint recovery (LAST: Listen, Apologise, Solve, Thank)** and empowerment limits | Logged recoveries |
| 6 | **Mystery diner debrief** and refresher | Action plan |

### 6.3 Mystery diner checklist (100 points; monthly per venue)
Use a trusted regular with a £40 voucher, or a mystery-dining service **[verify cost]**. Score 0/1/2 per line, double-weight the starred lines, and scale the total to 100.

1. Google profile shows the menu and correct hours.
2. Phone answered within 5 rings with the venue name.
3. Greeted within 30 seconds.
4. Seated within 2 minutes.
5. **Asked about allergies or dietary needs (critical).**
6. Drinks order within 3 minutes.
7. Server could describe two dishes confidently.
8. A specific recommendation was made.
9. Drinks within 5 or 7 minutes and correct to spec (garnish, glass, ice).
10. Small plates or starters within 12 minutes.
11. Mains within 20 minutes.
12. Food hot.
13. Food matched the description.
14. Seasoning correct.
15. Portion fair.
16. Check-back within 2 minutes.
17. Table cleared promptly.
18. Toilets clean, with a visible check log.
19. Music and lighting appropriate.
20. Bill within 2 minutes of the request.
21. Payment smooth; no tip pressure.
22. Warm farewell and an invitation to return.
23. Value for money (1–10).
24. "Would you return?" and "Would you recommend?" (NPS).
25. One thing that would have made it better.

**Allergen test visit (quarterly).** The diner declares a sesame or gluten allergy and scores the response:
- Was the chef or manager consulted?
- Was written allergen information offered?
- Was the dish flagged on the ticket and delivered by name?
- Was there honest "we can't guarantee" messaging (e.g. on the fryer)?

### 6.4 Allergens: doing it properly (both venues)
**The law and guidance:**
- **Food Information Regulations (14 allergens).** For non-prepacked food, allergen information **must be available**. Currently it can be given verbally, as long as customers are told how to get it.
- **The FSA's best-practice guidance** (Feb/Mar 2025) recommends **written allergen information for every non-prepacked item, plus a conversation** between server and customer ([GOV.UK](https://www.gov.uk/government/publications/allergen-information-for-non-prepacked-foods-best-practice/allergen-information-for-non-prepacked-foods-best-practice); [FSA news](https://www.food.gov.uk/news-alerts/news/updated-industry-guidance-issued-for-food-allergen-information-in-the-out-of-home-sector)). The FSA offers free icons, an allergen matrix and a poster.
- **Natasha's Law** (in force since 1 Oct 2021) requires full ingredient labelling with allergens emphasised on **prepacked-for-direct-sale (PPDS)** food. That applies if Cassiel pre-wraps sandwiches or cakes for display or grab-and-go.
- **Owen's Law** (mandatory menu allergen labelling and asking every customer) is **still a campaign, not law**, as of April 2026 ([Open University](https://www.open.edu/openlearn/health-sports-psychology/owens-law-the-case-written-allergen-information-every-food-business); [Anaphylaxis UK](https://anaphylaxis.org.uk/?p=10506)). Adopt its practices now anyway: it is the direction of travel, and a strong defence.
- **Distance selling (Deliveroo):** allergen information must be available before purchase and at delivery **[verify with FSA guidance]**.

**Evidence of the gap at Cassiel.** Reviews cite **no allergy menu**, and a chef who would not discuss options with a wheat-allergic guest ([Wanderlog review summary](https://wanderlog.com/place/details/3477692)).

**System:**
1. **Allergen matrix for every dish, sub-recipe and drink**, built from recipes plus **supplier spec sheets**. Keep it on paper at each venue, on the website and behind a QR code. Commonly missed allergens:
   - Sesame in tahini, hummus and some buns.
   - Mustard in burger sauce and dressings.
   - Celery in celery salt (Bloody Mary) and stocks.
   - Fish in Worcestershire sauce (Caesar, Bloody Mary).
   - Molluscs in oyster sauce.
   - Egg white in sours.
   - Nuts in orgeat, amaretto and pesto.
   - Milk in cream liqueurs.
   - Sulphites in wine, dried fruit and vinegar.
   - Gluten in beer and in shared fryer oil.
   - Lupin in some flours.
2. **No-substitution rule.** No product swap, including Makro top-ups, until the head chef has updated the matrix. Re-issue the matrix with a version number and date.
3. **Order flow:**
   - The server asks every table.
   - The allergy is entered with an **EPOS allergen modifier that prints in red** on the kitchen ticket.
   - The chef confirms verbally with the server.
   - Prep uses clean, segregated equipment (purple boards and knives) and fresh gloves.
   - The dish is plated separately with an allergen marker.
   - **The person who took the order delivers it** and names the allergen ("This is the sesame-free souvlaki").
4. **Honesty.** Shared fryer oil means no gluten-free chips unless there is a dedicated fryer. Airborne flour in the pizza area means no "GF pizza" claim. If in doubt, **"we're sorry, we can't make that safely"**.
5. **Records.** Log every allergy order in the EPOS report, record staff training, and log any incident or near-miss with a corrective action.
6. **Menus:** allergen icons or a line saying "Allergen guide available. Please speak to us before ordering."

---

## Appendix A: Sources
- National Living Wage £12.71 (April 2026): https://www.restaurantonline.co.uk/Article/2025/11/26/national-living-wage-to-increase-by-41-to-1271/
- NLW, 18–20 rate, NIC and Employment Allowance: https://www.nory.ai/blog/national-living-wage-2026-restaurants ; https://www.theaccessgroup.com/en-gb/hospitality/resources/nic-calculator/
- GP benchmarks: https://www.nory.ai/blog/what-is-a-good-profit-margin-for-restaurants ; https://blog.stocktake-online.com/good-gross-profit-margin-uk-restaurant-2026 ; https://www.netsuite.co.uk/portal/uk/resource/articles/erp/restaurant-benchmarks.shtml ; https://www.morningadvertiser.co.uk/Article/2013/11/14/BBPA-Benchmarking-survey-2013
- Closures, hours cuts and rates: https://www.thecaterer.com/all-content/ukhospitality-warns-of-2076-closures-in-2026 ; https://www.morningadvertiser.co.uk/Article/2026/01/12/hospitality-warns-of-more-than-2000-closures-in-2026-without-urgent-business-rates-reform ; https://www.thedrinksbusiness.com/2026/01/uk-hospitality-faces-rates-reset-and-wage-rise/ ; https://www.thedrinksbusiness.com/2026/02/hospitality-insolvencies-hit-3353-in-2025/ ; https://www.westnorthants.gov.uk/business-rates/new-business-rates-multipliers-1-april-2026
- Labour and cost structure: https://www.cbi.org.uk/media/bkdl4v2b/business-costs-hospitality-cbi-deep-dive.pdf ; https://www.cbi.org.uk/media/extlnkk2/business-costs-beer-pubs-breweries-cbi-deep-dive.pdf ; https://catererlicensee.com/average-pub-faces-78-business-rates-rise-as-wage-inflation-and-vat-stagnation-push-sector-to-breaking-point/ ; https://admin.beerandpub.com/media/03ld0xta/running-a-pub-2026-final.pdf
- Rent: https://morningadvertiser.co.uk/Article/2016/02/16/RICS-Average-new-lease-rent-up-3-year-on-year
- Spend per head: https://www.lumina-intelligence.com/?p=41673
- Menu engineering and psychology: https://beancount.io/blog/2026/07/08/menu-engineering-food-cost-percentage-stars-plowhorses-puzzles-dogs-matrix ; https://en.robotpos.com/restaurant-menu-engineering ; https://www.qsrweb.com/blogs/making-qsr-menus-maximize-profits/ ; https://news.cornell.edu/node/273666
- Break-even: https://pos.toasttab.com/blog/on-the-line/how-to-calculate-break-even-point
- Allergens: https://www.gov.uk/government/publications/allergen-information-for-non-prepacked-foods-best-practice/allergen-information-for-non-prepacked-foods-best-practice ; https://www.food.gov.uk/news-alerts/news/updated-industry-guidance-issued-for-food-allergen-information-in-the-out-of-home-sector ; https://www.open.edu/openlearn/health-sports-psychology/owens-law-the-case-written-allergen-information-every-food-business ; https://anaphylaxis.org.uk/?p=10506
- Ingredient prices: https://www.trolley.co.uk/product/asda-succulent-boneless-chicken-thigh-fillets/EIP782 ; https://rattonpantry.co.uk/collections/cheese/products/latteria-sorrentina-fior-di-latte-bag-cubed-1-5kg ; https://www.brake.co.uk/fresh-produce/potatoes/white-red/white/maris-piper-potatoes/p/450066 ; https://www.rattonpantry.co.uk/collections/caputo%C2%AE
- Suppliers: https://www.betterwholesaling.com/interview-turner-price/ ; https://thenacc.co.uk/partners/premier_partners/turner-price ; https://www.jjfoodservice.com/blog/events/the-history-of-jj-food-service-limited-1988-to-2015 ; https://wholesalemanager.co.uk/jj-encourages-independent-retailers-to-take-advantage-of-chef-quality-foods-and-bulk-savings/
- Stock audit: https://www.morningadvertiser.co.uk/Article/2006/11/30/Setting-the-standard/ ; https://www.rgis.co.uk/case-study/restaurant-monthly-drinks-audit/
- Waste and menu trimming: https://thegrocer.co.uk/news/restaurant-food-waste-improvements-shown-to-hike-profits/576629.article ; https://www.uhy-uk.com/insights/uks-top-100-restaurant-groups-record-profits-ps244-million-past-year-sharp-turnaround
- Exit market: https://www.restaurantonline.co.uk/Article/2026/10/06/christie-co-reports-22-rise-in-pubs-and-restaurants-brought-to-market/ ; https://www.christie.com/news-resources/press-releases/resilient-buyer-demand-drives-strong-transactional-momentum-pubs-h1-2026/
- Venue context (seen as search snippets only): https://wanderlog.com/place/details/3477692 ; https://deliveroo.co.uk/menu/Hull/cottingham-centre/raphs-lounge ; https://hullisthis.news/?p=10272
