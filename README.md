# Streaming Wars: Platform Strategy & Predicted Revenue

## Project Summary
This project analyzes how movies perform across streaming platforms and predicts box office revenue using IMDb-based data. It combines platform matching logic, ROI calculations, and regression-based modeling to deliver a business-focused, data-driven dashboard in Tableau.

---
Key Insights
- Prime Video Dominates in Genre Breadth.
    With over 1,000 titles, Prime Video had the widest genre variety, appearing across nearly every top genre combo.
- HBO Max Delivers the Highest ROI
    despite a smaller title count. HBO Max led in average return on investment, proving that quality beats quantity.
- Predicted Gross Tracks Strongly with Budget & Ratings.
    Movies with budgets above $100M and ratings over 8.0 consistently projected grosses exceeding $500M in the model.
- Director Impact is Huge.
Names like James Cameron and the Russo Brothers averaged over $1.5B in box office gross per film, highlighting the power of star directors.
- Post 2010 Streaming Surge,
release volume climbed sharply after, ultimately peaking before COVID-19 which caused a noticeable dip between 2020–2021.
- Genre-Platform Relationships Are Clear
	•	Netflix favors action/thriller blends
	•	Disney+ focuses on animation-heavy content
	•	HBO Max leans into drama and prestige genres
 
## Tools & Languages
- **Python** – pandas, scikit-learn, matplotlib  
- **SQL** – MySQL Workbench for early filtering  
- **Tableau** – for all visual storytelling  
- **GitHub** – project documentation and file hosting

---

## Focus Areas
- Assigning movies to optimal streaming platforms  
- Calculating ROI and modeling predicted gross  
- Analyzing viewer ratings and genre trends  
- Visualizing content release patterns and top directors

---

## Key Features
- **Platform Matching Logic** based on genre, rating, and runtime  
- **Predicted Gross Modeling** from budget, rating, and runtime  
- **Top Genres by Platform** visualized via grid and bar charts  
- **Top Directors by Average Gross**  
- **Release Trends Over Time**  
- Uniform **orange–red–gold** color theme for dashboard visuals

---



## 💻 Code Preview
```python
# Convert release date & calculate ROI
df['releaseDate'] = pd.to_datetime(df['releaseDate'], errors='coerce')
df['Release Year'] = df['releaseDate'].dt.year
df['ROI'] = (df['gross'] - df['budget']) / df['budget']

# Assign suggested streaming platform
def assign_platform(row):
    if row['averageRating'] >= 7.5 and row['runtimeMinutes'] >= 100:
        return 'HBO Max'
    elif 'Animation' in str(row['genres']) or row['runtimeMinutes'] < 90:
        return 'Disney+'
    elif row['averageRating'] >= 6.5:
        return 'Prime Video'
    else:
        return 'Netflix'

df['suggestedPlatform'] = df.apply(assign_platform, axis=1)
```

---

## 📊 Tableau Dashboard  
> Hosted on Tableau Public  
> 🔗 [https://public.tableau.com/app/profile/ruona.ogrih/viz/FilmROI/StreamingROIDashboard]

- Genre x Platform Grid  
- Average Viewer Rating by Platform  
- Predicted Gross Bubble Chart  
- Top Directors by Gross  
- Release Trends Line Chart  
- Suggested Platform Pie Chart

---

## Repo Structure
```
📁 Streaming-Wars-Project/
├── README.md
├── imdb_data.csv
├── imdb_with_roi.csv
├── platform_assignment.py
├── images/
│   ├── dashboard_cover.png
│   ├── genre_grid.png
│   └── predicted_gross.png
```]

- Genre x Platform Grid  
- Average Viewer Rating by Platform  
- Predicted Gross Bubble Chart  
- Top Directors by Gross  
- Release Trends Line Chart  
- Suggested Platform Pie Chart

---

## 📁 Repo Structure
```
📁 Streaming-Wars-Project/
├── README.md
├── imdb_data.csv
├── imdb_with_roi.csv
├── platform_assignment.py
├── images/
│   ├── dashboard_cover.png
│   ├── genre_grid.png
│   └── predicted_gross.png
```
