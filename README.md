# FAA Airline On-Time Performance Analysis

## Project Overview

This project analyzes the U.S. Department of Transportation's Airline On-Time Performance dataset for **June 2018**. The analysis examines flight delays, cancellations, and operational patterns across 17 major U.S. airlines and hundreds of airports.

**Live Website**: https://hongzhewang0922.github.io/DSAN-6300_mini_project/

## Key Findings

- Southwest Airlines demonstrated the best reliability with minimal delays
- Pago Pago Airport experienced the highest average departure delays (77.6 minutes)
- Friday was the busiest travel day with over 108,000 flights
- 10,693 flights were cancelled, primarily due to carrier and weather issues

## Dataset

- **Source**: U.S. Department of Transportation Bureau of Transportation Statistics
- **Period**: June 2018
- **Total Flights**: ~626,217
- **Airlines**: 17 major U.S. carriers
- **Airports**: 296 departure airports

## Technologies Used

- **Database**: MySQL (AWS RDS)
- **Data Analysis**: SQL
- **Visualization**: R (ggplot2, plotly)
- **Publishing**: Quarto + GitHub Pages

## Repository Structure

```
.
├── index.qmd                 # Main analysis document
├── _quarto.yml              # Quarto configuration
├── styles.css               # Custom CSS styling
├── miniproj_*.csv           # Query results data
├── .nojekyll                # GitHub Pages configuration
└── README.md                # This file
```

## How to Build Locally

1. Install [Quarto](https://quarto.org/docs/get-started/)
2. Install R and required packages:
   ```r
   install.packages(c("tidyverse", "plotly", "DT", "scales"))
   ```
3. Clone this repository
4. Run: `quarto render`
5. Open `docs/index.html` in your browser

## SQL Queries

The analysis answers 7 key questions:

1. Maximum departure delays by airline
2. Maximum early departures by airline  
3. Flight volume ranking by day of week
4. Airport with highest average departure delay
5. Each airline's worst-performing airport
6. Cancellation analysis (count and reasons)
7. 3-day rolling average of daily flights

## Author

**Hongzhe Wang** (hw530)  
Georgetown University  
Database Management Systems - Mini Project

## License

This project is created for educational purposes as part of coursework at Georgetown University.

## Acknowledgments

- U.S. Department of Transportation for providing the data
- Professor and TAs for project guidance
- Georgetown University Database Management Systems course
