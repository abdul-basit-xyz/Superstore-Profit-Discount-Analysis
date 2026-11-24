# Superstore-Profit-Discount-Analysis

# 📊 Superstore Profitability & Discount Analysis

## 🎯 Project Purpose
The purpose of this project is to analyze retail sales data to uncover why specific product categories and regions suffer financial losses despite strong sales volume. By cleaning raw transactional records in Python and building an interactive dashboard in Tableau Public, this project identifies loss-making hotspots and provides actionable discount recommendations to improve profit margins.

## 🔗 Dataset Source & Live Dashboard
* **Original Dataset:** [Superstore Dataset on Kaggle](https://www.kaggle.com/code/lynnclemons/superstore-data-cleaning-transformation) (`SampleSuperstore.csv`)
* **Live Interactive Dashboard:** [View Dashboard on Tableau Public](https://public.tableau.com/app/profile/abdul.basit.nasir/viz/Superstore_Profit_and_Discount_Analysis/Superstore_Profit_and_Discount_Analysis)

## 🛠️ Tools & Libraries Used
* **Programming & Data Cleaning:** Python 3.13, Jupyter Notebook
* **Python Libraries:** `pandas` (data manipulation, duplicate removal, feature engineering), `os`
* **Data Visualization & BI:** Tableau Public (Desktop & Web Authoring)
* **Version Control:** GitHub

## ⚙️ Setup & Installation Instructions
To run the data cleaning script locally on your machine:
1. Clone or download this repository to your computer.
2. Ensure Python 3.x and Jupyter Notebook (or VS Code) are installed.
3. Install the required library via terminal or notebook cell:
   ```bash
   pip install pandas
   ```
4. Open `data_cleaning.ipynb` and run all cells sequentially (`Kernel -> Restart & Run All`) to generate `cleaned_superstore.csv`.

## 🧹 Data Cleaning & Transformation Steps
1. **Data Inspection:** Checked dataset dimensions (`9,994 rows, 13 columns`), data types, missing values (`0 nulls`), and statistical distributions using `.info()`, `.isnull().sum()`, and `.describe()`.
2. **Duplicate Removal:** Identified and removed **17 exact duplicate rows** (reducing the dataset to **9,977 unique records**) to prevent double-counting sales and profit.
3. **Dimensionality Reduction:** Dropped non-essential columns (`Ship Mode`, `Segment`, `Country`, `State`, `Postal Code`, `Quantity`) to focus strictly on geographic, product, and financial metrics.
4. **Feature Engineering & Formatting:**
   * Converted raw decimal discounts (`0.20`) into a readable **`Discount (%)`** column (`20%`).
   * Created a **`Profit_Status`** column categorizing strictly positive profit (`> 0`) as `Profit` and zero/negative returns (`<= 0`) as `Loss`.

## 📈 Dashboard Build Instructions (Tableau Public)
1. **Connect Data:** Opened Tableau Public and connected to `cleaned_superstore.csv` as a Text File.
2. **Profit & Loss by Product (Bar Chart):** Placed `Sub-Category` on Rows and `Profit` on Columns, color-coded by Profit (Green) and Loss (Red).
3. **Discount Impact Analysis (Bar Charts):** Created regional and category-level views using `Average Discount (%)` to highlight over-discounted segments.
4. **Auto-Zoom City Profit Map:** Mapped `City` (set to United States), sized circles by `Sales`, colored by `Profit`, and unlocked the map pin for dynamic auto-zooming.
5. **Gross Profit vs. Gross Loss (Pie Chart):** Used a calculated field `ABS([Profit])` grouped by `Profit_Status` to compare the true dollar magnitude of profit vs. loss.
6. **Dashboard Assembly & Interactivity:** Combined all sheets onto a single dashboard canvas and enabled **Use as Filter** on key charts (`PnL by Product`, `Discount by Region`, and `Discount by Category`) for interactive cross-filtering.

## 💡 Key Business Insights & Recommendations
* **The Central Region & Binders Discount Trap:** The **Central Region** carries the highest average discount (~24%), creating severe red loss hotspots on the map (especially in Texas and Illinois).
* **Product-Level Losses:** **Binders** and **Tables** suffer heavy losses due to extreme clearance discounts (60%–80%), where discounted prices fall below actual product cost.
* **Recommendation:** Cap maximum discounts on **Binders** and **Tables** at **20%** in the Central Region to recover profit margins immediately without hurting overall sales volume.

## 📂 Repository Files
* `SampleSuperstore.csv` — Original raw dataset from Kaggle.
* `data_cleaning.ipynb` — Complete Python script for data inspection, cleaning, and transformation.
* `cleaned_superstore.csv` — Final processed dataset used for Tableau visualization.
* `superstore_dashboard.pdf` — PDF export of the interactive Tableau dashboard.
