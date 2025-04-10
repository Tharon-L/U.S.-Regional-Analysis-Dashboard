# **U.S.-Regional-Analysis-Dashboard**

# *Advanced Insurance Data Analysis with Pandas* 

## **📌 Project Overview**  
This Python project performs **comprehensive statistical analysis** on medical insurance data using **pandas** for advanced data processing. It calculates key metrics by region and exports results for **Power BI visualization**.  

---

## **📂 Project Structure**  
```
insurance-analysis/  
├── data/  
│   ├── insurance.csv            # Raw dataset  
│   ├── regional_stats.csv       # Aggregated regional statistics  
│   ├── charge_per_bmi.csv       # Charge-to-BMI ratio by region  
│   └── insurance_clean.csv      # Processed dataset for Power BI  
├── insurance_analysis.py        # Main analysis script  
├── README.md                    # Project documentation  
```

---

## **🔍 Key Features**  

### **1. Comprehensive Regional Analysis**  
Calculates **15+ metrics** per region including:  
- **Financial Metrics**  
  - Mean, median, min, max, and standard deviation of charges  
  - Charge-to-BMI ratio (cost efficiency metric)  
- **Demographic Insights**  
  - Average age and BMI  
  - Percentage of smokers  
  - Total number of children  

### **2. Automated Data Export**  
- Generates **analysis-ready CSV files** for Power BI:  
  - `regional_stats.csv` – Full regional breakdown  
  - `charge_per_bmi.csv` – Cost efficiency metric  
  - `insurance_clean.csv` – Processed dataset  

### **3. Advanced Pandas Techniques**  
Demonstrates:  
✅ Multi-level aggregation with `groupby()` + `agg()`  
✅ Lambda functions for custom metrics  
✅ Column flattening for cleaner exports  
✅ Memory-efficient data processing  

---

## **🚀 How to Use**  

1. **Install dependencies** (just pandas):  
   ```sh
   pip install pandas
   ```

2. **Run the analysis:**  
   ```sh
   python insurance_analysis.py
   ```

3. **Expected Output:**  
   ```
   Analysis complete and files exported for Power BI
   ```
   + 3 CSV files generated in `/data` directory  

4. **Visualize in Power BI:**  
   - Connect to the exported CSVs  
   - Create dashboards with regional comparisons  

---

## **📊 Sample Output Metrics**  

| Region    | Mean Charges | Smoker % | Charge/BMI | Avg. Children |  
|-----------|-------------|----------|------------|---------------|  
| northeast | $13,500     | 20.1%    | $420.50    | 1.2           |  
| southwest | $12,300     | 17.8%    | $380.75    | 1.1           |  

*(Example values - actual results will vary by dataset)*  

---

## **🛠️ Technical Highlights**  

### **Core Functionality**  
```python
# Advanced multi-metric aggregation
regional_stats = data.groupby('region').agg({
    'charges': ['mean', 'median', 'std', 'min', 'max', 'count'],
    'smoker': lambda x: (x == 'yes').mean() * 100  # Smoker percentage
})

# Custom metric calculation
charge_per_bmi = data.groupby('region').apply(
    lambda x: (x['charges'] / x['bmi']).mean()  # Cost efficiency
)
```

### **Optimized for Power BI**  
- Flattened column names (`charges_mean`, `smoker_<lambda>`)  
- Index reset for proper relational modeling  
- Clean dataset export with `to_csv()`  

---

## **🔮 Future Enhancements**  
- Add **age group segmentation** (20-30, 30-40, etc.)  
- Incorporate **geographic mapping** in Power BI  
- Build **predictive model** for charge estimation  

---

## **📜 License**  
MIT License – Open source and adaptable for commercial use.  

---

## **💡 Why This Project?**  
- **Perfect for intermediate Python learners** wanting to master pandas  
- **Real-world business intelligence pipeline** (Python → Power BI)  
- **Production-ready structure** with clear data exports  

**⭐ Star the repo if you find this useful!**  

--- 

Would you like me to add a Jupyter Notebook version for exploratory analysis? 😊
