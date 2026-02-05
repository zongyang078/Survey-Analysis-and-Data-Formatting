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
│   ├── 2022-2026 Case Data.xlsx          # Primary dataset
│   └── 2016-2022 Case Data.xlsx          # Historical data (stretch goal)
├── output/
│   ├── cleaned_data_2022_2026.csv          # Cleaned dataset (primary)
│   └── cleaned_data_2016_2022.csv          # Cleaned data (stretch goal)
├── report_assets/
│   ├── charts/       
│   └── tables/         
├── figures_stretch_goal/
│   ├── stretch_10year_overview.png       # 10-year trends
│   └── stretch_period_comparison.png     # Period comparison
├── hw3_data_cleaning.py                  # Main cleaning script
├── hw3_final_analysis.py                 # Visualization script
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
python hw3_final_analysis.py

# 3. (Optional) Stretch Goal - 10-year comparison
python hw3_stretch_goal_cleaning.py
python hw3_stretch_goal_viz.py
```

### Output

- **Cleaned Data**: `output/cleaned_data_2022_2026.csv` (98 records)
- **Figures**: `figures/` (5 PNG files, 300 DPI)
- **Stretch Goal**: `figures_stretch_goal/` (2 additional PNG files)

## Data Overview

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

## Analysis Components

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

## Technical Details

### Data Cleaning Features

- **Intelligent Column Detection**: Automatically identifies columns across different Excel formats
- **Multi-Year Processing**: Handles 4 different worksheet structures
- **Summary Row Removal**: Filters out total/subtotal rows
- **Category Standardization**: Normalizes application types and priorities
- **Missing Data Preservation**: Maintains data integrity with NaN values

## License

This project is licensed under the MIT License - see the LICENSE file for details.

**Note**: This project analyzes real CDBG grant data from the City of Portland. All data is used for educational purposes in accordance with public record access policies.
