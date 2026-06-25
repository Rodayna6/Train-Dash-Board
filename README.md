# Train_Rides_Project
# 🚂 UK Train Rides — Railway Transportation Analytics Dashboard

> **DEPI R4 Graduation Project · Microsoft Power BI Track · CAI4_DAT2_S4 · April 2026**

An interactive Power BI dashboard analysing 31,653 UK National Rail ticket transactions across January–April 2024. The dashboard covers revenue performance, ridership patterns, operational disruptions, refund analysis, and 3-month forecasting.

---

## 👥 Team Members

| Name | Role |
|------|------|
| Habiba Waleed Abdelrazek Mohammed | Project Leader, Forecasting Dashboard |
| Habiba Mohammed Abdelfattah | Dashboard Visualization |
| Gannah Salah | Refund& financial analysis Dashboard |
| Aya Hossam Mostafa | Analysis and insights |
| Rodayna | Data cleaning and preparation |
| Sara Mohamed | Cancelled Rides |
| Each one take part of it depend on the dashboard page | Documentation & Presentation |

---

## 📊 Dashboard Pages

| # | Page | What it covers |
|---|------|----------------|
| 1 | **Financial Performance** | Total revenue · MoM trends · Ticket type & payment method breakdown |
| 2 | **Tickets Details** | Ticket class & type demand · Time-of-day segments · Decomposition Tree |
| 3 | **Delayed Rides** | Delay counts · Root causes · Station breakdown · Ticket class analysis |
| 4 | **Cancelled Rides** | Cancellation counts · Reasons · Route & ticket type impact |
| 5 | **Refunds & Financial Analysis** | Refund rate · Revenue lost · Station-level refund breakdown |
| 6 | **Forecasts** | 3-month projections for revenue, tickets, delays & cancellations |

---

## 📁 Repository Structure

```
Train-Dash-Board/
├── Railway_DEPI_Grad_Project_final_file.pbix   # Power BI dashboard
├── railway.csv                                  # Raw dataset (31,653 rows, 18 columns)
├── railway_data_dictionary.csv                  # Column definitions
├── README.md                                    # This file
├── docs/
│   ├── DEPI_Team4_Documentation.docx           # Full technical documentation
│   ├── DEPI_Team4_UserGuide.docx               # Dashboard user guide
│   ├── DEPI_UK_Train_Rides_Project_Documentation.pdf  # Planning & requirements PDF
│   └── DEPI_Team4_Presentation.pptx            # Final presentation deck
```

---

## 🗂️ Dataset

| Property | Value |
|----------|-------|
| File | `railway.csv` |
| Rows | 31,653 ticket transactions |
| Columns | 18 |
| Date range | January 2024 – April 2024 (journey dates) |
| Key fields | Transaction ID, Date of Journey, Departure Station, Arrival Destination, Ticket Class, Ticket Type, Price, Journey Status, Reason for Delay, Refund Request |

---

## ⚙️ How to Open the Dashboard

### Prerequisites
- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) — free download, version 2.0 or later
- Windows 10 / 11

### Steps
1. Clone or download this repository
2. Open **Power BI Desktop**
3. Click **File → Open report → Browse to file**
4. Select `Railway_DEPI_Grad_Project_final_file.pbix`
5. If prompted about data sources, click **Continue with current credentials**
6. The dashboard opens on **Page 1 — Financial Performance**

> **Note:** The dataset (`railway.csv`) is embedded in the .pbix file. No separate data connection is required.

---

## 🔑 Key Findings

- **£741,921** total revenue across Jan–Apr 2024 · Average ticket price **£23.44**
- **February revenue dropped 20.2% MoM** (−£40,244) before recovering +22.4% in March
- **Advance tickets** are the most popular type (17,561 tickets, 41.7% of revenue)
- **Manchester Piccadilly** is the busiest departure station (5,650 journeys)
- **86.8% of journeys are on time** · 7.2% delayed · 5.9% cancelled (13.2% combined disruption)
- **Weather is the #1 delay cause** (~758 normalised incidents)
- **1,118 refund requests** submitted · £38,702 refunded · Net revenue after refunds: **£703,219**

---

## 🛠️ Technical Details

### Data Model
- **1 fact table:** `railway` (31,653 rows)
- **4 dimension tables:** `Date Table`, `Journey Status`, `Payment Method`, `Reason for Delay`
- **1 measures table:** 17 DAX measures

### Key DAX Measures
- `Total Revenue` · `Monthly Revenue` · `MoM Revenue Change (£)` · `MoM Revenue Change (%)`
- `Delayed Rides` · `Cancelled Rides` · `On-Time Rides` · `Off Time Rides %`
- `Sum Actual Delay (Min)` · `Refund Request Rate` · `Refunded Revenue` · `Revenue After Refund`

### Power Query Steps
- Data type enforcement on all 18 columns
- Null replacement in `Reason for Delay` → `"None"` and `Refund Request` → `"No"`
- Trimmed whitespace on all text columns
- Calculated `Departure Time Segments` column (Morning / Afternoon / Evening / Night)
- Created 3 reference dimension tables
- Built and marked a DAX Date Table with `CALENDAR()` function

---

## 📄 Documentation

All project documentation is in the `/docs` folder:

| Document | Contents |
|----------|----------|
| `DEPI_Team4_Documentation.docx` | DAX measures table · Power Query steps · Testing checklist · Business questions & KPIs · Final insights · Literature review |
| `DEPI_Team4_UserGuide.docx` | How to navigate the dashboard · Per-page visual guide · KPI reference · Troubleshooting |
| `DEPI_UK_Train_Rides_Project_Documentation.pdf` | Project proposal · Timeline · Task roles · Risk assessment · Stakeholder analysis · User stories · Functional & non-functional requirements |
| `DEPI_Team4_Presentation.pptx` | 15-slide deck: problem → data → cleaning → model → dashboard walkthrough → insights → recommendations |

---

## 📜 License

This project was developed as a graduation project for the Digital Egypt Pioneers Initiative (DEPI) Round 4, Microsoft Power BI Track. The dataset is used for educational purposes only.
