# Spotify Listening Behavior Analysis: Interview Explanation

## Problem Statement

"Music streaming platforms like Spotify generate vast amounts of user data, but without proper analysis, this data remains underutilized. My project aimed to uncover meaningful patterns in Spotify listening behavior over a 12-year period (2013-2020) to understand user preferences, platform usage, and temporal listening habits. The goal was to transform raw streaming data into actionable insights that could inform business decisions around user engagement, content recommendations, and platform development."

## Tools Used

1. **Excel**: For initial data cleaning and preparation
   - Standardized timestamps, artist names, and track names
   - Handled missing values and inconsistencies
   - Created preliminary pivot tables for basic analysis

2. **Power BI**: For advanced analysis and visualization
   - Built interactive dashboards
   - Created calculated measures using DAX
   - Developed time intelligence metrics
   - Implemented dynamic filtering with slicers

## Key Insights Generated

### Content Preferences
1. **Top Artists**: The Beatles and The Killers emerged as consistently popular artists across the years
2. **Top Albums**: "The New Abnormal" by The Strokes and various Beatles albums were most streamed
3. **Popular Tracks**: "Ode to the Mets" and "The Return of Kings" had the highest streaming numbers

### Platform Analysis
- **Android dominated** with 25K engagements (as shown in D1.png)
- Cast to device was the second most popular platform
- iOS and Windows showed significant but lower usage

### Temporal Patterns
1. **Daily Patterns**:
   - Peak listening hours were between 6 PM to 12 AM
   - Highest activity at 10 PM (22K streams as shown in D2.png)
   
2. **Weekly Patterns**:
   - Fridays were the busiest days
   - Wednesdays also showed high activity
   
3. **Monthly Patterns**:
   - October was the most active month
   - April, August, and December also showed significant activity (as per D1.png)

## Visualization Strategy

I carefully selected visualization types to best represent different insights:

1. **Bar Charts** (Used in both D1 and D2):
   - For comparing artists, albums, and tracks
   - Example: Comparing streaming minutes for "The New Blower real" vs "Imploding The Mirage"

2. **Cards** (Prominent in D1):
   - To highlight key metrics like:
     - Total Albums (7,907)
     - Total Artists (4,112)
     - Total Minutes (320K)

3. **Tables** (Used in both files):
   - For displaying detailed numerical comparisons
   - Example: The +12K, +47K, +37K comparison of track popularity

4. **Line Charts** (Implied in analysis):
   - For showing trends over time (hours, days, months)
   - Example: The listening pattern across different hours of the day

5. **Slicers and Filters**:
   - Enabled interactive exploration of the data
   - Allowed users to filter by year, month, platform etc.

## Technical Implementation

1. **DAX Measures**:
   - Created calculations for totals (albums, artists, minutes)
   - Developed time intelligence metrics (YOY comparisons)

2. **Data Modeling**:
   - Established relationships between different data tables
   - Created date tables for proper time analysis

3. **Data Transformation**:
   - Extracted components from timestamps (hour, day, month)
   - Standardized categorical data (platforms, artists)

## Business Impact

These insights could help Spotify:
1. **Optimize server loads** by anticipating peak usage times
2. **Improve recommendations** by understanding artist/track popularity patterns
3. **Guide marketing efforts** by knowing when users are most active
4. **Allocate resources** effectively across different platforms

## Challenges & Solutions

1. **Data Quality Issues**:
   - Solution: Implemented thorough cleaning process in Excel before analysis

2. **Time Zone Variations**:
   - Solution: Standardized all timestamps to UTC before analysis

3. **Duplicate Entries**:
   - Solution: Created unique identifiers for each streaming event

This analysis demonstrates how raw data can be transformed into strategic insights that drive business decisions in the music streaming industry. The combination of careful data preparation, appropriate visualization choices, and thoughtful analysis resulted in actionable findings that could directly impact Spotify's operations and strategy.
