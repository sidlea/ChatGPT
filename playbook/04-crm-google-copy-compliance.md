# Data capture, Google, copy bank and compliance

> Part of the Hallgate playbook for Cassiel Bar & Kitchen and Raph's Lounge, Cottingham. Prices, dates and margins are working assumptions (Oct 2026): check them against real recipe costs, licences and calendars before use.


## 7. Data capture, CRM and automation (GDPR/PECR-compliant)

### 7.1 Where the list comes from (target +1,200 opted-in contacts by mid-January)
| Source | How | Expected yield (by 17 Jan) |
|---|---|---|
| **SV Tables bookings** | Turn on (or check) the optional, **unticked** marketing opt-in at booking; make sure the wording names both venues; export or sync contacts weekly (7.5) | 300–500 |
| **Table QR talkers and bill QR** | "Join the Hallgate list: first dibs on Christmas dates and live music, plus a free 0% cocktail or bread & olives next visit." Links to a Wix form (7.2) | 250–400 |
| **Christmas party enquiries and the Organiser Pack** | Every enquiry form has an optional marketing tick (organisers often use work emails; see the note below) | 100–200 |
| **"Win a Christmas party for 10" competition** | Entry form: name, email, group type, size, preferred date + an **optional** marketing tick + short T&Cs | 200–400 entries (about 60% opt in) |
| **Cottingham Christmas Festival** | A QR card handed to every passer-by (about 20k visitors in 2023 [S25]) offering a free mulled wine or mocktail on the next visit | 150–300 |
| **Gift card buyers** | The checkout includes an opt-in. The soft opt-in *may* apply for the same venue's own similar products if an opt-out is offered at checkout [S15], but explicit opt-in is cleaner | 50–150 |
| **WhatsApp Channel followers** | Follow-based (not a contact list); promote on QR talkers and Stories | 450 followers |
| **Guest Wi-Fi portal** (optional) | Only if the router supports a captive portal or you use a vendor such as Purple or Stampede; **separate terms tick and an unticked marketing tick**, with access never conditional on consent [S16] | Bonus |

**Corporate note:** under PECR, B2B emails to *corporate* addresses (for example name@company.co.uk) can be sent without prior consent if you identify yourself and offer an opt-out. Sole traders and partnerships are treated like individuals. UK GDPR still applies (legitimate interest, privacy notice). Keep a separate "B2B" tag (not re-verified in this pass; follow ICO guidance).

### 7.2 Consent wording (copy-ready; use it on every form)
> **Stay in the loop on Hallgate**
> ☐ Yes, send me offers, events and news from **Cassiel Bar & Kitchen** and **Raph's Lounge** by **email**.
> ☐ …and by **SMS / WhatsApp** to the number above.
> Birthday month (optional): [Month ▼]. We'll send you a birthday treat.
> You can unsubscribe at any time. See our [privacy notice] to find out how [Cassiel's company] (Cassiel) and [Raph's company] (Raph's) use your data.

Why it's built this way:
- Two venues are run by **two different companies**, so name both in the wording and in the privacy notice. The privacy notice must say who the controller(s) are and how data is shared between the venues (ask the data/legal workstream to confirm joint-controller wording).
- Keep the boxes **unticked**, with **separate channels**, and **no bundling** with booking terms or competition entry [S16].
- **Record** the timestamp, source (QR, booking, festival), wording version and venue in the CRM sheet. PECR fines now match GDPR levels [S15].
- **Unsubscribe** links on every email, and "STOP" handling on SMS.

### 7.3 The automated flows (build them in Wix Automations, or in n8n plus an email/SMS tool)
| Flow | Trigger | Messages | Offer |
|---|---|---|---|
| **Welcome** | New opted-in contact | T+0: "Welcome to Hallgate" with the code for the free 0% cocktail or bread & olives (30 days). T+3: "Two venues, one street": what each venue is for (positioning in 2.1). T+10: the seasonal call to action (a Christmas party in Oct–Dec, January Joy in Jan) | A low-cost item |
| **Post-visit** | Day after the booking date (from SV Tables) | T+1: "Thanks for coming. How did we do?" with a Google review link (**sent to everyone**). T+14 (if no new booking): "Your next visit: [the next event at the *other* venue]" | None, or a cross-venue nudge |
| **Birthday** | Birthday month minus 21 days | T−21: "Your birthday treat is waiting: book 4+ and the birthday star's cocktail or dessert is on us." T−7: a reminder | A free item |
| **Win-back** | No visit in 60 days (from booking data or loyalty) | D60: "We've changed a few things" (new menu, new nights). D90: a stronger offer (a free starter with 2 mains, Mon–Thu). D150: "Still want to hear from us?" (re-permission or remove) | Escalating, Mon–Thu only |
| **Christmas organiser nurture** | Party enquiry or Organiser Pack request | T+0: pack PDF plus availability. T+2: a personal WhatsApp or call from the ops manager. T+5: "Your date: 2 Fridays left". T+10: the early-bird deadline. Stop as soon as they book | The deadline offers |
| **Gift card buyer** | Purchase | T+0: the e-card plus "how to redeem". Mid-January: a reminder to the *recipient* if their email was captured with permission; buyers get "Your Bonus Card is now live" | The bonus card |
| **Post-Christmas party** | Party date +2 days | A thank-you; "Share your photos #HallgateChristmas"; a review ask; "Lock in 2027 at 2026 prices" (offer #20) | The 2027 lock-in |

### 7.4 Channel rules
- **Email:** the main channel, fortnightly, weekly in December. Subject lines are in the copy bank (9.5).
- **SMS:** deadlines only (31 Oct, 15 Nov, Black Friday, NYE last tickets). 160 characters, with the brand name and STOP.
- **WhatsApp:** use the **Channel** for broadcast-style posts (free). The **Business app** suits one-to-one chats with organisers. API marketing messages cost about £0.05–0.064 each plus fees [S14], so not needed yet.

### 7.5 Plugging the campaigns into the existing n8n + "Content Brain" + Wix AI set-up
**A. Extend the Content Brain (Google Sheet). Add these tabs:**
1. **`Campaign_Calendar`**. Columns: `post_id | week | publish_at | venue (Cassiel/Raphs/Joint) | campaign (XMAS26 / RESET / VOUCHERS / NYE / JANJOY) | pillar (Proof/People/Plans/Place) | platform (IG/FB/TT/GBP/WA/Email) | format (Reel/Carousel/Story/Offer/Event) | hook | caption | cta | link_with_utm | offer_code | asset_url | status (Draft→Approved→Scheduled→Posted) | approver | post_url | reach | sends_shares | saves | link_clicks | bookings_attributed`.
2. **`Offer_Guardrails`**: the rules from 2.3 plus the live offer list (name, venue, days, start, end, price, code). The AI agents must read this before writing anything.
3. **`CRM`** (or Wix Contacts as master; see C). Columns: `contact_id | name | email | phone | consent_email | consent_sms_wa | consent_timestamp | consent_source | consent_wording_ver | venue_first | birthday_month | last_visit | visits | segment_tags (NHS, Organiser, B2B, Family, Gig) | unsubscribed`.
4. **`Party_Pipeline`**: `enquiry_date | organiser | company | size | venue/package | date_requested | status (New/Pack sent/Held/Deposit paid/Pre-order in/Completed) | deposit_£ | next_action_date`.
5. **`Scoreboard`**: the weekly KPIs from 3.5.

**B. n8n workflows to add** (design only; nothing has been built or posted):
| WF | Trigger | Steps |
|---|---|---|
| **WF1 Campaign Scheduler** (extend the existing one) | Every 15 minutes | Read `Campaign_Calendar` rows where status=Approved and publish_at ≤ now → post to the FB Page and IG (Meta Graph API) and to Google Business Profile (Business Profile API local posts, Offer/Event types with dates and code) → write back post_url and status=Posted. TikTok and the WhatsApp Channel stay **manual** (simplest; API posting options are limited or unverified) |
| **WF2 Booking → CRM** | New SV Tables booking email or export | Parse name, email, phone, date, covers, opt-in → upsert `CRM` and Wix Contacts (only consented contacts get marketing labels) → if covers ≥ 8, create a `Party_Pipeline` row and alert the ops manager on WhatsApp or email |
| **WF3 Post-visit and review ask** | Daily at 10:00 | Bookings dated yesterday → send the thank-you plus the Google review link to **all** guests (a transactional/service message; keep any marketing out unless they consented) |
| **WF4 Birthday and win-back** | Daily | Select consented contacts with birthday month starting in 21 days, or last visit = 60/90/150 days ago → trigger the Wix Automation or send the email |
| **WF5 Organiser nurture** | Wix form submission (Christmas enquiry) | Email the pack instantly → create a pipeline row → T+2/T+5/T+10 follow-ups unless status = Deposit paid |
| **WF6 Weekly Scoreboard** | Monday 07:30 | Pull GBP performance metrics (Business Profile Performance API), Meta insights, Google Ads conversions and SV Tables counts → write to `Scoreboard` → email a one-screen summary to the owners and ops manager |
| **WF7 Review radar** (extend the existing approval system) | New Google review | Tag Raph's reviews mentioning food words (frozen, cheese, pizza, chicken, gyros) → feed the relaunch KPI; a 1–2 star review sends an alert to Simon within 1 hour |

**C. Use the Wix AI marketing agent for what Wix does natively:**
- **Landing pages:** "Christmas Parties in Cottingham" (both venues, packages, FAQ, enquiry form), "NYE on Hallgate", "Gift Cards". Ask the agent to optimise them for "christmas party cottingham", "christmas party hull", "restaurants cottingham" and "places to eat cottingham". **A human checks every price, date and allergen claim.**
- **Wix Forms** for the consent form and enquiries; **Wix Automations** for the welcome and birthday flows (if they live in Wix, n8n only syncs the contacts); **Wix Email Marketing** for the fortnightly newsletters (the agent drafts, a human approves).
- **The AI agents' brief** (paste it into both the n8n LLM node and the Wix agent): brand voice per venue (2.1), the `Offer_Guardrails` tab, the rule "never invent prices, dates or dishes; only use rows from the Content Brain", "no AI-generated food photos", "no mention of internal matters".
- **UTM convention** (so bookings can be attributed): `?utm_source={instagram|facebook|tiktok|google|whatsapp|email}&utm_medium={social|organic|cpc|crm}&utm_campaign={xmas26|reset|vouchers|nye|janjoy}&utm_content={post_id}`. Add a "How did you hear about us?" field to SV Tables if possible.

---

## 8. Google Business Profile and Google Ads

### 8.1 Google Business Profile: the free win (do it this week, then every week)
Both profiles are seen by thousands of people a month (Raph's 4,786 views, Cassiel 2,781), but menu views fell about 50% and bookings fell 28–54%. **Fix conversion before buying clicks.**

**One-off fixes (W1):**
- [ ] **Menu:** add the full menu in the Menu editor (items, prices, photos), plus a menu link, plus a Christmas menu. Google is already flagging this gap.
- [ ] **More hours:** kitchen hours, lunch, happy hour ("Two cocktails £15, Mon–Fri until 7pm"), and **holiday hours** for 24–26 Dec, 31 Dec and 1 Jan (set them now, because Google surfaces them). Google is already flagging the missing lunch hours.
- [ ] **Categories:** both venues' biggest search term is "restaurants", so the **primary category should be a restaurant category**. Cassiel: primary "Mediterranean restaurant", secondary "Tapas restaurant", "Cocktail bar", "Bar". Raph's: primary "Pizza restaurant" (or "Bar & grill"), secondary "Live music bar", "Lounge", "Steak house" (only once Steak Night is live). Watch rankings for 4 weeks after the change.
- [ ] **Booking link:** the SV Tables URL with `?utm_source=google&utm_medium=organic&utm_campaign=gbp`. Check whether SV Tables supports Reserve with Google (unverified).
- [ ] **Attributes:** live music, cocktails, vegetarian and vegan options, good for groups, wheelchair access (only if true), Wi-Fi, accepts reservations.
- [ ] **Products:** each Christmas package, gift cards, NYE tickets and the Masterclass, each with price, photo and link.
- [ ] **Description:** use the role lines from 2.1, and mention "Hallgate, Cottingham, near Hull".
- [ ] **Photos:** 10 real, recent photos now (food, the bar, the room, the team, the street), then 3–5 new ones every week.

**Weekly posting rhythm (both venues, about 15 minutes, automated by WF1):**
- **Monday "This week on Hallgate"** (Update post): 3 lines + photo.
- **Offer post** for the current hero offer, with start/end dates, a coupon code and terms [S13]. Use codes to attribute (for example `GOOGLEXMAS`, which gives a free prosecco per 8 when quoted at booking).
- **Event post** for every gig, quiz, NYE and the Christmas Festival day.
- Don't put phone numbers in post text (posts can be rejected); use the call-to-action buttons [S13].

**Reviews:** the target is **5+ new reviews per venue per week**. Ask everyone through WF3 and bill-card QR codes; reply to every review within 48 hours (using the existing approval system).

### 8.2 The new-advertiser credit: how to get it and use it well
- **How these promotions work** (Google's terms [S11]):
  1. The offer must be **activated as a new advertiser**, through the promotion shown at sign-up or in Billing → Promotions.
  2. **The qualifying spend must happen within 60 days.**
  3. Google then takes **up to 35 days** to verify the account is new and apply the credit.
  4. **The credit expires 60 days after it is applied.**
  5. One per customer, and it doesn't cover spend above the credit.
  - Some advertisers have had credits "invalidated" after spending [S11], so **screenshot the offer and terms at sign-up**, use a genuinely new account, and don't create several accounts.
- **The exact UK amount wasn't confirmed** in public sources (one 2024 listing showed "Spend £400 get £400" [S11]). This plan assumes the account offer is roughly **"spend about £380, get £380"**. Check it in the account.
- **The timeline that fits this plan:**
  - Start Search on **about 20 Oct**.
  - Spend about £100 in Oct and about £230 in Nov, so the qualifying spend is reached by **about 5 Dec** (inside the 60-day window, which ends about 19 Dec).
  - The credit lands by about mid-January at the latest.
  - Spend it **Jan to Mar** on "Round Two", Valentine's (Sun 14 Feb), and Mothering Sunday (7 Mar 2027). **The Christmas campaign pays for the spring comeback.**

### 8.3 Search vs Performance Max: use Search
| | **Search (recommended)** | Performance Max (not now) |
|---|---|---|
| Fit for about £8/day, one location | Bids only on high-intent queries ("christmas party hull") | Spreads budget across Display, YouTube and Maps; needs conversion volume to learn; tends to struggle below about $1,000 a month [S12] |
| Control | Keywords, negatives, schedule, radius | Little control; reporting at "asset group" level |
| When to revisit | — | Spring 2027, if conversion tracking (calls, bookings, directions) records **30+ conversions a month**, as a store-goals test [S12] |

### 8.4 Campaign build (copy-ready)
**Campaign 1: "XMAS26 – Christmas Parties"** (20 Oct to 18 Dec; about £5–7/day)
- **Location:** Cottingham, Hull, Hessle, Anlaby, Willerby, Kirk Ella, Beverley (about 10 miles); option **"Presence: people in or regularly in"** (this excludes the *other* Cottinghams in Northamptonshire and Leicestershire).
- **Keywords** (phrase and exact match): "christmas party cottingham", "christmas party hull", "christmas party venues hull", "work christmas party hull", "christmas do hull", "christmas meal cottingham", "christmas party menu hull", "christmas lunch hull", "christmas party ideas hull", "nye hull" (from 16 Nov).
- **Negatives:** jobs, recipe, free, "hull fair", "christmas market", "cottingham leicestershire", corby, "market harborough", "northamptonshire", hotel, "christmas day" (unless you open), "kids party", "party shop", "fancy dress".
- **Ad copy (Responsive Search Ad; lengths checked: headlines ≤30, descriptions ≤90):**
  - **Headlines:** Christmas Parties Cottingham | Christmas Do Near Hull | Festive Menus From £22.95pp | Dinner Here, Party Next Door | Live Band Party Nights | Book Now – Organiser Eats Free | Cocktails & Tapas on Hallgate | Dates Filling Fast – Enquire | Work Christmas Party Hull | Two Venues, 30m Apart
  - **Descriptions:** "Festive tapas, cocktails & live bands, two venues 30m apart on Hallgate, Cottingham." | "Groups 8+, £10pp deposit. Organiser eats free if booked by 15 Nov. Enquire now." | "Dinner at Cassiel, then party at Raph's with a live band. One booking, one great night."
- **Landing page:** the Christmas page (Wix) with packages, the Crawl, an enquiry form and the Organiser Pack download.

**Campaign 2: "EAT – Restaurants Cottingham"** (always on; about £2–3/day; raise in January with the credit)
- **Location:** a 4-mile radius around HU16 4BB, presence only.
- **Keywords:** "restaurants cottingham", "places to eat cottingham", "cottingham restaurants", "bars cottingham", "cocktail bar cottingham", "tapas cottingham", "tapas hull", "pizza cottingham", "steak night hull" (from Jan), "restaurants near me" and "bars near me" (fine within the 4-mile radius), "live music cottingham".
- **Two ad groups:** Cassiel (tapas, cocktails, Mediterranean) and Raph's (pizza, live music; **from 13 Nov only**, after the Kitchen Reset).
- **Headlines:** Restaurants in Cottingham | Places to Eat in Cottingham | Tapas & Cocktails Cottingham | Lunch Tapas 2 for £11.90 | Book a Table on Hallgate | Mediterranean Kitchen & Bar | Proper Cocktails, Hallgate | Live Music & Pizza Nights | New Kitchen at Raph's Lounge
- **Descriptions:** "Mediterranean small plates, grills & proper cocktails in the heart of Cottingham." | "Lunch tapas 2 for £11.90 Mon–Fri. Tapa Nights 3 tapas + a drink £25.90. Book online." | "Live bands, pizza from dough made in-house & cold drinks in Cottingham's old bank."

**Assets for both campaigns:** sitelinks (Christmas Menu, Book a Table, Gift Cards, Live Music, NYE); callouts (Groups Welcome, Live Bands, Real Mozzarella (Raph's, after the fix), Vegan Options); call asset (only during opening hours); **location asset linked to the Google Business Profile**; image assets (real photos); price asset (the Christmas tiers).

**Schedule and bidding:**
- **Schedule:** 10:00–21:00. Increase bids on Thu–Sat 16:00–19:00 (the "where shall we eat tonight" window) and Mon–Thu 09:00–14:00 for the Christmas campaign (office organisers).
- **Bidding:** start on *Maximise clicks* with a max CPC cap of about £1.20. After **15–30 tracked conversions**, switch to *Maximise conversions*. Pause keywords with a CTR below 3% after 200 impressions.

**Conversion tracking (set up before launch):**
1. Clicks on "Book" buttons going out to SV Tables (Google Tag on the Wix site, outbound-click event).
2. Wix enquiry form submissions (Christmas, NYE).
3. Calls from ads (call asset, 30+ seconds).
4. Gift card purchases (Wix thank-you page).
5. Directions and calls from the location asset (reported as local actions).

**Expected outcome:** local queries are low-volume (Google Business Profile shows "cottingham restaurants" at about 67–71 searches a month per venue). Paid ads place you **at the top for the ready-to-book moments**: plan on about 300–600 clicks and about 60–80 tracked conversions over Oct–Dec, at roughly £5–8 per conversion (an estimate to be confirmed after 2 weeks of data).

---

## 9. Copy bank (paste-ready; check prices and dates before posting)

### 9.1 Christmas launch: Instagram/Facebook caption (both, as a Collab post)
> **Two venues. One street. One proper Christmas do. 🎄**
> Dinner at Cassiel. Then 30 steps across Hallgate to Raph's, where the band's already playing.
> 🍷 Festive tapas from £22.95pp
> 🎸 Party Platters & a live band at Raph's from £26.95pp
> ✨ The Hallgate Christmas Crawl: dinner + party, £39.95pp
> **Book by Sat 31 Oct → a free bottle of prosecco for every 8 guests.**
> Organising the work do? Comment **PACK** and we'll DM you our Christmas planner.
> 📍 Hallgate, Cottingham · Book via the link in bio
> #Cottingham #HullChristmas #ChristmasPartyHull #Hallgate #EastYorkshire

### 9.2 Google Business Profile posts
- **Offer (Cassiel):** *Title:* "Festive Tapas Lunch, £22.95pp" · *Details:* "4 festive tapas each, bread & olives and a mini dessert. Mon–Fri 12–4 from 26 Nov. Perfect for a team lunch: back at your desk by 3 (we won't tell)." · *Code:* GOOGLELUNCH · *Dates:* 13 Oct – 23 Dec · *Terms:* "Groups 6+, £10pp deposit, pre-order 14 days ahead." · *Button:* Book
- **Event (Raph's):** *Title:* "Live on Saturday: [Band]" · "Free entry from 8:30pm. Pizza from dough made in-house, cold drinks and good company. Tables bookable." · *Button:* Book
- **Update (Monday):** "This week on Hallgate: Tue Pizza & Pint £14 at Raph's · Wed–Thu Tapa Nights at Cassiel · Thu Quiz at Raph's · Fri Fish Friday at Cassiel + a live band at Raph's."

### 9.3 Facebook community group post (Simon posting as himself, only on the group's permitted day or with admin approval)
> Hi all, Simon here, one of the two brothers who run Cassiel and Raph's on Hallgate. Some of you have told us (fairly!) that the food at Raph's hadn't been good enough. We've rebuilt the kitchen: real mozzarella, dough made on site, chicken marinated and grilled to order. Before we shout about it, we'd love 60 locals to taste it first, **free**, on Tue 3 or Wed 4 Nov. All we ask is your honest verdict on a card. Comment or message me if you'd like a seat. Thanks for supporting Hallgate's independents. 🙏

### 9.4 WhatsApp Channel "Hallgate Insider"
- **Launch:** "👋 Welcome to Hallgate Insider: first dibs on Christmas dates, live music line-ups and last-minute tables at Cassiel & Raph's. 1–3 posts a week, no spam. Say **INSIDER** at the bar this month for free bread & olives."
- **Friday 4pm:** "🔥 Tonight: 2 tables left at Cassiel (7:30, 8:00) and a booth at Raph's for the band (on from 9). Reply here or book: [link]"
- **NYE:** "🎆 Insiders first: NYE on Hallgate tickets are live, 48 hours before anyone else. [link]"

### 9.5 Email subject lines
- "Christmas on Hallgate: dinner here, party next door 🎄"
- "Organiser eats free (if you book by Sunday)"
- "Real mozzarella. Dough made here. Taste the difference."
- "The gift that isn't socks"
- "Black Friday: a £10 bonus with every £50 gift card"
- "NYE: two venues, one midnight"
- "January, but make it joyful"
- "Your birthday treat is waiting 🎂"

**Sample email ("Christmas on Hallgate"):**
> **Two venues. One street. One proper Christmas do.**
> Hi [First name],
> This year you don't have to choose between a good dinner and a good party. Eat at **Cassiel** (festive tapas, cocktails), then walk 30 steps across Hallgate to **Raph's**, where the band's already on.
> **Festive Tapas Lunch** £22.95 · **Festive Tapas Feast** from £29.95 · **Party Platters & Band** £26.95 · **Hallgate Christmas Crawl** £39.95
> 🎁 Book by **Sat 31 Oct** for a free bottle of prosecco per 8 guests. Book by **Sun 15 Nov** and the organiser eats free (12+).
> [See menus & book] · [Get the Organiser Pack]
> Simon & Chris
> *You're receiving this because you opted in at Cassiel or Raph's. [Unsubscribe]*

### 9.6 SMS (all under 160 characters, GSM-safe; links are placeholders for pages to create)
- "Cassiel & Raph's: Christmas parties on Hallgate. Book by Sat 31 Oct = free prosecco per 8 guests. cassielbar.co.uk/christmas Reply STOP to opt out" (146)
- "Hallgate Black Friday: buy a £50 gift card, get a £10 bonus card (use 11 Jan-31 Mar). Fri-Mon only: cassielbar.co.uk/gift STOP to opt out" (137)
- "NYE on Hallgate: last tickets for Raph's party (£15) & Cassiel's 8:30 supper. Book now: raphslounge.co.uk/nye Reply STOP to opt out" (131)
- "Raph's Lounge: new kitchen, real mozzarella, dough made here. Free dough balls with every pizza 14-17 Jan. Book: raphslounge.co.uk STOP to opt out" (146)

### 9.7 Reply template for a 1-star review (Raph's; post only once the changes are real)
> Hi [Name], thank you for taking the time to write this, and I'm sorry. You paid good money and it wasn't good enough. You're right about [the chicken / the tzatziki / value for money]. Since your visit we've [switched to real mozzarella / started making our dough here / marinated chicken thigh, grilled to order / tzatziki made fresh every day] and cut the menu so we can do every dish properly. I'd genuinely like the chance to show you the difference. Please ask for me next time, or drop us a message via our website. Simon (co-owner)

*(Keep it under 80 words, specific, not defensive, with no offer of freebies in public. Make any goodwill gesture privately.)*

### 9.8 A-boards, windows and table talkers
- **A-board (Cassiel):** "CHRISTMAS ON HALLGATE · Festive tapas from £22.95 · Dinner here, party over the road at Raph's 🎸 · Ask inside or scan ▶ [QR]"
- **A-board (Raph's):** "LIVE TONIGHT: [Band] · Pizza from dough made in-house · Christmas parties from £26.95 · Free entry"
- **Table talker (both):** "Join the Hallgate list 📲 First dibs on Christmas dates and gigs, plus a **free 0% cocktail or bread & olives** on your next visit. Scan ▶ [QR] · 30 seconds · Unsubscribe anytime."

### 9.9 Competition: "Win a Christmas party for 10" (short-form T&Cs; adapt with the legal workstream)
> Promoter: [company name], Hallgate, Cottingham. Open to UK residents aged 18+, excluding staff and their families. Enter by completing the form at [link] by 23:59 on 30 Nov 2026. One entry per person. No purchase necessary. One winner drawn at random on 1 Dec 2026 and notified by email within 48 hours; announced on our social channels with consent. Prize: the Festive Tapas Feast **or** Party Platters & Band for up to 10 people (a non-alcoholic drink alternative is available), on a Sun–Thu date in Dec 2026 or Jan 2027, subject to availability. No cash alternative. Marketing opt-in is optional and doesn't affect entry. Not affiliated with Instagram, Facebook or TikTok.

### 9.10 Organiser Pack (outline of the 4-page PDF)
1. "Two venues, one street": the Crawl explained with a simple map of the 30 metres.
2. Packages and prices, a sample menu per venue, and a dietary and allergen promise.
3. Timings (lunch at 1pm, evening at 6pm/8:30), deposits, a pre-order form link, and FAQs (accessibility, parking, trains: Cottingham station is about 10 minutes' walk (unverified), taxis).
4. The deadlines (31 Oct, 15 Nov), and "Hold a date for 48 hours: reply to this email."

---

## 10. Compliance quick-check (before anything goes live)
| Area | Rule of thumb | Source / status |
|---|---|---|
| Email, SMS and WhatsApp marketing | Explicit, unticked, channel-specific consent that names both venues; soft opt-in only for the same company's own similar products, with an opt-out at collection; unsubscribe in every message | [S15] |
| Guest Wi-Fi | Separate marketing consent; never a condition of access | [S16] |
| Drinks promotions | No unlimited or "all you can drink" offers; fixed quantities; food; table service; time limits; staff briefed (Licensing Act mandatory conditions) | [S17] |
| NYE and late hours | Check the licence's permitted hours; any TEN needs at least 10 working days' notice (standard), so submit by about 1 Dec | (Licensing Act 2003; not re-verified) |
| Reviews | Ask everyone; no incentives; no gating; no fake reviews (Google policy; DMCC Act 2024) | (not re-verified) |
| Influencers | #ad or #gifted on gifted or paid content (ASA/CMA) | (not re-verified) |
| Competitions | Clear T&Cs; no purchase necessary or clearly stated; winner selection documented (CAP Code section 8) | (not re-verified) |
| Food descriptions | Describe every ingredient exactly as it is; no "all fresh" claims unless true; allergen information available for all 14 allergens | (trading-standards advice recommended) |
| Gift cards | State the expiry; agree the multi-purpose voucher VAT treatment and any inter-company settlement with the accountant | (accountant to confirm) |
| AI content | No AI-generated images of dishes (misleading); a human approves prices, dates and allergens | ASA/CAP principle |

---


## 12. Sources
*(Accessed 13 Oct 2026 through web-search summaries; full-page fetches were blocked in this environment.)*
- **[S1]** Lumina Intelligence, "UK Eating Out Market Shrinks but Intentional Diners Drive Opportunity" (press release, May 2026): https://www.lumina-intelligence.com/wp-content/uploads/2026/05/159.UK-Eating-Out-Market-Shrinks-but-Intentional-Diners-Drive-Opportunity.docx ; Morning Advertiser, "Pubs under pressure as eating out growth slows in 2026" (27 May 2026): https://www.morningadvertiser.co.uk/Article/2026/05/27/pubs-under-pressure-as-eating-out-growth-slows-in-2026/ ; Lumina press hub: https://www.lumina-intelligence.com/press/
- **[S2]** Lumina Intelligence, "UK alcohol trends 2026": https://www.lumina-intelligence.com/blog/uk-alcohol-trends-2026/
- **[S3]** Morning Advertiser, "Xmas bookings fall 1% as operators brace for late demand" (Dojo data, 11 Dec 2025): https://www.morningadvertiser.co.uk/Article/2025/12/11/festive-hospitality-bookings-drop-1-as-operators-prepare-for-late-christmas-demand/ ; Morning Advertiser, "Where you need to be with Christmas planning" (15 Sep 2025): https://morningadvertiser.co.uk/Article/2025/09/15/pubs-urged-to-prep-early-for-festive-bookings-boost/ (Zonal +8% figure: a secondary mention, verify)
- **[S5]** VenueScanner, "2026 UK Christmas party booking trends businesses need to know": https://www.venuescanner.com/blog/2026-uk-christmas-party-booking-trends-businesses-need-to-know
- **[S6]** Alcohol Change UK, "UK brings a Jan-do attitude to better health and wellbeing in 2026": https://alcoholchange.org.uk/blog/uk-brings-a-jan-do-attitude-to-better-health-and-wellbeing-in-2026
- **[S7]** Veganuary, "Veganuary 2026 results": https://veganuary.com/veganuary-2026-results/ ; YouGov, "How many people intend to go vegan for January 2026": https://yougov.com/en-gb/articles/53780-how-many-people-intend-to-go-vegan-for-january-2026 ; DJS Research: https://djsresearch.co.uk/insights/nearly-one-in-five-brits-embrace-veganuary-according-to-new-research
- **[S8]** TechCrunch, "TikTok rolls out a Nearby feed… in select countries" (4 Dec 2025): https://techcrunch.com/?p=3072760 ; TikTok Newsroom, "Introducing the Local feed" (11 Feb 2026): https://newsroom.tiktok.com/introducing-the-local-feed ; SEO-Day commentary: https://www.seo-day.de/news/article/why-tiktok-deserves-a-place-in-your-seo-strategy?lang=en
- **[S9]** SocialPilot, "Instagram Reels Algorithm (Aug 2026)": https://www.socialpilot.co/es/blog/instagram-reels-algorithm ; PostEverywhere, "How the Instagram algorithm works in 2026": https://posteverywhere.ai/blog/how-the-instagram-algorithm-works ; Metricool Reels guide 2026: https://metricool.com/instagram-reels-guide/ (secondary sources; Mosseri's signals from Jan 2025)
- **[S10]** Tablein, "Restaurant social media marketing trends": https://www.tablein.com/blog/restaurant-social-media-marketing-trends ; Emplifi, "Restaurant social media strategy": https://emplifi.io/resources/blog/restaurant-social-media-strategy/ ; Resy: https://blog.resy.com/?p=52433 ; Irish Times, "The camera eats first" (Nov 2024): https://www.irishtimes.com/food/restaurants/2024/11/05/the-camera-eats-first-the-impact-of-tiktok-on-irelands-restaurant-scene/
- **[S11]** Google Ads Help, "Google Ads promotional offers": https://support.google.com/google-ads/answer/2393021 ; Google promotional credit terms: https://www.google.com/ads/coupons/terms/ ; Search Engine Land, "Advertisers report Google Ads credits being revoked after spending": https://searchengineland.com/advertisers-report-google-ads-credits-being-revoked-after-spending-488330 ; DoDropshipping, free ad credits 2026 (UK tier listing, dated): https://dodropshipping.com/free-ad-credits-for-marketing/
- **[S12]** Google Ads Help, "Optimization tips for Performance Max for store goals": https://support.google.com/google-ads/answer/13775728 ; "About Performance Max campaigns": https://support.google.com/google-ads/answer/10724817 ; Chatterbuzz, "When PMax is wasting your budget": https://www.chatterbuzzmedia.com/blog/performance-max-campaigns/ ; NAV43, "Search vs Performance Max (2026)": https://nav43.com/blog/search-vs-performance-max-for-lead-gen-scale-guide-2026
- **[S13]** Katalyst, "Google Business Profile for restaurants": https://www.katalystos.com/blog/google-business-profile-for-restaurants ; Wiremo, "GBP posts best practices": https://wiremo.co/blog/google-business-profile-posts-best-practices/
- **[S14]** Hyperleap, "WhatsApp Business API pricing calculator (UK, 2026)": https://hyperleap.ai/whatsapp-pricing-calculator-uk ; ChatDaddy, "WhatsApp Marketing UK (2026)": https://chatdaddy.tech/blog/whatsapp-marketing-uk ; Lilach Bullock: https://www.lilachbullock.com/whatsapp-business-cost-per-message-sent/
- **[S15]** GOV.UK, "Data (Use and Access) Act 2025 factsheet: PEC Regulations": https://www.gov.uk/government/publications/data-use-and-access-act-2025-factsheets/data-use-and-access-act-factsheet-pec-regulations ; Mills & Reeve (MFMac), "DUAA 2025: increased maximum fines": https://www.mfmac.com/insights/data-protection/data-use-and-access-act-2025-increased-maximum-fines-for-cookies-and-direct-marketing-practices/ ; GDPRLocal, "Soft opt-in": https://gdprlocal.com/existing-customers-the-soft-opt-in/ ; Slaughter and May, "Lessons from ICO direct marketing enforcement": https://slaughterandmay.com/media/ffqd0nme/consents__records_and_disguises___lessons_from_ico_direct_marketing_enforcement_actions_3629pdf.pdf
- **[S16]** Purple, "GDPR and guest WiFi compliance guide": https://www.purple.ai/en-gb/guides/gdpr-and-guest-wifi-compliance-guide-for-venue-marketers-and-it ; Stampede docs, "GDPR-compliant data capture": https://wir.stampede.ai/docs/product/wifi/gdpr-compliant-data-capture
- **[S17]** Morning Advertiser, "Bottomless brunches: the legal risks operators must avoid" (8 Apr 2026): https://www.morningadvertiser.co.uk/Article/2026/04/08/bottomless-brunches-the-legal-risks-operators-must-avoid ; Portsmouth City Council licence review (Southsea Brunch Klub): https://democracy.portsmouth.gov.uk/mgAi.aspx?ID=23573 ; The Caterer, "Irresponsible alcohol promotion": https://www.thecaterer.com/business/advice/irresponsible-alcohol-promotion-wake-up-call
- **[S18]** DineOpen, "Deliveroo vs Just Eat vs Uber Eats commission 2026": https://www.dineopen.com/blog/deliveroo-vs-just-eat-vs-uber-eats-commission-2026 ; Whito, "UK takeaway marketing costs": https://whito.co.uk/takeaways/research/uk-takeaway-marketing-costs/
- **[S19]** GetApp, Stamp Me: https://www.getapp.com/all-software/a/stamp-me/ ; Stamp Me UK: https://www.stampme.com/uk ; GetApp, Loyalzoo: https://www.getapp.com/marketing-software/a/loyalzoo
- **[S20]** Blue Light Card, "Keep it local FAQs": https://www.bluelightcard.co.uk/en/keep-it-local-faqs
- **[S21]** Sovran, "Restaurant Facebook Ads: a 2026 ROI playbook": https://sovran.ai/blog/restaurant-facebook-ads ; GrowWithSakib, "Meta ads for local businesses": https://growwithsakib.com/meta-ads-for-local-business/
- **[S22]** Hotel Executive / Gifted (Journey Hospitality), voucher seasonality: https://hotelexecutive.com/newswire/71464/vouchers-gift-hotels-a-boom-to-business ; Buybox 2025 Tourism & Travel report: https://content.buybox.net/hubfs/RAPPORT%20EN%202025/2025%20Report%20Tourism%20Travel%20EN.pdf
- **[S23]** Wikipedia, "Hull Fair": https://en.wikipedia.org/wiki/Hull_Fair ; Hull City Council, "Hull Fair returns for 2025": https://news.hull.gov.uk/10/10/2025/hull-fair-returns-for-2025/
- **[S24]** Galactic Fireworks, "UK Bonfire Night events 2026": https://www.galacticfireworks.co.uk/blogs/occasions/uk-bonfire-night-events-2026
- **[S25]** Cottingham Parish Council, "Cottingham Christmas Festival": https://www.cottinghamparishcouncil.org.uk/uncategorised/cottingham-christmas-festival ; "Cottingham Day & Christmas Festival": https://cottinghamparishcouncil.org.uk/council-facilities/cottingham-day ; Mumbler, East Yorkshire switch-ons (2023): https://hullandeastriding.mumbler.co.uk/?p=30232
- **[S26]** MCR Property Group, "Acquires former University of Hull sites The Lawns & Ferens Hall": https://www.mcrproperty.com/articles/mcr-property-group-acquires-former-university-of-hull-sites-the-lawns-ferens-hall ; Wikipedia, "The Lawns": https://en.wikipedia.org/wiki/The_Lawns
- **[S27]** Humber Health Partnership (via NLG NHS site): https://www.nlg.nhs.uk/?p=11071
- **[S28]** Collabstr, Hull influencer directory: https://collabstr.com/top-influencers/in/united-kingdom/hull
- **[S29]** Trustpilot, Sugarvine Tables reviews: https://at.trustpilot.com/review/sugarvinetables.com?page=2
- **[S30]** Yorkshire Post, "New venture in former bank… Cottingham" (Raph's opening background): https://www.yorkshirepost.co.uk/business/new-venture-in-former-bank-set-to-provide-boost-for-englands-largest-village-3269455
