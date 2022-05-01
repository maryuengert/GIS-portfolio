## Final Project: Determining New Tree Planting Sites in the City of Pittsburgh Using Suitability Analysis

For my final project, I chose to complete a suitability analysis to help the City of Pittsburgh Planning Department, in a fictional scenario, determine where to plant new trees to help restore the city's tree canopy. The suitability model uses criteria as inputs that adhere to goals laid out by the city:

* Equity: prioritize sites in historically neglected areas, such as neighborhoods with a high percentage of people of color and low-income areas
* Environment: plant in areas with less tree canopy cover, high land surface temperature, and high levels of daily traffic
* Vulnerability: prioritize areas with highly susceptible populations, such as elderly, young children, smokers, and people with asthma or other respiratory illnesses

*This project is based in concept on a Learn ArcGIS lesson, which can be found [here](https://learn.arcgis.com/en/projects/shade-equity-determine-tree-planting-locations-with-suitability-analysis/).*

### Methodology

Before inputting criteria into the suitability model, I collected all necessary data and cleaned the datasets to eliminate unnecessary variables, filter for rows appropriate to the analysis, create calculated fields necessary to the analysis, and join appropriate tables. Below are the data sources I used for this project:

**The Western Pennsylvania Regional Data Center**
Pittsburgh Trees (XY data), Daily Traffic counts (.csv), Smoking Rates (shapefile), Childhood Asthma Healthcare Utilization 2017 (.csv.), Pittsburgh Neighborhoods (shapefile), Pittsburgh census tracts 2016 (.csv)

**Census.gov**
2020 American Community Survey 5-year estimates for poverty and demographic characteristics (.csv)

**Mendeley Data**
US Urban Heat Island Database (.csv)

Once the data were cleaned and imported into ArcGIS Pro as feature classes, I performed several geoprocessing tasks to further derive the necessary variables for analysis and prepare the layers for the suitability model. These tasks included the following:

* Used “Summarize Within” tool to aggregate number of trees to the census tract level and create “Count of Trees” variable; Divided “Count” by Total Population for each census tract to create Trees Per Capita variable

* Used “Summarize Within” tool to take average of all traffic count data points in each census tract to get the overall average daily traffic count for each tract.

Once the feature classes were derived into raster data layers, I began the Suitability Model process. First, I added each layer as a criterion to the model and transformed the data using ArcGIS Pro’s built-in transformation process. This process converts each layer’s data to exist on a shared scale and allows the user to control how values are assigned a preference value in the model. For example, I used a transformation process on the smoking rate data to indicate that very large data values were the most preferred when selected tree planting sites. 

Once the data were transformed, I ran the suitability and location processes. To give the Department multiple options for determining tree planting sites, I ran the model several times using different criteria weights based on the City’s three key goals: equity, environment, and vulnerability. 

Model 1: Trees Per Capita weighted at 2, with all other criteria assigned a weight of 1

Model 2 (“Equity Model”): Trees Per Capita weighted at 2, equity criteria weighted at 1.5, with all other criteria assigned a weight of 1

Model 3 (“Environment Model”): Trees Per Capita weighted at 2, environment criteria weighted at 1.5, with all other criteria assigned a weight of 1

Model 4 (“Vulnerability Model”): Trees Per Capita weighted at 2, vulnerability criteria weighted at 1.5, with all other criteria assigned a weight of 1

Each of the models produced 5 regions suitable for further exploration by the Planning department.

### Results and Analysis

*Model 1 - Trees Per Capita Weighted*

<img width="524" alt="image" src="https://user-images.githubusercontent.com/81482638/166165732-d398e48c-8db1-4d88-aa5b-fd454944db40.png">

Model 1 produced five suitable regions that were well equally distributed around the city. Considering the variable weights, this model as expected primarily considered trees per capita when measuring preference.

<img width="684" alt="image" src="https://user-images.githubusercontent.com/81482638/166165753-a4f2216e-ac88-4b8c-b9d8-3b7cec3f5dac.png">

However, as seen from the region zoom-ins in Figure 1, the most suitable regions factor 
in other variables as well, such as neighborhoods that have been historically neglected by the city, such as the Hazelwood/Glen Hazel area and parts of the Hill District. It also produced high suitability scores for areas with higher land surface temperature (Shadyside) and areas with high amounts of poverty (Carrick/Knoxville). 

*Model 2 – Equity Criteria Weighted*

<img width="532" alt="image" src="https://user-images.githubusercontent.com/81482638/166165786-d11d1cd4-ad64-46b0-815c-67054b69f292.png">

Model 2 produces similar results to Model 1, with a few key differences. First, Region 1 includes more of the northwest parts of the city, such as Sheraden and Fairywood. Region 3 extends further into Oakland away from the Lawrenceville area. Region 4 shifts north and towards the river to include the Mt. Washington and Duquesne Heights neighborhoods. These shifts account for the increased weights on high-poverty areas and areas with high percentages of Black residents, populations which have been historically neglected by major cities. 

However, Model 2 still does not recommend regions that fully prioritize poverty and race as criteria (see figures below). For example, the neighborhoods of Homewood and parts of the North Shore are not identified as suitable regions. This demonstrates the effects of multiple criteria as inputs to the model. 

<img width="762" alt="image" src="https://user-images.githubusercontent.com/81482638/166165809-430e6424-0c3a-4f8a-a771-e47b4b962a8b.png">

<img width="764" alt="image" src="https://user-images.githubusercontent.com/81482638/166165822-fa9127cd-9276-4328-b8a6-4d95ec89ad14.png">

*Model 3 - Environment Criteria Weighted*

<img width="521" alt="image" src="https://user-images.githubusercontent.com/81482638/166165851-915bde88-cc1a-406d-9227-9c3fd756dfa5.png">

Model 3 shifts Region 5 to central Pittsburgh to account for the heavier weights on environmental factors, such as traffic and land surface temperatures. We can also see from the Trees Per Capita choropleth map that these areas have less concentrated tree coverage, which likely contributes to the higher LSTs. If interested in focusing on these factors, the City should consider exploring new planting sites in areas such as the Hill District, Oakland, East Liberty, and parts of Point Breeze.

*Model 4 - Vulnerability Criteria Weighted*

<img width="518" alt="image" src="https://user-images.githubusercontent.com/81482638/166165888-9821209f-c96a-4aed-b874-efcfd5c8c126.png">

The regions identified in Model 4 look nearly identical to Model 1, despite weighting criteria associated with vulnerable populations (e.g. elderly, children, children with asthma, smokers). This could show that these factors are highly correlated with the trees per capita metric, or that they do not display strong spatial correlation. 

Recommendations and Next Steps

The Planning Department has several options for next steps given these models. There are some regions each of these models have in common that I recommend the Planning Department seriously consider for new tree planting sites: 

1)	The Upper Hill/North Oakland
2)	Glen Hazel/Hazelwood/South Squirrel Hill/Greenfield
3)	The northwest side (Elliot, Crafton Heights, Sheraden)

Other neighborhoods for consideration depend on whether the City has primary and secondary goals for tree canopy cover. For example, if the City wants to focus on mitigating environmental factors such as traffic pollution and land surface temperatures, they should focus tree planting efforts in central Pittsburgh: the Hill District, Oakland, Lower Lawrenceville, East Liberty, Bloomfield, and Highland Park. 

Once the City has decided on general neighborhoods to focus on, the Planning Department should conduct further street-level studies to select exact sites, and study tree types to select species that maximize shade coverage at full maturity.



