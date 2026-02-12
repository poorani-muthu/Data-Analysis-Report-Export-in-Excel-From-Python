
Airline Safety Dashboard Generator
Professional single-sheet Excel dashboard with charts, borders, and exact cell layout

🚀 Features

Executive Summary - Key metrics + Top 5 safest airlines
Risk Heatmap - Top 10 highest-risk airlines with color-coded scores
Interactive Charts - Bar chart (Top 10 safest) + Pie chart (Risk distribution)
Professional Styling - Colors, borders, center alignment, precise column widths
Risk Scoring - Normalized safety scores (0-100) based on fatalities per ASK
Exact Cell Layout - Pixel-perfect positioning for charts and tables

📊 Data Source
FfiveThirtyEight Airline Safety Dataset (1985-2014)

56 airlines worldwide
Available Seat Kilometers (ASK) exposure
Fatal accidents and fatalities (85-99, 00-14)

🛠 Requirements
pip install pandas openpyxl numpy

Download dataset:
curl -O https://raw.githubusercontent.com/fivethirtyeight/data/master/airline-safety/airline-safety.csv

🎯 Quick Start
python air_travel_safety.py
Output: Airline_Safety_Dashboard_EXACT.xlsx

🏗 Dashboard Layout
 
 │ ✈️ AIRLINE SAFETY EXECUTIVE │ 🔥 TOP 10 HIGHEST RISK      ││ DASHBOARD 1985-2014 (A1:H3)  │ AIRLINES (D5:H6)            │├─────────────┬────────────────┼──────────────────────────────┤│ 🎯 KEY      │ Total Airlines │ Rank | Airline | Score |Risk││ METRICS     │ 56             │  1   | ...     |  12  |🔴HIGH││ (A7:B7)     │ Top Score: 98  │  ... | ...     |  ... | ... ││             │ High Risk: 3   │      |         |      |     │├─────────────┼────────────────┼──────────────────────────────┤│ 🏆 TOP 5    │ Air India      │ 98/100│✅ SAFE │      │     ││ SAFEST      │ Emirates       │ 97/100│✅ SAFE │      │     ││ AIRLINES    │ ...            │ ...  │ ...    │      │     ││ (A11:B16)   │                │      │        │      │     │└─────────────┴────────────────┴──────────────────────────────┘          │ 📊 INTERACTIVE SAFETY RANKINGS & CHARTS (A19:D20) │          ├─────────────────────────────────────────────────────┤🏆 TOP 10 │ 📊 Safety │ 📈 Risk    │Charts                      │SAFEST   │Comparison │Distrib.   │Bar + Pie Charts (E18:E32)  │(A21:D33)│(A36:B45) │(C36:D39) │                            │          └─────────────────────────────────────────────────────┘

🔬 Safety Score Calculation
 
textSafety Score = 100 × (    0.6 × (1 - fatal_rate_00_14/max_rate) +    0.4 × (1 - fatal_acc_rate_00_14/max_acc_rate))Risk Levels:🔴 HIGH:    0-40🟡 MEDIUM: 41-65  🟢 LOW:    66-85✅ SAFE:   86-100
Where:

fatal_rate_00_14 = fatalities per billion ASK (2000-2014)
fatal_acc_rate_00_14 = fatal accidents per billion ASK (2000-2014)

🎨 Design Features
Feature	Implementation
Colors	Primary blue (1F4E79), Success green (70AD47), Danger red (C00000)
Borders	Thin black borders on all data tables
Alignment	Center-aligned text/numbers with wrap_text
Charts	Native Excel bar + pie charts with exact cell references
Typography	Bold headers (12-20pt), emoji risk indicators
 

📈 Charts
Bar Chart (E18): Top 10 safest airlines by safety score
Pie Chart (E32): Risk distribution across 4 categories

🔧 Customization
 python# Edit these in DashboardConfig.COLORS'primary_blue': '1F4E79'    # Main headers'success_green': '70AD47'   # Safe airlines'danger_red': 'C00000'      # Risk headers# Column widths (pixels)column_widths = {'A':25.91, 'B':12.64, 'C':13, 'D':11, ...}

🐛 Troubleshooting
Issue	Solution
FileNotFoundError	Download airline-safety.csv to working directory
MergedCell error	Values set BEFORE merge_cells()
Charts not showing	Check exact cell references match data ranges
Misaligned tables	Verify column_widths dictionary
 

📄 License
MIT License - Feel free to use and modify!

🙌 Acknowledgements
FiveThirtyEight - Original dataset
openpyxl - Excel generation
