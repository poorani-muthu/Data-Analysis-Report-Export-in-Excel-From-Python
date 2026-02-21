
**Airline Safety Dashboard Generator**
<br>Professional single-sheet Excel dashboard with charts, borders, and exact cell layout<br><br>

🚀 Features

<br>Executive Summary - Key metrics + Top 5 safest airlines
<br>Risk Heatmap - Top 10 highest-risk airlines with color-coded scores
<br>Interactive Charts - Bar chart (Top 10 safest) + Pie chart (Risk distribution)
<br>Professional Styling - Colors, borders, center alignment, precise column widths
<br>Risk Scoring - Normalized safety scores (0-100) based on fatalities per ASK
<br>Exact Cell Layout - Pixel-perfect positioning for charts and tables<br><br>

📊 Data Source
<br>FfiveThirtyEight Airline Safety Dataset (1985-2014)

<br>56 airlines worldwide
<br>Available Seat Kilometers (ASK) exposure
<br>Fatal accidents and fatalities (85-99, 00-14)<br><br>

<br>🛠 Requirements
<br>pip install pandas openpyxl numpy

<br>Download dataset:
<br>curl -O https://raw.githubusercontent.com/fivethirtyeight/data/master/airline-safety/airline-safety.csv<br><br>

🎯 Quick Start
<br>python air_travel_safety.py
<br>Output: Airline_Safety_Dashboard_EXACT.xlsx<br><br>


🔬 Safety Score Calculation
 
<br>textSafety Score = 100 × (    0.6 × (1 - fatal_rate_00_14/max_rate) +    0.4 × (1 - fatal_acc_rate_00_14/max_acc_rate))
<br>Risk Levels:🔴 HIGH:    0-40🟡 MEDIUM: 41-65  🟢 LOW:    66-85✅ SAFE:   86-100
<br>Where:
<br>fatal_rate_00_14 = fatalities per billion ASK (2000-2014)
<br>fatal_acc_rate_00_14 = fatal accidents per billion ASK (2000-2014)<br><br>

🎨 Design Features

<br>Feature	Implementation
<br>Colors	Primary blue (1F4E79), Success green (70AD47), Danger red (C00000)
<br>Borders	Thin black borders on all data tables
<br>Alignment	Center-aligned text/numbers with wrap_text
<br>Charts	Native Excel bar + pie charts with exact cell references
<br>Typography	Bold headers (12-20pt), emoji risk indicators<br><br>
 

📈 Charts

<br>Bar Chart (E18): Top 10 safest airlines by safety score
<br>Pie Chart (E32): Risk distribution across 4 categories<br><br>

🔧 Customization

<br># python Edit these in DashboardConfig.COLORS 'primary_blue': '1F4E79'    
<br># Main headers'success_green': '70AD47'   
<br># Safe airlines'danger_red': 'C00000'      
<br># Risk headers
<br># Column widths (pixels) column_widths = {'A':25.91, 'B':12.64, 'C':13, 'D':11, ...}<br><br>

🐛 Troubleshooting

<br>Issue	Solution
<br>FileNotFoundError	Download airline-safety.csv to working directory
<br>MergedCell error	Values set BEFORE merge_cells()
<br>Charts not showing	Check exact cell references match data ranges
<br>Misaligned tables	Verify column_widths dictionary<br><br>
 

📄 License
<br>MIT License - Feel free to use and modify!<br><br>

🙌 Acknowledgements
<br>FiveThirtyEight - Original dataset
<br>openpyxl - Excel generation
