# FMCG Retail Data Science & Strategic Category Analytics Pipeline

A comprehensive, production-grade retail data engineering and statistical modeling suite analyzing Fast-Moving Consumer Goods (FMCG) transaction datasets, purchasing velocity, and controlled store marketing trials utilizing an optimized Python analytics framework.

## 🔗 Repository Interactive Directories
*   [📓 **Pipeline 1: Consumer Profiling & Sizing Affinity**](task1_customer_insights/task1_customer_insights.ipynb) — Automated regex text cleansing, demographic grouping, and scale index validation.
*   [📓 **Pipeline 2: Controlled Uplift Market Trial Simulation**](task2_uplift_trial_testing/task2_uplift_trial_testing.ipynb) — Time-series similarity matching engine using blended proximity vectors and Welch's t-tests.

---

## 🛠️ Portfolio Architecture & Feature Deep-Dive

### 📈 Task 1: Retail Customer Segmentation & SKU Sizing Affinity Engine
Processes transaction-level retail records to isolate consumer household demographics, calculate continuous commercial price points, and evaluate buying distributions.

*   **Algorithmic Data Cleansing:** Tokenized and split text strings directly from product descriptors. Engineered condition filters to purge non-chip adjacent items (Salsa dips) and non-consumer wholesale outliers (e.g., matching single line orders of 200 items).
*   **Timeline Integrity Verification:** Built a continuous true chronological 365-day fiscal year timeline object, executing a `left join` on the raw logs to validate pipeline health and isolate tracking anomalies (zero-volume Christmas holiday store closures).
*   **Hypothesis Pricing Disparity:** Conducted a Welch’s Independent T-test evaluating the mean price paid per pack across cohorts. Mainstream Young and Midage singles/couples paid a significantly higher unit cost (p < 0.05), proving a strong willingness-to-pay and brand value sensitivity.
*   **Strategic Proportional Affinity Indexing:** Developed an automated logic matrix to identify product brand and pack-size preferences relative to market baselines:
$$
\[\text{Affinity Index} = \left( \frac{\% \text{ Target Segment Volume bought}}{\% \text{ Baseline Segment Volume bought}} \right) \times 100\]
$$

*   **Core Takeaway:** Mainstream Young/Midage consumers over-index heavily on premium brands (Kettle, Tyrrells) and large, sharing-sized party bags (330g, 270g, 380g), while significantly under-indexing on individual single-serve packs (70g, 90g).

### 🧪 Task 2: Marketing Uplift & Controlled Market Trial Simulation
Evaluates the commercial growth impact of an experimental in-store layout test executed across Trial Locations (Stores 77, 86, and 88) between February 2019 and April 2019.

*   **Similarity-Matching Engine (Pearson Correlation + Magnitude Distance):** Formulated an automated store matching algorithm scanning the 7-month pre-trial timeline. It scores control store candidates using a blended metric tracking trend direction (correlation) and sales volume scale (min-max proximity normalization):
$$
\[\text{Score} = (W \times \text{Correlation}) + ((1 - W) \times \text{Normalized Proximity})\]
$$
    *   *Algorithm Output Matched Controls:* Store 77 → **Control 233** | Store 86 → **Control 155** | Store 88 → **Control 237**.
*   **Calibrated Baseline Scaling Factors:** Applied a proportional scaling multiplier during the pre-trial phase to correct absolute volume baseline scale variances driven by physical store footprint sizes.
*   **Statistical Significance Verification:** Executed a one-tailed independent T-test using the pre-trial standard deviation of percentage changes (df = 6). This evaluated whether performance changes indicated true campaign growth or normal retail data noise.
*   **Dual-Axis Net-Uplift Dashboard:** Formulated a net net uplift visualization tracking Net Financial Revenue (Left Axis Bars) overlapping Net Unique Traffic Volume (Right Axis Line) from January to June to trace campaign efficiency and long-term customer retention.

### 📋 Blended Campaign Diagnostics
1.  **Store 77:** Successful layout implementation. The pipeline isolates rolling monthly sales and customer counts, tracking performance directly against a 95% critical t-value threshold boundary to confirm significant positive performance spikes during active campaign months.
2.  **Store 86:** Wallet-share expansion proof. Total revenue and unique shopper traffic significantly broke past the 95% confidence limits across active trial months.
3.  **Store 88:** Statistically insignificant response. Operational metrics fluctuated inside standard pre-trial standard error bounds, closely matching control store performance.

---

## 📂 Repository Layout Blueprint
```text
├── README.md                           <-- Master portfolio hub and documentation core
├── requirements.txt                    <-- Environment packages (pandas, seaborn, scipy)
├── .gitignore                          <-- Excludes notebook checkpoints and localized junk
├── task1_customer_insights/
│   └── task1_customer_insights.ipynb    <-- Data cleansing, tokenization & affinity tracking
└── task2_uplift_trial_testing/
    └── task2_uplift_trial_testing.ipynb <-- Store matching engine & statistical trial tests
```
