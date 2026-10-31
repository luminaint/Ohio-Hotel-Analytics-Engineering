# Business Questions and Findings

*Hotel booking analysis: 2,500 bookings with arrival dates from 1 January 2024 to 25 October 2026. Revenue means room revenue (nightly rate × nights) and is shown in dollars. With 2,500 bookings, differences between small groups (fewer than about 150 bookings) may be due to chance; no statistical significance tests were run.*

---

### Business Question 1: How much revenue do cancellations cost the hotel?

**What we did**

We counted how many bookings were canceled and added up the room revenue those bookings would have brought in, then compared it with the revenue from guests who actually stayed.

**Results**

| KPI | Value |
|---|---|
| Bookings | 2,500 |
| Cancellation rate | **16.0%** |
| Room revenue earned (guests who stayed) | **\$553,938** |
| Room revenue lost to cancellations | **\$104,640** |
| Share of all booked room revenue lost | **15.9%** |
| Of that, from "Non Refund" bookings (the hotel keeps the deposit) | \$1,278 |
| **Realistic loss** (excluding Non Refund bookings) | **about \$103,362** |

**What we learned**

About 1 in 6 bookings is canceled, and those cancellations represent about 16 of every 100 dollars of booked room revenue. Almost none of the loss is covered by non-refundable deposits, so nearly all of the \$104,640 is a real loss. Even so, this is an upper limit: it assumes every canceled room stayed empty, and some were probably resold.

**Business takeaway**

Cancellations cost the hotel roughly one-sixth of its booked room revenue, and almost none of that is protected by a deposit.

---

### Business Question 2: Which booking channels lose the most revenue to cancellations?

**What we did**

We compared each market segment (how the booking came in) on cancellation rate and revenue lost.

**Results**

![Revenue lost to cancellations by market segment](images/03_lost_revenue_by_segment.png)

| Market segment | Bookings | Cancellation rate | Revenue lost |
|---|---|---|---|
| Online Travel Agent (booking websites) | 938 | **20.7%** | **\$55,676** |
| Direct (hotel website or phone) | 890 | 10.9% | \$28,492 |
| Groups | 147 | **29.9%** | \$8,270 |
| Corporate | 334 | 11.1% | \$8,192 |
| Offline Travel Agent / Tour Operator | 133 | 15.0% | \$3,941 |
| Complementary | 58 | 12.1% | \$68 |

**What we learned**

- **Online Travel Agents cause 53% of all lost revenue.** They bring 38% of bookings but cancel almost twice as often as Direct bookings (20.7% vs 10.9%).
- **Groups have the highest cancellation rate (29.9%)**, but they are a small segment (147 bookings), so they account for only 8% of lost revenue.
- Direct and Online Travel Agent bookings arrive in similar numbers (890 vs 938), yet Online Travel Agents lose almost twice as much revenue (\$55,676 vs \$28,492).

**Business takeaway**

Booking websites are the main source of lost revenue, because they cancel far more often than guests who book direct.

---

### Business Question 3: Which channels are actually worth the most once cancellations are counted?

**What we did**

We plotted each segment's average nightly price against its cancellation rate. We also calculated **revenue per booking made**: revenue actually earned divided by all bookings, including canceled ones. This shows what one booking from a channel is really worth.

**Results**

![Market segments: price vs. cancellation risk (bubble size = bookings)](images/06_segment_price_vs_cancel.png)

*Top-left is best: high price, few cancellations.*

| Market segment | Bookings | Avg nightly price | Cancellation rate | Revenue per booking made |
|---|---|---|---|---|
| Offline Travel Agent / Tour Operator | 133 | \$108.43 | 15.0% | **\$259.65** |
| Direct | 890 | \$110.41 | 10.9% | \$242.75 |
| Online Travel Agent | 938 | \$113.40 | 20.7% | \$232.99 |
| Corporate | 334 | \$87.66 | 11.1% | \$188.19 |
| Groups | 147 | \$88.74 | 29.9% | \$146.50 |

By distribution channel, Direct bookings cancel 11.0% of the time compared with 21.2% for travel agents and tour operators, but revenue per booking made is almost the same (\$228.34 vs \$225.46).

**What we learned**

Online Travel Agent bookings carry the highest nightly price (\$113.40), but because they cancel twice as often as Direct bookings, each Direct booking ends up worth slightly more (\$242.75 vs \$232.99, about 4% more). Offline Travel Agents show the highest value per booking (\$259.65), but with only 133 bookings that result is not reliable. Groups are worth the least per booking (\$146.50) because of their high cancellation rate and lower price.

The analysis did not include travel agent commissions, so the real value of agent bookings is lower than shown.

**Business takeaway**

Direct bookings match booking websites on value while cancelling half as often, which makes them the more dependable channel.

---

### Business Question 4: Do bookings made further in advance cancel more often?

**What we did**

We grouped bookings by how many days ahead they were made (lead time) and compared cancellation rates and lost revenue.

**Results**

![Cancellation rate by how far ahead the booking was made](images/04_cancel_rate_by_lead_time.png)

| Booked ahead | Bookings | Cancellation rate | Revenue lost |
|---|---|---|---|
| 0-7 days | 1,171 | **11.7%** | \$38,939 |
| 8-30 days | 908 | 17.0% | \$38,785 |
| 31-90 days | 336 | 22.9% | \$20,527 |
| 91-180 days | 85 | **36.5%** | \$6,389 |

**What we learned**

Cancellation risk rises at every step. A booking made 91 to 180 days ahead is about 3 times as likely to cancel as one made in the last week (36.5% vs 11.7%). Most guests book close to arrival: almost half of all bookings (47%) are made within a week, and the typical (median) booking is made 9 days ahead. **Bookings made 31 or more days ahead are 17% of all bookings but 26% of lost revenue (\$26,916).** No booking in this data was made more than 179 days ahead.

The 91-180 day group has only 85 bookings, so its exact rate is less certain, but the upward pattern holds across all four groups.

**Business takeaway**

The further ahead a guest books, the more likely they are to cancel, and the hotel knows this at the moment of booking.

---

### Business Question 5: Do early bookers pay more or less?

**What we did**

We compared the average nightly price and revenue per booking made across the same lead-time groups.

**Results**

![Price and cancellation rate by lead time](images/10_price_and_cancel_by_lead_time.png)

| Booked ahead | Avg nightly price | Revenue per booking made |
|---|---|---|
| 0-7 days | \$104.60 | **\$231.72** |
| 8-30 days | **\$106.22** | \$225.75 |
| 31-90 days | \$103.05 | \$195.35 |
| 91-180 days | \$93.67 | \$140.86 |

**What we learned**

Early bookers pay less, not more. Bookings made 91 to 180 days ahead pay the lowest average price (\$93.67) and are also the most likely to cancel, so each one is worth only \$140.86, about 40% less than a last-minute booking (\$231.72). Bookings made within 30 days are the most valuable.

**Business takeaway**

Far-ahead bookings are both cheaper and less reliable, so they deserve the strictest booking terms.

---

### Business Question 6: What other booking details signal that a guest will cancel?

**What we did**

We compared cancellation rates by customer type, whether the guest had canceled before, deposit type, and how many special requests the guest made.

**Results**

| Booking detail | Group | Bookings | Cancellation rate |
|---|---|---|---|
| Customer type | Group | 147 | **29.9%** |
| | Transient (individual) | 1,979 | 15.7% |
| | Transient-Party | 237 | 13.5% |
| | Contract | 137 | 8.8% |
| Canceled before? | Yes | 141 | **22.0%** |
| | No | 2,359 | 15.6% |
| Deposit type | No Deposit | 2,357 | 16.5% |
| | Refundable | 47 | 8.5% |
| | Non Refund | 96 | 5.2% |

![Cancellation rate by number of special requests](images/07_cancel_rate_by_special_requests.png)

| Special requests | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| Cancellation rate | 16.0% | 16.6% | 13.6% | 15.4% |

**What we learned**

- **Group bookings cancel the most (29.9%)**, more than three times the rate of Contract guests (8.8%).
- **Guests who canceled before are more likely to cancel again** (22.0% vs 15.6%), but they are only 6% of bookings.
- **Deposits line up with fewer cancellations.** Non-refundable bookings cancel 5.2% of the time and refundable ones 8.5%, compared with 16.5% for bookings with no deposit. Bookings with no deposit make up 94% of bookings and **99% of the realistic loss**. The deposit groups are small (96 and 47 bookings), and this shows a link, not proof that a deposit causes guests to cancel less.
- **Special requests do not predict cancellations here.** Rates stay between 13.6% and 16.6% whatever the number of requests.

**Business takeaway**

Group bookings, repeat cancelers and bookings with no deposit are the clearest warning signs; special requests are not.

---

### Business Question 7: When is demand highest, and do prices keep up?

**What we did**

We compared guest arrivals and average nightly price by month. The data covers January 2024 to October 2026, so January to October appear in three years and November and December in two. We divided each month's arrivals by its number of years so every month is compared fairly.

**Results**

![Demand vs. price by month](images/05_demand_vs_price_by_month.png)

| Month | Arrivals per year | Avg nightly price | Cancellation rate | Revenue per year |
|---|---|---|---|---|
| January | **42** | \$83.83 | 18.2% | **\$8,850** |
| February | 47 | **\$82.28** | 14.0% | \$11,532 |
| March | 55 | \$93.28 | 18.4% | \$12,547 |
| April | 57 | \$97.55 | 15.4% | \$13,838 |
| May | 64 | \$105.96 | 13.6% | \$17,934 |
| June | 81 | \$118.75 | 15.6% | \$23,651 |
| July | 85 | \$121.41 | 15.3% | \$24,911 |
| **August** | **87** | **\$121.67** | 13.3% | **\$25,721** |
| September | 66 | \$102.17 | 16.4% | \$15,918 |
| October | 59 | \$105.39 | 17.3% | \$16,009 |
| November | 44 | \$92.00 | 17.1% | \$10,885 |
| December | 44 | \$84.38 | **22.3%** | \$9,717 |

**What we learned**

- **Summer is the peak.** June to August bring the most arrivals and the highest prices; August leads on both (87 arrivals per year at \$121.67).
- **Prices already follow demand.** The months with more guests are the months with higher prices, so there is no obvious underpriced busy month.
- **Winter is the low season.** January has half of August's arrivals and earns about a third of August's revenue (\$8,850 vs \$25,721 per year). February has the lowest price (\$82.28).
- **December has the highest cancellation rate (22.3%).**

October 2026 is only partly in the data (it ends on 25 October), so October's figures are slightly understated.

**Business takeaway**

The hotel's pricing already tracks the summer peak; the opportunity is in filling the November to March low season.

---

### Business Question 8: Which types of guests bring the most revenue per stay?

**What we did**

For guests who actually stayed, we compared average length of stay, nightly price, and total room revenue per stay by customer type.

**Results**

![Average revenue per stay by customer type](images/08_revenue_per_stay_customer_type.png)

| Customer type | Stays | Avg nights | Avg nightly price | Revenue per stay |
|---|---|---|---|---|
| Transient (individual) | 1,668 | 2.57 | \$106.90 | **\$272.56** |
| Transient-Party | 205 | 2.40 | \$107.25 | \$258.48 |
| Group | 103 | 2.39 | \$89.87 | \$209.08 |
| Contract | 125 | 2.28 | \$87.81 | \$198.22 |

**What we learned**

Individual (Transient) guests are the hotel's main business, with 1,668 of 2,101 completed stays, and they bring the most revenue per stay (\$272.56). That is 38% more than Contract guests (\$198.22), who pay the lowest nightly price. Stay lengths are similar across all types (2.3 to 2.6 nights), so the difference comes mostly from price.

**Business takeaway**

Individual guests are both the largest and the most valuable group per stay.

---

### Business Question 9: How valuable are repeat guests?

**What we did**

We compared returning guests with first-time guests on share of bookings, cancellation rate, nightly price, and revenue per booking made.

**Results**

| Guest type | Share of bookings | Cancellation rate | Avg nightly price | Revenue per booking made |
|---|---|---|---|---|
| First-time | 90.7% | 16.3% | \$105.19 | \$223.77 |
| Repeat | 9.3% | **12.9%** | \$98.95 | \$200.10 |

**What we learned**

Repeat guests are about 1 in 11 bookings. They cancel a little less often than new guests (12.9% vs 16.3%) but pay about \$6 less per night, so each repeat booking brings in about 11% less revenue. The data does not include marketing or customer acquisition costs, so it cannot show whether keeping a repeat guest is cheaper than winning a new one.

**Business takeaway**

Repeat guests are slightly more reliable but not currently more valuable per booking.

---

### Business Question 10: Where do the hotel's guests come from?

**What we did**

We counted guests (adults, children and babies) on bookings that were not canceled, by home country.

**Results**

![Top countries by number of guests](images/02_top10_countries_guests.png)

| Country | Guests | Share |
|---|---|---|
| United States | 3,688 | **90%** |
| Canada | 187 | 5% |
| Mexico | 61 | 1% |
| India | 58 | 1% |
| United Kingdom | 56 | 1% |
| Germany | 33 | 1% |

**What we learned**

The hotel is almost entirely a domestic business: 9 in 10 guests come from the United States, and only six countries appear among guests who stayed. Canada is a distant second at 5%.

**Business takeaway**

Marketing and pricing decisions should be built around U.S. travelers, who make up nearly all of the demand.

---

### Business Question 11: Which countries bring revenue and actually show up?

**What we did**

The analysis compared revenue and cancellation rates for countries with at least 1,000 bookings, so that small countries would not produce misleading rates.

**Results**

| Country | Bookings | Cancellation rate | Revenue earned | Revenue lost | Revenue per booking made |
|---|---|---|---|---|---|
| United States | 2,252 | 15.9% | \$499,858 | \$90,881 | \$221.96 |

**What we learned**

Only the United States meets the 1,000-booking threshold, so **this question cannot be answered with the current data**: there is no second country to compare against. The U.S. results simply mirror the hotel overall (15.9% cancellation vs 16.0%). Comparing countries would need a lower threshold, which would mean comparing groups of fewer than 250 bookings, or more international data.

**Business takeaway**

Country is not a useful way to segment this hotel's guests yet.

---

### Business Question 12: Where are the opportunities to sell more?

**What we did**

We looked at how often guests ended up in a different room type than they reserved, and compared revenue per booking by meal plan and parking requests.

**Results**

| Booking detail | Group | Bookings | Cancellation rate | Avg nightly price | Revenue per booking made |
|---|---|---|---|---|---|
| Room type changed | Yes (0.9% of bookings) | 23 | 4.3% | \$135.95 | \$485.09 |
| | No | 2,477 | 16.1% | \$104.32 | \$219.13 |
| Meal plan | Self catering | 1,335 | 16.4% | \$104.33 | \$218.59 |
| | Bed and breakfast | 1,087 | 15.7% | \$105.19 | \$224.71 |
| Parking requested | 1 space | 1,699 | 15.7% | \$104.42 | \$226.72 |
| | None | 676 | 16.6% | \$104.86 | \$212.83 |
| | 2 spaces | 125 | 16.0% | \$105.87 | \$198.98 |

**What we learned**

- **Room changes are rare.** Only 23 bookings (0.9%) ended up in a different room type. Those guests paid more (\$135.95 per night), but the group is too small to size an upgrade program.
- **Meal plans barely differ.** Guests choose only self catering (53%) or bed and breakfast; there is no half-board or full-board option in the data, and the two plans are worth almost the same per booking (\$218.59 vs \$224.71).
- **Most guests want parking.** 68% of bookings request one parking space, and these bookings are worth slightly more per booking than those without parking (\$226.72 vs \$212.83).
- The data does not record meal or parking revenue, so the value of any add-on cannot be measured directly.

**Business takeaway**

The data does not show a strong add-on opportunity yet; parking is in high demand, but its value cannot be measured without parking revenue data.

---

# Recommendations

These are **proposed actions** based on the findings above. None has been tested, so every benefit below is expected, not proven.

**1. Ask for a partial deposit, or send a reconfirmation email, for bookings made 31 or more days ahead.**

- **Evidence:** Cancellation rates rise from 11.7% to 36.5% with lead time; bookings made 31+ days ahead are 17% of bookings but 26% of lost revenue (Question 4). Far-ahead bookings are also the cheapest (Question 5). Bookings with no deposit carry 99% of the realistic loss, while deposit bookings cancel less (Question 6).
- **Business value:** Expected to reduce cancellations in the riskiest window and release rooms earlier for resale, while leaving last-minute guests (47% of bookings) untouched.
- **Success metric:** Cancellation rate and lost revenue for bookings made 31+ days ahead, plus booking volume in that window.
- **Priority:** High. Test it on a sample first, because a deposit could discourage some early bookers.

**2. Negotiate stricter cancellation terms with online travel agents.**

- **Evidence:** Online travel agent bookings cancel 20.7% of the time, about twice the Direct rate (10.9%), and cause 53% of lost revenue (Question 2).
- **Business value:** Expected to reduce the largest single source of lost revenue.
- **Success metric:** Online travel agent cancellation rate and lost revenue.
- **Priority:** High. Stricter terms could reduce the hotel's visibility on booking websites, so watch booking volume from that channel.

**3. Encourage guests to book direct.**

- **Evidence:** Direct bookings cancel half as often as online travel agent bookings and are worth slightly more per booking made (\$242.75 vs \$232.99), before counting agent commissions (Question 3).
- **Business value:** Expected to lower cancellations and commission costs without raising prices. Examples include a best-price guarantee or small perks for booking on the hotel's website.
- **Success metric:** Direct share of bookings and the overall cancellation rate.
- **Priority:** Medium. The revenue difference per booking is small; most of the benefit comes from fewer cancellations and avoided commissions, which were not measured.

**4. Release unconfirmed group room blocks earlier.**

- **Evidence:** Group bookings cancel 29.9% of the time, the highest of any segment, and are worth the least per booking (\$146.50) (Questions 2, 3 and 6).
- **Business value:** Expected to free up rooms for other guests sooner.
- **Success metric:** Group pickup rate (rooms used vs. rooms blocked) and group cancellation rate.
- **Priority:** Medium. Groups are only 6% of bookings and 8% of lost revenue.

**5. Run low-season promotions from November to March.**

- **Evidence:** January has half of August's arrivals and about a third of its revenue; December has the highest cancellation rate (22.3%) (Question 7).
- **Business value:** Expected to raise occupancy in the slowest months. Summer pricing already follows demand, so no price increase is recommended.
- **Success metric:** Arrivals and revenue per month for November to March, compared with prior years.
- **Priority:** Medium. Room capacity and occupancy were not in the data, so the size of the opportunity cannot be measured.

**6. Require a deposit from guests who have canceled before.**

- **Evidence:** These guests cancel 22.0% of the time versus 15.6% for others (Question 6).
- **Business value:** Expected to reduce cancellations in a small, higher-risk group (about 6% of bookings).
- **Success metric:** Cancellation rate for flagged guests.
- **Priority:** Low. The difference is modest and the group is small.

**What the data cannot support yet**

- **Add-on and upgrade programs:** Room changes are too rare (23 bookings) and meal or parking revenue is not recorded (Question 12). Collecting ancillary revenue data would be needed first.
- **A loyalty program:** Repeat guests cancel slightly less but bring about 11% less revenue per booking, and acquisition costs are unknown (Question 9).
- **Country-based targeting:** Only the United States has enough bookings to analyze (Question 11).
