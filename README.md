# Fuel Economy Analysis 🚗⛽

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3.0-blue)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4.3-blue)](https://matplotlib.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.11.2-blue)](https://seaborn.pydata.org/)

A comprehensive analysis of vehicle fuel economy trends using EPA data from 2008 and 2018. This project explores fuel efficiency improvements, alternative fuel adoption, and characteristics of eco-friendly vehicles.

## 📌 Key Questions Answered
1. Are more models using alternative fuels? By how much?
2. How have vehicle classes improved in fuel economy?
3. What characterizes SmartWay vehicles?
4. What features correlate with better fuel economy?
5. Which 2008 model showed the greatest MPG improvement by 2018?

## 📦 Dataset Overview
- **Source**: EPA's National Vehicle and Fuel Emissions Lab
- **Years Analyzed**: 2008 vs 2018
- **Original Features**:
  - Engine specifications (displacement, cylinders)
  - Fuel type (Gasoline, Diesel, Ethanol, etc.)
  - MPG metrics (City, Highway, Combined)
  - Environmental scores (Air Pollution, Greenhouse Gas)
  - SmartWay certification

## 🛠️ Data Wrangling Highlights
```python
# Key Cleaning Steps
fe_08 = fe_08.dropna().drop_duplicates()
fe_18 = fe_18.dropna().drop_duplicates()

# Fixing data types
fe_08['cyl'] = fe_08['cyl'].str.extract('(\d+)').astype(int)
fe_18['cyl'] = fe_18['cyl'].astype(int)

# Handling hybrid vehicles
hb_08 = fe_08[fe_08['fuel'].str.contains('/')]
# ... (complex splitting logic for hybrid metrics)
```

## 🔍 Major Findings
### 1. Alternative Fuel Adoption
| Year | Unique Alternative Fuel Models | Proportion of Total |
|------|--------------------------------|---------------------|
| 2008 | 2                              | 0.5%               |
| 2018 | 26                             | 7.3%               |

![Alternative Fuel Growth](https://via.placeholder.com/600x400.png?text=Alternative+Fuel+Growth)

### 2. MPG Improvements by Vehicle Class
| Vehicle Class    | MPG Improvement (2008-2018) |
|------------------|----------------------------|
| Large Cars       | +4.9                       |
| Midsize Cars     | +6.3                       |
| Pickups          | +2.3                       |

### 3. SmartWay Vehicles Profile (2018)
- **Avg Engine Size**: 1.79L vs 2.6L in 2008
- **Avg Combined MPG**: 37.4 vs 23.7 in 2008
- **Common Features**: Smaller engines, hybrid systems, aerodynamic designs

### 4. Top Improved Model
**Volvo XC 90** achieved the largest MPG improvement:
- 2008: 15.7 MPG → 2018: 32.2 MPG (+104% improvement)

## 📊 Key Visualizations
```python
plt.scatter(fe_18['displ'], fe_18['cmb_mpg'])
plt.title('Engine Size vs Fuel Efficiency (2018)');
```
![Engine Size vs MPG](https://via.placeholder.com/600x400.png?text=Engine+Size+vs+MPG)

## 🚀 Getting Started
1. Clone repo:
   ```bash
   git clone https://github.com/yourusername/fuel-economy-analysis.git
   ```
2. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```
3. Run Jupyter notebook:
   ```bash
   jupyter notebook fuel_economy_analysis.ipynb
   ```

## 📂 File Structure
```
├── Data/
│   ├── fe_08_cleaned.csv
│   └── fe_18_cleaned.csv
├── Images/
├── fuel_economy_analysis.ipynb
├── README.md
└── requirements.txt
```

## 📚 Data Sources
- [EPA Fuel Economy Data](https://www.epa.gov/compliance-and-fuel-economy-data)
- [DOE Fuel Economy Guide](https://www.fueleconomy.gov/)

## 🤝 Contributing
Contributions welcome! Please open an issue first to discuss proposed changes.

## 📄 License
EPA data files are public domain. Code licensed under [MIT License](LICENSE).

---

**Let's drive towards a more fuel-efficient future!** 🌱
