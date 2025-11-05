
# Flower Exports Analysis 2024
**Final Project – Data Analytics**

This project analyzes international flower exports from multiple countries to the U.S. The analysis includes data cleaning, manipulation, visualization, and statistical insights.


## Documentation

[Documentation](https://linktodocumentation)


# Dataset Information
**File name:** `flower_exports_2024.csv`  
**Rows:** 660 | **Columns:** 17  
**Main columns include:**
- Export_ID  
- Flower_Type  
- Country_Origin  
- Quantity_Tons  
- Unit_Price_USD  
- Total_Value_USD  
- Shipment_Method  
- Temperature_Celsius  
- Humidity_Percent  
# DATA CLEANING
1. Check for missing values.
2. Remove duplicate rows.
3. Convert the 'Export_Date' column to datetime format.
4. Review the data types of all columns.
5. Renamed unclear columns for clarity. 

# DATA MANIPULATION
**SORTERING.** I applied multi-level sorting to identify the largest and most valuable flower exports. For instance, I sorted the dataset by Quantity_Tons, Total_Value_USD, and Unit_Price_USD to reveal the top shipments. Additionally, I used sorting to analyze which flower types and countries had the highest prices and most efficient transport conditions.  I used the sort_values() method to organize the dataset from highest to lowest based on several variables quantity, unit price, total value, temperature, and humidity. This allowed me to easily identify the largest and most valuable flower shipments, as well as analyze how environmental conditions varied across them.

-**Which countries export the most expensive flowers in terms of unit price?**

The countries that export the most expensive flowers based on unit price are: Mexico at $9.99 for roses, Ecuador at $9.73 for roses, and Kenya at $9.41 for roses, while Colombia exports chrysanthemums at $0.54.

-**Which country has the largest shipment volume in tons**
Colombia has the highest shipment at 4,990 tons, followed by the Netherlands with 590 tons.

-**Which country had the highest total value in its exports?** Colombia had the highest total export value, amounting to 23,942.40 thousand USD, followed by the Netherlands, with a total export value of 3,363.36 thousand USD.

-**Which flowers have the highest unit price?** 
The flowers that have the highest unit values are the alstroemerias from Ecuador, which have a maximum value of 7.15 and a minimum value of 5.76. Additionally, tulips from Colombia have a maximum value of 0.70 and a minimum value of 0.56.

-**Which ocean shipments had the longest transit time?**
Kenya experiences the longest sea shipment delays, with a maximum delay of 25 days and a minimum delay of 23 days. Colombia follows with a delay of 2 days.

-**Which air shipments had the longest transit time?**
Colombia has the longest air shipping time at 10 days, while Mexico and the Netherlands each have a shipping time of 1 day.

-**Which country exports were carried out under the best conditions, specifically with moderate temperatures and stable humidity?**
Ecuador, Kenya, and the Netherlands have an average temperature of 0.6 degrees Celsius, while Colombia has an average temperature of 8 degrees Celsius. In terms of humidity, Ecuador, Kenya, and the Netherlands have an average humidity level of 90%, whereas Colombia has an average of 75%.


**FILTERING** used conditional filters to explore specific subsets of the dataset. For example, I isolated exports from Colombia, air shipments, and high-value transactions exceeding 1,000 tons. This allowed me to focus on relevant data for deeper analysis.

-**Which country exported more than 1,000 tons of flowers?**
Colombia is the only country that exports over 1,000 tons of flowers to the United States.

-**Which exports exceeded $500,000 in total value?**
In 2024, Colombia's exports surpassed $500,000.

-**Which flower types were shipped with humidity levels above 90%?**
The flowers most commonly transported at levels above 90% are gypsophila and roses from Ecuador.



**GROUPING.** I used the groupby() function to summarize data by categorical variables. For instance, I calculated the total export quantity per country and identified which shipment method (Air or Sea) was most frequently used by each of the five exporting countries.

-**Which flower type was exported the most (in tons)?**
The most exported flower types to the United States in 2024 were carnations, with 298,739 tons; chrysanthemums, with 287,892 tons; alstroemerias, with 279,910 tons; roses, with 220,646 tons; and tulips, with 206,337 tons.

-**Which country exported the largest total quantity?**
The country that exported the most flowers to the United States in 2024 was Colombia, with 216,706 tons, followed by Kenya with 37,745 tons, Mexico with 37,621 tons, the Netherlands with 37,436 tons, and finally Ecuador with 35,140 tons.

-**What is the average total value per shipment method (Air vs Sea)?**
The average value of exports is as follows: exports by air amount to $77,004.27 thousand, while exports by air specifically total $6,520.57 thousand USD. 

-**What is the average transport temperature by flower type?.** The average transport temperature varies based on the type of flower, as indicated below:
| Flower_Type |Temperature Celcius|
|:-----------:|:-------------:|
| Gypsophila |2.3|
| Lily |2.3|
| Marigold | 2.5 |
| Hypericum | 2.5 |
| Eryngium | 2.9 |
| Gerbera | 3.0 |
| Rose | 4.3 |
| Chrysanthemum| 4.5 |
| Carnation | 4.6 |
| Alstroemeria | 4.7 |
| Tulip | 4.9 |


-**Which destination cities received the highest total flower value?>** The U.S. cities that received the most flowers in tons were:

 City | Tons|
|:-----------:|:-------------:|
| Miam, Fl | 602.680 |
| Los Angeles, Ca |227.739|
| New York, NY | 182.583|
| Chicago, IL| 123.169 |
| Dallas, TX | 84.787 |
| Atlanta, GA | 73.350 |
| Seattle, WA | 39.400 |
| Houston, TX| 309 |

-**Which shipment method (Air or Sea) was most used by the five countries?.** The shipping method most commonly used by the five countries was

| Country | Air | Sea |
|:---------:|:---------:|:---------:|
| Colombia|250  |250  |
| Ecuador | 32 | 8 |
| Kenya |32  | 8 |
| Mexico| 24 | 16 |
| Netherlands|35  | 5 |



**MERGING.** To enrich the analysis, I created a complementary dataset that linked each exporting country to its respective continent. Using the pd.merge() function, I combined this secondary table with the main flower exports dataset on the common column Country_Origin.
This merge allowed me to include a new column called “Continent”, which connects each record with its geographical region (South America, Europe, Africa, or North America). I created a new dataset named "flower_exports_2024_final.csv" and downloaded it.
After merging, I was able to perform deeper analyses, such as:

-**Which continent is the largest exporter of flowers?**
South America is the largest exporter of flowers, with a total of 1,251,846 exports.

-**Which continent has the highest total exports value?**
South America has the highest total export value, amounting to 3,729,243.01 thousand million dollars.


**RESHAPING THE DATA.** (Pivot Table — Flower Type vs Packaging Type): I created a pivot table to compare the quantity of flowers exported by flower type and packaging type. Each row represents a flower type and each column represents a packaging method (e.g., Box, Crate, Plastic Wrap, etc.). This analysis revealed that alstroemeria is the most exported flower, with a total of 111,411 tons, followed by carnations with 97,231 tons and chrysanthemums with 75,663 tons. In terms of packaging, the most commonly used types were boxes, followed by corrugated boxes and crates
| Type of flower | Box | Corrugated box | Crate | Plastic crate | Plastic Wrap | Sleeved Box| Ventilated Box|
|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
| Alstroemeria | 111.411 |810  |  75.382|  997| 84.927 | 5.490 | 893 |
| Carnation | 97.231 | 2.945 | 101.541  | 1.137 | 86.493 | 5.789  | 3.603 |
| Chrysanthemum| 75763 | 8.156 | 91.990 | 4.632 | 101.627  | 2.553  | 3.171 |



# DATA VISUALIZATION
-**Flower Type vs Quantity vs Country of Origin.** I created a grouped bar chart to compare the total tons of flowers exported by flower type and country of origin. Each color on the chart represents a different exporting country. The Y-axis displays the total quantity in tons, while the X-axis represents the various flower types.  The chart indicates that Colombia leads in overall exports, particularly for Alstroemeria, chrysanthemums, and carnations, whereas Ecuador specializes more in roses. Kenya specializes in hypericum and eryngium, Mexico focuses on lilies, marigolds, and roses, and the Netherlands is recognized for gerberas, chrysanthemums, and tulips. 

### Flower Type vs Quantity vs Country of Origin
![Flower Type vs Quantity vs Country of Origin](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Flower%20Type%20vs%20Quantity%20vs%20Country%20of%20Origin.png?raw=true)


-**Bubble Map — Flower Type vs. U.S. Destination City.** This visualization was created using Plotly Graph Objects (Scattergeo). Each bubble on the map represents a U.S. city that imports flowers from various countries. The map legend includes the following information:

-Bubble Size: indicates the total tons of flowers imported.
-Color: represents the type of flower.
-Tooltip: Shows the city name and the total tonnage.
The map demonstrates that Miami, New York, and Los Angeles are the primary hubs for flower imports in the U.S. The most commonly imported flower types include carnations, chrysanthemums, roses, and tulips.

### U.S. Flower Import Destination
![U.S. Flower Import Destination](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/U.S%20Flower%20Import%20Destination.png?raw=true)


-**Total Export Value by Country of Origin.** This bar chart illustrates the total export value generated by each flower-exporting country. Colombia leads with the highest export value at $3,500,000,000 thousands of USD, followed by Mexico and Kenya, each contributing $250,000 thousands of USD. The results indicate that while multiple countries participate in flower exports, Colombia dominates both in volume and revenue, reinforcing its position as a global leader in the flower industry.

### Total Export Value by Country of Origin
![Total Export Value by Country of Origin](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Total%20Export%20Value%20by%20Country%20of%20Origin.png?raw=true)


-**Average Export Value vs Month vs Country.** This line chart shows how the average export value changes over time for each country of origin. Colombia consistently maintains the highest export value throughout the year, followed by Ecuador and the Netherlands, highlighting their strong market presence.

### Average Export Value
![Average Export Value](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Averague%20export%20value%20.png?raw=true)


-**Shipment Method vs. Country of Origin.** This grouped bar chart compares the shipment methods used by various flower-exporting countries to the United States.The results indicate that Colombia primarily exports its flowers by sea. In contrast, Kenya, the Netherlands, and Ecuador predominantly use air transport, likely due to the distance involved and the perishable nature of the product. Mexico employs both shipment methods. This analysis highlights how logistics strategies and geographical factors influence export decisions. 


### Shipment Method by Country
![Shipment Method by Country](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Shipment%20Method%20by%20country.png?raw=true)

**STATISCAL ANALYSIS** 

**DESCRIPTIVE STATISTICS.** The descriptive statistics summarize the key numerical variables of the flower export dataset.
 -In 2024, the average export of flowers from various countries to the United States was 2,067.64 tons, with a maximum of 4,990 tons and a minimum of 120 tons.

-The average unit price was $3.67 USD, ranging from $0.50 to $9.99, showing price diversity across flower types and quality grades.

-The average transit time was 5.6 days, while the temperature and humidity averages (4.37°C and 74.3%) indicate controlled conditions to preserve flower quality during shipment.
Overall, the data shows consistent export activity throughout 2024 with a wide range of shipment sizes and export values, influenced by different flower types, destinations, and shipment methods.


#**MEASURES OF CENTRAL TENDENCY (MEAN, MEDIAN, AND MODE)**


To better understand the behavior export, the mean, median, and mode were calculated for Quantity_Tons, Unit_Price_USD, and Total_Value_USD.

In 2024, an average of 2,067.64 tons of flowers were exported to the United States. The average price per flower was $3.67, although the most frequently observed price was $1.36. Overall, the total sales for that year amounted to approximately $6,730.91 thousand.


**CORRELATION ANALYSIS**

The correlation heatmap reveals key relationships among export variables.
\

![Correlation Analysis](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Correlation.png?raw=true)


-The strongest positive relationship (r = 0.72) occurs between Quantity_Tons and Total_Value_USD, indicating that export volume directly drives total revenue.

-There is a moderate negative correlation (r = -0.30) between Quantity_Tons and Unit_Price_USD, suggesting that larger shipments tend to have lower per-unit prices.

-Additionally, Humidity_Percent shows a moderate positive correlation with Unit_Price_USD (r = 0.48), possibly indicating that flowers requiring controlled humidity conditions are higher-value exports.
Overall, the dataset shows logical and realistic relationships that align with export and logistics dynamics.


| Variable | Correlation| Interpretation |
|:---------:|:---------:|:---------:|
| Quantity_Tons vs Total_Value_USD| 0.72 (strong positive) | As export quantity increases, the total export value also increases. This makes sense since total value depends directly on shipment volume |
| Quantity_Tons vs Unit_Price_USD | -0.30 (moderate negative) | Larger export volumes tend to have lower unit prices, possibly due to bulk discounts or lower shipping costs per unit. |
| Unit_Price_USD vs Total_Value_USD | 0.31 (moderate positive) | Higher unit prices contribute to higher total export values, though the impact is smaller compared to export volume|
| Temperature_Celsius vs Quantity_Tons | 0.28 (slight positive) | Slightly higher temperatures may be associated with larger shipments, possibly reflecting tropical flower varieties.|
| Humidity_Percent vs Unit_Price_USD | 0.48 (moderate positive) | Flowers requiring higher humidity levels tend to be higher-value exports, indicating more delicate or premium types. |
| Temperature_Celsius vs Humidity_Percent | -0.33 (moderate negative) | As temperatures rise, humidity typically decreases, reflecting a common environmental relationship. |



**DISTRIBUTION ANALYSIS**

The variable Total_Value_USD was chosen for the distribution analysis because it best represents the economic outcome of each flower export transaction. This variable captures the combined effect of both export volume and unit price, making it ideal for understanding revenue patterns. The distribution of total export values (USD) shows a clear right-skewed pattern.
Most flower export transactions fall within the $3,000–$6,000 range, indicating that mid-sized exports are the most common. A few high-value shipments significantly raise the overall average, suggesting that a small number of large transactions contribute disproportionately to total revenue. This pattern aligns with typical international trade behavior, where large-volume exports play a major economic role.

![Distribution Analysis](https://github.com/marcelarodriguez182/Final-Project-Phyton-2025/blob/main/visualizations/Distrubution.png?raw=true)
