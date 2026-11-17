# Field Notes: Bus Agency Booking System (Desk Research + Field Visit Plan)

**Project:** Bus Agency Booking System, a travel agency running buses from Buea Park to Douala (CEF 345, Week 4)
**Prepared:** 2026-11-17
**Method:** Secondary desk research only, i.e. published news, regulator data and travel-planner listings, all listed under Sources with access date. **This is not field research.** No agency visit, interview, survey or observation took place. Nothing here may be read as "the agency said..." or "agents/passengers reported...".
**Status:** Sections 1-6 are desk research. Sections 7-9 are the plan for the real field visit and a template for the real notes (section 9 stays empty until the visit happens).
**Purpose:** Give context and constraints for `docs/srs.md`. These notes do not describe the client's actual procedures. The five problems in the problem statement come from the client brief, not from this research.

Where sources are thin or silent, that is stated rather than filled in.

---

## 1. Route and operating context

- Buea and Douala are about 67 km apart by road, roughly one hour of driving [1].
- Travel-planner listings describe the Buea-Douala link as running through Mile 17 (a motor park on the Buea side), with a local taxi connecting to Buea itself [1]. The client's departure point, "Buea Park", must therefore be confirmed with the client (primary research).
- Fares in the Anglophone regions are set by transport agencies themselves and change with fuel prices. One report shows agencies announcing fare rises, with Bamenda-Buea at 7,500 FCFA and Bamenda-Douala at 6,500 FCFA after the rise [2]. The article's date is not confirmed, so these figures are indicative only and are not for the Buea-Douala route.
- On the Yaoundé-Douala axis, the agencies' professional body announced a "classique" bus fare of 3,500 FCFA [3]. Date not confirmed; different route.
- Travel costs rise around year-end festivities [4], and political unrest has slowed the Buea-Douala corridor [5].

**Implication for the SRS:** fares, routes and schedules vary by season and by agency, so they must be configurable data, never hard-coded. Departures can be delayed or disrupted, so the system should allow a departure to be rescheduled, merged or cancelled.

**Not found:** the actual Buea-Douala fare, number of daily departures and bus sizes for this agency. These are open questions for the field visit.

## 2. Regulation and safety context (relevant to seat limits and manifests)

- Overloading is a recognised problem in Cameroonian interurban transport, and press coverage of major accidents links it to the risk [6][7].
- In a 2024 Ministry of Transport inspection campaign, authorities checked vehicles on the Yaoundé-Douala road and found many violations, including overloading. Some buses were sent back, and agencies were told to give affected ticket-holders another compliant bus [8].
- Authorities carry out checks on interurban companies and motor parks, including whether passenger manifests are properly filled [9].
- Interurban companies are required to fit seat belts, but compliance is reported as low [10].
- Surveillance cameras were installed in 100 interurban buses to help identify causes such as overloading and speeding [11].

**Implication for the SRS:** the "never sell more tickets than seats" rule has a regulatory basis as well as a business one. The system should enforce seat capacity per bus and be able to produce a passenger list (manifest) for each departure. Whether the client must show a manifest to authorities is a question for primary research.

## 3. Payment landscape

- Cameroon's regulator reports about 11.4 million active mobile money subscriptions across MTN Mobile Money and Orange Money in 2024, with sector revenue of about 135.8 billion FCFA [12][13].
- MTN Mobile Money Corporation revenue was about 70.2 billion FCFA and Orange Money about 65 billion FCFA in 2024; transaction volume rose 47.3% [13].
- MTN and Orange dominate. Sources disagree on exact shares, so only the fact that these two lead is relied on [13][14].
- Camtel's planned mobile money service (Blue Money) is a possible new entrant [15].

**Implication for the SRS:** payments recorded by agents should allow cash and mobile money (MTN MoMo, Orange Money) as payment methods, each with a transaction reference. Amounts are whole XAF with no decimals. Whether the client wants online payment or only desk-recorded payment is not known and is an open question.

## 4. Derived design constraints (desk-research-based, not client-confirmed)

- Currency: XAF, whole francs.
- Routes, fares and schedules are configurable data.
- Seat capacity per bus is enforced, and a per-departure passenger list can be produced.
- Departures can be rescheduled, merged or cancelled.
- Payment methods include cash and mobile money, each with a recorded reference.
- Two roles from the use case work: Agent and Manager (Manager inherits Agent's abilities).

## 5. Limitations and gaps

- No visit, interview or observation took place; no primary data was collected.
- **No source was found** on how Cameroonian agencies currently handle parcels, parcel fees by weight, or proof of delivery (problem 3). This is entirely an open question.
- **No source was found** on how agencies currently sell and track seats, so problems 1, 2, 4 and 5 rest on the client brief alone.
- Fare figures are for other routes or have unconfirmed dates, and are used only for context.
- Mobile money market-share figures conflict across sources and are not relied on.
- Regulatory points come from press reports, not legal texts. Confirm with the client or the Ministry of Transport before relying on them.

## 6. Sources (for sections 1-5)

All accessed 2026-11-17.

1. Rome2Rio, Douala to Buea travel options. https://www.rome2rio.com/s/Douala/Buea
2. Mimi Mefo Info, Transport agencies in Anglophone regions increase transport fares. https://mimimefoinfos.com/transport-agencies-in-anglophone-regions-increase-transport-fares/amp/
3. EcoMatin, Transport interurbain: les agences de voyage augmentent le prix du classique sur la ligne Yaoundé-Douala. https://ecomatin.net/transport-interurbain-les-agences-de-voyage-augmentent-le-prix-du-classique-sur-la-ligne-yaounde-douala/
4. Cameroon News Agency (via Ground News), Douala-Buea: Transportation costs surge amid year-end festivities. https://ground.news/article/douala-buea-transportation-costs-surge-amid-year-end-festivities
5. Data Cameroon, Southwest: Post-election violence paralyzes Buea-Douala transport, driving prices up. https://datacameroon.com/southwest-post-election-violence-paralyzes-buea-douala-transport-driving-prices-up/
6. Africanews, Questions after 53 die in bus crash in Western Cameroon (2021). https://www.africanews.com/2021/01/28/questions-after-53-die-in-bus-crash-in-western-cameroon
7. Mimi Mefo Info, Many cheat death after bus veers off road at Bamenda's risky C-bend. https://mimimefoinfos.com/many-cheat-death-after-bus-veers-off-road-at-bamendas-risky-c-bend/amp/
8. Mimi Mefo Info, Transport Minister shocked during surprise road visit (August 2024). https://mimimefoinfos.com/transport-minister-shocked-during-surprise-road-visit-70-of-buses-violate-regulations/amp/
9. Cameroon Tribune, Regional delegation reinforces transport safety checks (2016). https://www.cameroon-tribune.cm/article.html/1157/fr.html/details_2
10. East African Journal of Environment (EANSO), Seat belt usage by bus occupants in Cameroon (2025 study). https://journals.eanso.org/index.php/eaje/article/download/4114/4601/
11. Mimi Mefo Info, Surveillance cameras installed in 100 interurban buses. https://mimimefoinfos.com/?p=52957
12. Cameroon Tribune, Communications électroniques: plus de 1000 milliards de F générés en 2024. https://cameroon-tribune.cm/article.html/74465/fr.html/communications-electroniques-plus-de-1000-milliards-de-f-generes-en-2024
13. Cameroun24, Mobile money, data et nouveaux rapports de force: 2024. https://cameroun24.net/article/71870-mobile-money-data-et-nouveaux-rapports-de-force-2024-l-annee-du-grand-basculement-dans-les-t-l-coms-au-cameroun.html
14. Business in Cameroon, Orange Cameroon claims 4.5 million MoMo users (2019). https://www.businessincameroon.com/telecom/1504-9046-orange-cameroon-claims-4-5-million-momo-users-against-over-5-million-for-mtn
15. The Fintech Times, Mobile Money, Digital and Wider Fintech in Cameroon in 2026. https://thefintechtimes.com/mobile-money-digital-and-wider-fintech-in-cameroon-in-2026/

---

## 7. Open points (gaps the desk research could not fill)

| # | Problem | Gap | Resolve by |
|---|---------|-----|-----------|
| 1 | 3, parcels | No source on how agencies receive, weigh, charge for or prove delivery of parcels | Field visit, Q9-Q12 |
| 2 | 1, 2, 4, 5 | No source on how agencies sell and track seats; these problems rest on the client brief alone | Field visit, Q1-Q8, Q13-Q15 |
| 3 | Fares | Fare articles are for other routes with unconfirmed dates; actual Buea-Douala fare unknown | Ask the agency |
| 4 | Regulation | Whether a manifest must be shown to authorities, and how | Ask the agency |
| 5 | Payments | Whether payment is cash only, or also MoMo, and whether online payment is wanted | Ask the agency |
| 6 | Departure point | Whether "Buea Park" is Mile 17 or another park | Ask the agency |
| 7 | Parcel fee | The tariff (rate per kg, minimum fee) | Ask the agency |
| 8 | Low occupancy | The threshold for a "nearly empty" departure and the deadline for merging or cancelling | Ask the agency |

## 8. Field visit guide (one hour)

**Who and what to observe:** the ticket desk (selling and recording), the parcel counter or area, the boarding point, and how the staff pass information between desks. Note timing, paper or phone records, and any moment where a seat, ticket or parcel could go wrong. Ask permission first and do not photograph customers or records.

**Open questions** (ask in your own words; do not read them out):
1. Walk me through how a passenger buys a ticket, from arrival to receipt.
2. How do you decide which seat a passenger gets?
3. What happens when two passengers are given the same seat?
4. How do you know how many seats are left on a bus?
5. How do the two desks share what they have sold?
6. When do you stop selling tickets for a departure, and who decides?
7. What happens to a passenger who arrives after the bus has left?
8. How do you find out that a departure is nearly empty, and what do you do about it?
9. Walk me through what happens when someone brings a parcel.
10. How do you decide what a parcel costs?
11. What record do you keep of who sent it, who receives it, and when it was delivered?
12. Tell me about a parcel that was lost or disputed. What happened?
13. How do passengers pay, and how do you record it?
14. What reports or totals do you prepare at the end of the day?
15. What is the biggest daily problem you wish you could fix?

## 9. Field visit notes (to be written after the real visit)

*Leave this section empty until the visit happens. Write only what you observed or were told, and mark whose words they are.*

- **Date, time and place of visit:**
- **Who I spoke to (role only):**
- **Seats: how they are sold and tracked:**
- **Closing a departure and late passengers:**
- **Low-occupancy departures:**
- **Parcels: receiving, fee, proof:**
- **The two desks and shared records:**
- **Payments and daily report:**
- **Surprises / things that changed my view of the requirements:**
