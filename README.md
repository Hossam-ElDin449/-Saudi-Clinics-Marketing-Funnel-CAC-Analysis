# Healthcare Marketing Funnel & CAC Analysis: 17 Saudi Clinics

An end-to-end analytics project that links **digital ad spend** to **clinic revenue** across a group of 17 clinics in Saudi Arabia, answering one business question:

> *Is our marketing spend actually bringing in paying patients, and where should we move the budget?*

> **Data disclaimer:** All data in this repository is **synthetic (simulated)**. Clinic names, figures and results are fictional and were generated with random processes (see `scripts/generate_dataset.py`). Nothing here comes from a real company. The project demonstrates analytical method, not real-world performance.

## Dashboard
<!-- Add a screenshot: dashboard/dashboard.png -->
![Dashboard](<img width="3837" height="2285" alt="Screenshot 2026-10-05 060141" src="https://github.com/user-attachments/assets/a98cca73-98bd-4f88-bbff-b6a9249475cc" />
)

https://ai.studio/apps/c50b73ca-e9d4-485f-82a8-c610eb4cf9ca

## The Funnel
`Impressions → Clicks → Leads → Bookings → Attended → Paid patients → Revenue`

## Dataset
| File | Description |
|---|---|
| `data/saudi_clinics_marketing_funnel.csv` | 54,465 rows, one per ad per day, 5 Oct 2025 – 30 Sep 2026 |
| `data/saudi_clinics_dim.csv` | Clinic dimension: name, city, region, specialty, number of doctors |

Scope: 17 clinics, 12 cities, 9 specialties, 1,251 ads, 5 platforms (Snapchat, Instagram, TikTok, Facebook, Google Search). Currency is SAR, excluding VAT.

### Data dictionary
| Column | Meaning |
|---|---|
| date | Day of the ad activity |
| clinic_id, clinic_name, city, specialty | Clinic attributes (join to dim table on `clinic_id`) |
| campaign_id, campaign_objective | Campaign and its goal (Awareness, Offer / Promotion, Seasonal Push, Always-on Lead Gen) |
| ad_id, platform_campaign_id | Ad and platform campaign identifiers |
| platform | Ad channel |
| age, gender, interest | Targeted audience segment |
| Impressions, Clicks | Ad delivery and engagement |
| Spent | Ad spend (SAR) |
| Total_Conversion | Leads (enquiries) |
| Bookings, Attended | Appointments booked and attended |
| Approved_Conversion | Paid patients |
| Revenue | Revenue from paid patients (SAR) |

**Attribution note:** revenue and funnel outcomes are credited to the date the lead arrived (cohort attribution), not the visit date.
**Revenue is not profit.** Treatment and staff costs are not included.

## KPI definitions
| KPI | Formula |
|---|---|
| CTR | Clicks ÷ Impressions |
| CPC | Spent ÷ Clicks |
| CPM | Spent ÷ Impressions × 1000 |
| Click-to-Lead | Total_Conversion ÷ Clicks |
| Lead-to-Booking | Bookings ÷ Total_Conversion |
| Show-up rate | Attended ÷ Bookings |
| Lead-to-Paid | Approved_Conversion ÷ Total_Conversion |
| CPL | Spent ÷ Total_Conversion |
| CAC | Spent ÷ Approved_Conversion |
| AOV | Revenue ÷ Approved_Conversion |
| ROAS | Revenue ÷ Spent |
| ROI | (Revenue − Spent) ÷ Spent |

## Key findings
<!-- Replace with YOUR findings from the dashboard, each with a number and a recommendation. Example format:
1. Clinic X has the cheapest leads (CPL SAR __) but the lowest Lead-to-Paid rate (__%), so its CAC is __. Recommendation: review targeting before increasing budget.
2. Platform Y delivers the lowest CAC (SAR __). Recommendation: shift __% of budget from platform Z.
3. Booking rate dropped at Clinic Z in March–April (__% vs __% normal). Recommendation: investigate call-centre follow-up. -->

## Recommendations
<!-- 3 clear actions for management -->

## Tools
Python (pandas, numpy) for data generation and validation, and [Power BI / HTML dashboard / Excel: edit this] for visualisation.

## Reproduce
```bash
pip install -r requirements.txt
python scripts/generate_dataset.py
```
The random seed is fixed, so the output is identical on every run.

## Author
Dr Hossam ElDin 
