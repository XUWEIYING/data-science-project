# data-science-project

# Flight Passengers Analysis (1949–1960)

An exploratory data analysis of monthly international airline passenger
numbers from 1949 to 1960, focusing on long-term growth trends and
seasonal patterns.

---

## 1. Problem / Research Question

**Research question:**  
How did international airline passenger volume evolve between 1949 and 1960,
and is there a recurring seasonal pattern within each year?

The dataset contains monthly passenger counts over 12 years. Two questions
are addressed:

1. **Long-term trend** — Is there a consistent year-over-year growth in
   passenger volume?
2. **Seasonality** — Within each year, which months consistently show the
   highest and lowest passenger numbers?

Understanding these patterns is relevant for airline capacity planning,
route scheduling, and revenue forecasting.

---

## 2. Dataset Source and Usage Permissions

- **File:** `data/flight_details.csv`
- **Contents:** 144 rows (12 months × 12 years), 3 columns
  (`Years`, `Months`, `Passengers`)
- **Origin:** This is the well-known *AirPassengers* dataset, originally
  published by Box, G. E. P., Jenkins, G. M., and Reinsel, G. C. (1976)
  in *Time Series Analysis, Forecasting and Control*.
- **Usage permission:** The dataset is in the public domain and is widely
  used for teaching time-series analysis. It contains no personal,
  confidential, or restricted information. It is safe to redistribute.

---

## 3. Methods and Tools Used

**Tools**
- Python 3.10
- Jupyter Notebook
- pandas — data loading, reshaping, aggregation
- NumPy — numerical operations
- Matplotlib — plotting
- Seaborn — heatmap rendering

**Methods**
1. Loaded the raw CSV into a pandas DataFrame.
2. Converted the `Months` column into an ordered categorical variable so
   that months are displayed in calendar order rather than alphabetical order.
3. Pivoted the data into a 12 × 12 matrix (months as rows, years as columns)
   using `pandas.pivot`.
4. Visualized the matrix as a heatmap (Seaborn `heatmap`) to reveal both the
   year-over-year trend and the within-year seasonal pattern in one view.

---

## 4. Key Findings and One Limitation

**Key findings**
- Passenger volume grew steadily every year from 1949 (≈112–148 passengers
  per month) to 1960 (≈390–622 passengers per month) — roughly a **4×
  increase over 12 years**.
- A clear **seasonal pattern** repeats each year: July and August are
  consistently the busiest months, while November and February are
  consistently the quietest.
- The seasonal amplitude widens over time — later years show a much larger
  summer peak than earlier years, suggesting both demand growth and stronger
  seasonal concentration.

**Limitation**
This dataset only reports aggregate monthly passenger counts. It contains no
information on routes, aircraft type, ticket price, or economic context, so
we cannot attribute the observed growth or seasonality to specific causes
(e.g., tourism vs. business travel, fuel prices, or route expansion).

---

## 5. Instructions for Running the Analysis

**Requirements**
- Python 3.8 or later
- Jupyter Notebook

**Steps**

```bash
# 1. Clone this repository
git clone https://github.com/<your-username>/data-science-project.git
cd data-science-project

# 2. (Optional) Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter Notebook
jupyter notebook
