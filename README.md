# 🏨 Hotel Booking Trend Analysis — Exploratory Data Analysis (EDA)

![Hotel Booking](hotel_booking.jpg)

## 📌 Project Overview

This project performs an in-depth **Exploratory Data Analysis (EDA)** on a hotel booking dataset containing reservation records from two hotel types — a **City Hotel** and a **Resort Hotel** — spanning multiple years.

The dataset includes rich information such as guest demographics, booking channels, meal preferences, pricing (ADR), cancellation status, and more. The goal is to uncover actionable insights that support strategic decision-making in the hospitality sector.

---

## 🎯 Business Objectives

The analysis is designed to answer key business questions:

1. **What are the main reasons for booking cancellations?**
2. **What is the best time to book a hotel?**
3. **When is the peak season for each hotel type?**
4. **How can cancellations be reduced?**
5. **How can hotel revenue be increased?**

---

## 📂 Dataset Description

- **Source:** Hotel Booking Demand Dataset
- **Total Records:** ~119,390 rows, 36 columns
- **Hotel Types:** City Hotel, Resort Hotel
- **Coverage:** Multiple years of reservation data

### Key Features

| Feature | Description |
|---|---|
| `hotel` | Type of hotel (City Hotel / Resort Hotel) |
| `is_canceled` | Whether the booking was canceled |
| `lead_time` | Days between booking and arrival |
| `arrival_date_*` | Year, month, week, and day of arrival |
| `stays_in_weekend_nights` | Weekend nights stayed |
| `stays_in_week_nights` | Weekday nights stayed |
| `adults / children / babies` | Number of guests |
| `meal` | Meal type (BB, HB, FB, SC) |
| `country` | Guest's country of origin |
| `market_segment` | Market segment designation |
| `distribution_channel` | Channel through which booking was made |
| `adr` | Average Daily Rate |
| `reservation_status` | Final status (Canceled / Check-Out / No-Show) |

---

## 🛠️ Tech Stack

- **Language:** Python 3
- **Libraries:**
  - `pandas` — Data manipulation and analysis
  - `numpy` — Numerical operations
  - `matplotlib` — Data visualization
  - `seaborn` — Statistical data visualization
  - `plotly` — Interactive visualizations
  - `pycountry` — Country code mapping

---

## 🔍 Analysis Workflow

### 1. Data Loading & Initial Exploration
- Loaded dataset and performed first-look inspection (shape, dtypes, head/tail)
- Identified missing values and duplicate rows

### 2. Data Wrangling
- Dropped the `company` column (too many nulls)
- Filled missing values in `children` and `agent` columns with `0`
- Filled missing `country` values with `"Others"`
- Removed 166 invalid rows where all guest counts (adults + children + babies) were 0
- Fixed data types (`children`, `agent` → `int64`)
- Replaced binary flags with readable labels (`is_canceled`, `is_repeated_guest`)

### 3. Feature Engineering
- `total_stay_in_nights` = `stays_in_week_nights` + `stays_in_weekend_nights`
- `revenue` = `total_stay_in_nights` × `adr`
- `total_guest` = `adults` + `children` + `babies`

### 4. Univariate Analysis
- Hotel type preference distribution
- Repeat vs. new guest breakdown
- Cancellation rate
- Most preferred meal types
- Most preferred room types
- Top 10 booking agents
- Top 10 guest countries
- Most used distribution channels

### 5. Bivariate & Multivariate Analysis
- Year-wise booking trends by hotel type
- ADR variation across months
- Monthly booking counts by hotel
- ADR comparison across distribution channels
- Lead time variation across hotel types
- Pair plots (ADR vs. total guests by hotel)
- Correlation heatmap of all numerical variables

---

## 💡 Key Insights

- **City Hotel is more popular**, accounting for ~66% of all bookings.
- **Only 3.19% of guests are repeat visitors**, highlighting a loyalty gap.
- **Cancellation rate is ~37%**, a significant business concern.
- **Bed & Breakfast (BB)** is the most preferred meal type (92,236 bookings).
- **Room Type A** is the most preferred room, with 74,020 bookings.
- **Agent No. 9** is the highest-performing booking agent.
- **Portugal** contributes the most guests (~48,483), followed by the UK and France.
- **TA/TO (Travel Agent/Tour Operator)** is the dominant distribution channel.
- **2016 had the highest bookings** for both hotel types.
- **City Hotel peaks in May**, Resort Hotel peaks in **July–August**.
- **GDS channel** generates the highest ADR for City Hotels.

---

## ✅ Business Recommendations

- **Reduce cancellations** by offering flexible policies and proactive guest communication.
- **Boost repeat guests** through loyalty programs, discounts, and feedback-driven improvements.
- **Optimize pricing** based on seasonal demand (May for City, July–August for Resort).
- **Leverage TA/TO channels** and maintain strong relationships with high-performing agents.
- **Target Portuguese and UK markets** with focused marketing campaigns.
- **Promote less-popular room types** (H, I, K, L) through special packages and offers.

---

## 📁 Project Structure

```
hotel-booking-eda/
│
├── EDA_Hotel_Booking_Trend.ipynb   # Main analysis notebook
├── hotel_booking.csv               # Dataset (not included — see below)
└── README.md                       # Project documentation
```

> **Note:** The dataset (`hotel_booking.csv`) is not included in this repository. You can download it from [Kaggle — Hotel Booking Demand](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand).

---

## 👤 Author

**Jayakrishnan**

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

