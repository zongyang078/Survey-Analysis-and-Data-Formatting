# Survey Analysis and Data Formatting - CDBG Grant Analysis

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Code style: clean](https://img.shields.io/badge/code%20style-clean-brightgreen.svg)](https://github.com/psf/black)

A comprehensive data analysis project examining Community Development Block Grant (CDBG) applications from the City of Portland over a 10-year period (2016-2026). This project processes, analyzes, and visualizes grant application trends to inform policy decisions and improve the grant selection process.

## Project Overview

This analysis was conducted for Portland's Housing and Economic Development Department to identify trends and patterns in CDBG applications. The project addresses key questions about:

- Application volume trends over time
- Score distributions and quality metrics
- Organizational participation patterns
- Funding request analysis with scoring breakdowns
- Priority category distribution (Homeless, Economic Opportunity, Infrastructure, Housing)

## Key Features

- **Intelligent Data Cleaning**: Automatically handles multiple Excel formats across different years
- **Scoring Breakdown Analysis**: Extracts and analyzes 4 scoring components (Impact, Principles, Capacity, Collaboration)
- **10-Year Trend Comparison**: Optional stretch goal comparing 2016-2022 vs 2022-2026 periods
- **Professional Visualizations**: Generates 5 comprehensive charts following best practices
- **Missing Data Handling**: Preserves data integrity with transparent NaN handling

## Project Structure

```
Survey-Analysis-and-Data-Formatting/
├── data/
│   ├── 2022-2026_Case_Data.xlsx          # Primary dataset
│   └── 2016-2022_Case_Data.xlsx          # Historical data (stretch goal)
├── figures/
│   ├── 1_applications_per_year.png       # Application trends
│   ├── 2_score_spread.png                # Score distributions
│   ├── 3_organizations.png               # Top organizations
│   ├── 4_funding_and_scoring.png         # Funding + scoring breakdown
│   └── 5_priority_categories.png         # Priority analysis
├── figures_stretch_goal/
│   ├── stretch_10year_overview.png       # 10-year trends
│   └── stretch_period_comparison.png     # Period comparison
├── hw3_data_cleaning.py                  # Main cleaning script
├── hw3_visualizations.py                 # Visualization script
├── hw3_stretch_goal_cleaning.py          # Historical data cleaning
├── hw3_stretch_goal_viz.py               # 10-year comparison viz
└── README.md
```

## Quick Start

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

### Basic Usage

```bash
# 1. Clean the data
python hw3_data_cleaning.py

# 2. Generate visualizations
python hw3_visualizations.py

# 3. (Optional) Stretch Goal - 10-year comparison
python hw3_stretch_goal_cleaning.py
python hw3_stretch_goal_viz.py
```

### Output

- **Cleaned Data**: `output/cleaned_data.csv` (98 records)
- **Figures**: `output/figures/` (5 PNG files, 300 DPI)
- **Stretch Goal**: `output/` (2 additional PNG files)

## 📊 Data Overview

### 2022-2026 Dataset (Primary)
```
Records: 98 applications
Years: 2022-2025 (4 years)
Categories: Social Services (68%), Construction/Development (32%)
Priority Distribution:
  - ANGHP (Homeless): 50%
  - NI (Infrastructure): 30%
  - EO (Economic): 15%
  - HA (Housing): 5%
```

### Data Quality
- **Total Score**: 98% complete
- **Scoring Breakdown**: 70% complete (4 components × 98 records)
- **Funding Awards**: 87% complete

## 🔍 Analysis Components

### 1. Application Trends
- Year-over-year application volume
- Category-specific trends (Social Services vs Construction/Development)
- Identifies growth/decline patterns

### 2. Score Analysis
- Distribution by year and category
- Average score trends
- Quality metrics over time
- **Scoring Breakdown**: 
  - Priority Impact/Goal (30 pts)
  - Guiding Principles (30 pts)
  - Capacity to Deliver (25 pts)
  - Collaboration/Partnership (15 pts)

### 3. Organizational Analysis
- Top 15 organizations by application count
- Funding success rates
- Multi-year participation patterns

### 4. Funding Patterns
- Request vs award distributions
- Average funding trends by category
- Total funding allocation analysis

### 5. Priority Categories
- ANGHP: Addressing Needs of Growing Homeless Population
- EO: Economic Opportunity
- NI: Neighborhood Investment and Infrastructure
- HA: Housing Availability

## 📈 Key Findings (Stretch Goal)

**Comparing 2016-2022 vs 2022-2026:**

| Metric | Change | Interpretation |
|--------|--------|----------------|
| Application Volume | **-39.5%** | Fewer but more focused applications |
| Average Score | **+1.55 pts** | Higher quality applications |
| Average Request | **+38.1%** | Larger, more ambitious projects |
| ANGHP Priority | **+14.8%** | Increased focus on homelessness |

## 🛠️ Technical Details

### Data Cleaning Features

- **Intelligent Column Detection**: Automatically identifies columns across different Excel formats
- **Multi-Year Processing**: Handles 4 different worksheet structures
- **Summary Row Removal**: Filters out total/subtotal rows
- **Category Standardization**: Normalizes application types and priorities
- **Missing Data Preservation**: Maintains data integrity with NaN values

### Code Quality

- ✅ Comprehensive English documentation
- ✅ Modular design with reusable functions
- ✅ Robust error handling
- ✅ Automatic file path detection
- ✅ Clear variable naming
- ✅ PEP 8 compliant

### Example: Intelligent Column Detection

```python
col_idx = {
    "Type": next((i for i, c in enumerate(cols) 
                  if "type" in str(c).lower()), 1),
    "Priority": next((i for i, c in enumerate(cols) 
                      if "priority" in str(c).lower()), 2),
    # Adapts to different column names across years
}
```

## 📝 Missing Data Strategy

**Philosophy**: Preserve all NaN values for transparency

- **Funding_Award NaN**: Application not yet awarded
- **Total_Score NaN**: Application not yet scored
- **Score Breakdown NaN**: Format change in 2025-26 data

**Why This Matters**:
- Maintains data integrity
- Shows true state of data
- Pandas/Matplotlib automatically handle NaN correctly
- No artificial patterns introduced

See `MISSING_DATA_GUIDE.md` for detailed documentation.

## 🎨 Visualization Best Practices

All visualizations follow professional standards:

- **High Resolution**: 300 DPI for publication quality
- **Clear Labels**: All axes, titles, and legends properly labeled
- **Category Separation**: Social Services vs Construction/Development
- **Color Coding**: Consistent color scheme across all charts
- **Appropriate Chart Types**: Box plots for distributions, bar charts for comparisons, etc.

## 🔄 Reproducibility

To reproduce the analysis:

1. **Clone the repository**
   ```bash
   git clone https://github.com/zongyang078/Survey-Analysis-and-Data-Formatting.git
   cd Survey-Analysis-and-Data-Formatting
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Ensure data files are in correct location**
   ```bash
   # Data files should be in ./data/ directory
   ls data/
   # Should show: 2022-2026_Case_Data.xlsx, 2016-2022_Case_Data.xlsx
   ```

4. **Run the analysis**
   ```bash
   python hw3_data_cleaning.py
   python hw3_visualizations.py
   ```

## 📚 Requirements Analysis

This project fulfills all requirements from the Portland Community Needs brief:

| Requirement | Status | Evidence |
|-------------|--------|----------|
| Applications per year | ✅ | Figure 1 |
| Score spread per year | ✅ | Figure 2 |
| Applications per organization | ✅ | Figure 3 |
| Funding requests + scoring breakdown | ✅ | Figure 4 |
| Priority categories | ✅ | Figure 5 |
| Category separation (SS vs CON) | ✅ | All figures |
| Easy to understand | ✅ | Professional charts |
| **Stretch Goal: 10-year comparison** | ✅ | Additional figures |

## 🤝 Contributing

This project was developed as part of a data analysis course. For questions or suggestions:

- Open an issue
- Submit a pull request
- Contact: [Your Email]

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **Portland Community Needs** - For providing the dataset and project requirements
- **Rowen McAllister** - City of Portland Housing and Economic Development Department
- **Course Instructors** - For project guidance and feedback

## 📞 Contact

**Author**: Zongyang Li  
**GitHub**: [@zongyang078](https://github.com/zongyang078)  
**Project Link**: [Survey-Analysis-and-Data-Formatting](https://github.com/zongyang078/Survey-Analysis-and-Data-Formatting)

---

**Note**: This project analyzes real CDBG grant data from the City of Portland. All data is used for educational purposes in accordance with public record access policies.

**Last Updated**: February 2, 2026  
**Version**: 1.0.0  
**Status**: ✅ Complete
