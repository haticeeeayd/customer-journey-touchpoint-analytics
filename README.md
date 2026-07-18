# Customer Journey & Touchpoint Analytics Platform

An end-to-end data analytics project that maps the airline passenger journey across digital and physical touchpoints, identifies satisfaction drop points, and delivers actionable insights through SQL analysis and interactive dashboards.

## Project Overview

This project analyzes **129,880 airline passenger survey records** across 14 service touchpoints to understand where the company wins or loses customer satisfaction. The analysis covers the full customer lifecycle — from booking to inflight experience — and segments findings by customer type, travel class, and delay impact.

## Key Findings

- **56.6% of passengers are dissatisfied** — the majority experience is negative
- **Booking stage scores lowest at 2.76/5.00** — the first touchpoint is the weakest link
- **Eco + Disloyal customers have only 14.4% satisfaction** — the most at-risk segment
- **WiFi (2.73) and Online Booking (2.76) are the worst-performing touchpoints**
- **Delays beyond 30 minutes drop satisfaction by 11+ percentage points** (47.1% → 36.2%)
- **Online Boarding has the largest gap (1.37) between satisfied and dissatisfied passengers** — highest-impact improvement area

## Tech Stack

- **Python** (pandas, NumPy) — Data preprocessing, cleaning, feature engineering
- **SQL / MySQL** — Database design, cohort analysis, KPI queries
- **Google Colab** — Development environment
- **Power BI** — Interactive dashboard (coming soon)

## Project Structure

```
├── customerjourney.ipynb          # Python data preprocessing & analysis
├── customer_journey_analysis.sql  # SQL queries for touchpoint & cohort analysis
├── airline_clean.csv              # Cleaned dataset (129,880 rows, 34 columns)
└── README.md
```

## Data Pipeline

**1. Data Collection & Merging**
- Combined train (103,904) and test (25,976) datasets from Kaggle Airline Passenger Satisfaction survey
- Total: 129,880 passenger records with 14 touchpoint satisfaction scores (1-5 scale)

**2. Data Preprocessing (Python)**
- Handled 393 missing values in Arrival Delay using median imputation
- Created age group segments: Young (18-25), Young Adult (26-35), Middle Age (36-50), Senior (51+)
- Engineered CSAT Score (0-100) from average touchpoint ratings
- Mapped 14 touchpoints into 4 customer journey stages: Booking → Airport → Boarding → Inflight
- Generated delay group categories and binary satisfaction labels

**3. SQL Analysis (MySQL)**
- Loaded cleaned data into MySQL database via CLI pipeline
- Performed cohort analysis across Class × Customer Type segments
- Identified worst-performing touchpoints and journey stage drop points
- Analyzed delay impact on satisfaction rates across 5 delay brackets

**4. Dashboard (Power BI)** — Coming soon
- Executive summary with KPI cards
- Customer journey funnel visualization
- Touchpoint heatmap by segment
- Interactive filters for Class, Customer Type, and Age Group

## SQL Query Highlights

**Journey Stage Drop Analysis** — Identified Booking (2.76) as the critical drop point vs Airport (3.31), Boarding (3.16), and Inflight (3.30).

**Cohort Analysis** — Discovered that Business Class Loyal Customers have 74.6% satisfaction while Eco Plus Disloyal Customers drop to 8.0%.

**Touchpoint Ranking** — Ranked all 14 touchpoints by average score, revealing WiFi (2.73), Online Booking (2.76), and Gate Location (2.98) as the bottom 3.

**Delay Impact** — Quantified the satisfaction decline: No Delay (47.1%) → 1-30 min (42.8%) → 31-60 min (36.2%) → 120+ min (35.8%).

## Dataset

Source: [Kaggle — Airline Passenger Satisfaction](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)

| Feature | Description |
|---|---|
| 14 Touchpoint Scores | WiFi, Online Booking, Gate Location, Check-in, Boarding, Seat Comfort, Food, Entertainment, On-board Service, Leg Room, Baggage, Inflight Service, Cleanliness, Departure/Arrival Convenience |
| Demographics | Gender, Age, Customer Type (Loyal/Disloyal) |
| Travel Info | Type of Travel (Business/Personal), Class (Business/Eco/Eco Plus), Flight Distance |
| Delays | Departure and Arrival delay in minutes |
| Target | Satisfaction (satisfied / neutral or dissatisfied) |

## How to Run

1. Clone this repository
2. Open `customerjourney.ipynb` in Google Colab or Jupyter Notebook
3. Run all cells to reproduce the analysis
4. Import `airline_clean.csv` into MySQL and execute `customer_journey_analysis.sql`

## Author

**Hatice Aydogan**
- [LinkedIn](https://www.linkedin.com/in/haticeavdogan)
- [GitHub](https://github.com/haticeeayd)
