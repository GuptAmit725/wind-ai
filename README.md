Perfect 👍 I’ll turn the README into a **starter repo template** that not only describes the competition but also helps participants quickly get started with setup, data, and submissions.

Here’s the updated **README.md**:

---

# WindAI: Wind Power Forecasting in Norway

## 📖 Overview

WindAI is a data challenge focused on **wind power forecasting** in the Norwegian power market.
The task: build AI/ML models that can produce **hourly wind power forecasts two days ahead** for each of the Norwegian bidding zones (NO1–NO4).

These forecasts are critical for **Statnett** and Nordic transmission operators to ensure efficient and safe power trading in the **flow-based market coupling system**.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/<your-org>/windai-forecasting.git
cd windai-forecasting
```

### 2. Create and Activate Environment

We recommend using Python **3.9+**.

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

# Install requirements
pip install -r requirements.txt
```

### 3. Install Jupyter (optional)

If you want to run the provided notebooks:

```bash
pip install jupyterlab
```

---

## 📂 Data Setup

### Provided Datasets

The competition provides four main datasets (2020-01-01 → 2025-03-31):

1. **Weather Forecasts (MET MEPS)** – ensemble weather simulations (65 hours ahead)
2. **Weather Nowcasts (MET)** – closest available estimate to observed weather
3. **Wind Power Observations (Statnett)** – hourly wind power production (MW) by bidding zone
4. **Wind Park Metadata (Statnett)** – wind park locations, capacities, and start dates

### Download Data

The full dataset bundle is available on the **competition website**.
After download, extract the archive to the `data/` directory:

```bash
mkdir data
unzip windai_dataset.zip -d data/
```

Expected structure:

```
data/
  ├── met_forecast.csv
  ├── met_nowcast.csv
  ├── wind_power.csv
  ├── wind_metadata.csv
```

---

## 📓 Example Notebook

We provide a **starter Jupyter notebook** (`notebooks/example_baseline.ipynb`) that demonstrates:

* Data loading and preprocessing
* Feature aggregation (wind speed, temperature, humidity, etc.)
* Training a simple **linear regression with spline transformer** baseline
* Evaluation using **RMSE**

Run the notebook:

```bash
jupyter lab notebooks/example_baseline.ipynb
```

---

## 🏆 Tasks

* **Main Task:**
  Provide **hourly wind power forecasts two days ahead** for each bidding zone (NO1–NO4).

* **Additional Challenges:**

  * Ensure robustness to climate changes and new wind installations
  * Provide trustworthy and explainable predictions
  * Include uncertainty estimates
  * Optimize models for lightweight deployment

---

## 📊 Submissions

### Submission Format

Daily forecasts must be submitted as a CSV file with the format:

```
Time,ELSPOT NO1,ELSPOT NO2,ELSPOT NO3,ELSPOT NO4
2025-03-25 00:00:00+01:00,0,0,946.31,0
2025-03-25 01:00:00+01:00,0,0,761.13,0
...
2025-03-25 23:00:00+01:00,0,0,778.81,0
```

### Submission Workflow

1. Input data is updated daily at **14:00 CET** in a shared container
2. Teams generate a **two-day ahead forecast** for all 24 hours
3. Forecasts must be uploaded **before midnight CET**

---

## 📈 Evaluation

* **Scoring Metric:** Root Mean Square Error (RMSE)
* **10 submission days:** Sep 22–26 and Sep 29–Oct 3, 2025 (one miss allowed)

### Ranking Criteria

1. Accuracy (65%)
2. Trustworthiness & Explainability (20%)
3. Implementation & Presentation (10%)
4. Robustness to Changes (5%)
5. Tie-breakers: computational efficiency

A public **dashboard** will display RMSE and forecast plots.

---

## 📅 Timeline

* 📊 Data available: 2020-01-01 → 2025-03-31
* 📝 Forecasting period: Sep 22–26 and Sep 29–Oct 3, 2025
* ⏱️ Submissions: 10 forecasts (one can be missed)

---

## 🙌 Acknowledgements

This challenge is made possible thanks to **Statnett**, **SINTEF**, **University of Oslo**, and the **Norwegian AI Research Consortium (NORA)**.
Supported by projects funded by the **Research Council of Norway (RCN)** and international collaborations on AI and wind energy research.

---

## 📬 Contact

For questions or correspondence:
**Kushtrim Visoka** – [kushtrim.visoka@nora.ai](mailto:kushtrim.visoka@nora.ai)
