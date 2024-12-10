# MAP673: Final Project Proposal
## Tentative title: US Presidential Elections 2004-2024

## Introduction
For my final project, I will map US presidential election results from 2004 to 2024 at the state level. The map will be fixated in the contiguous US but the user will be able to pan and zoom around to search for specific state results including Alaska, Hawaii, or the District of Columbia.

## 1. Data
Data for this project comes from two main sources:
* MIT Election Data and Science Lab, 2017, "U.S. President 1976–2020", https://doi.org/10.7910/DVN/42MVDX, Harvard Dataverse, V8; 1976-2020-president.tab [fileName], UNF:6:a2yzwWNbv+Eff8aqVmkZKA== [fileUNF] 

* Data 2024: Dave Leip's Atlas of U.S Presidential Elections (https://uselectionatlas.org/RESULTS/national.php)

Electoral data from 2004 to 2020 was collected from the MIT Election Data and Science Lab. This data was enriched with 2024 election data from Dave Leip's Atlas of U.S Presidential Elections. Data on the Electoral college seats won by each parte in each election for the 2004-2024 period were also collected from [Dave Leip's Atlas of U.S Presidential Elections](https://uselectionatlas.org/).

The data was aggregated and edited using Visual Studio Code to obtain a CSV that can be retrieved [here](https://github.com/newmapsplus/map673-mod-06-alexmunozviso/blob/master/digital_mockup/data/us_election2004_2024.csv).

The US polygon data was be downloaded from  [Natural Earth Data](https://www.naturalearthdata.com/). Then, using QGIS, it was converted to a GEOJSON and enriched with the election data through a table join. The final GEPJSON can be retrieved [here](https://github.com/newmapsplus/map673-mod-06-alexmunozviso/blob/master/digital_mockup/data/us_50m_states_election2004_2024.geojson).

## 2. Map style and representation
Electoral data will be represented coloring each state polygon with the color of the election winner for that given year. Party colors for the <span style="color:#00AEF3;font-weight:700">Democratic (HEX #00AEF3)</span> and the <span style="color:#E81B23;font-weight:700">Republican (HEX #E81B23)</span> parties were extracted from [flagcolorcodes](https://www.flagcolorcodes.com/). 

As per the overall layout style, I am the idea is to build a sober greyscale design, aiming at providing a 'presidential' look. The fonts used will also follow that design direction. [Halant](https://fonts.google.com/?query=halant) will be used for titles and [Nunito Sans](https://fonts.google.com/specimen/Nunito+Sans) for all other texts.

## 3. Interactive Capabilities and UI
The map will include different interactive elements with a simple design to highlight user accessibility and familiarity. Most interactive elements, such as the slider to navigate through years of data, will have a familiar design that the user can recognize, thus facilitating user experience and the map's functionality.

Regarding particular elements and the visuals of the UI, the map will contain:
1. The map and data occupying the whole screen.
2. A title box in the top/left corner of the screen.
3. An information button right below the title. If clicked, a pop/up text will appear at the center of the screen including a map description and map data information and links.
4. A year button in the top/right corner of the screen. When interactted with, the map will change to show the results of the selected year.
5. A legend showing election results for that particular year with the candidate's name and the party colors, situated to the left side of the map.
6. Hovering affordances. When the user hovers over a given state, the state boundary will change color to indicate selection and a tooltip will appear. The tooltip will contain information on the electoral college seats for the state and the popular vote for the two majority parties.

Visually, the final map will look similar to this approximation (see also a digital interactive mockup [here](https://github.com/newmapsplus/map673-mod-06-alexmunozviso/blob/master/index.html)):

![Map Mockup](https://github.com/newmapsplus/map673-mod-06-alexmunozviso/blob/master/graphics/digi_map_mockup.jpg "Map Mockup")

## 4. Map objectives
The purpose of the map is to offer an summary of election data that is accessible, simple to comprehend, and easy to visualize. When looking for election results, it is not easy to find a single place where all data is accessible in the simplest of ways, especially in the way it will be presented in this digital map.

Moreover, mapping election results is a contested topic among cartographers, as it is hard to have the right balance between how elections are won (e.g., Electoral College seats ) and what people vote for (i.e., popular vote). I think the data represented at the state level plus a tooltip with detailed information will help bridge this gap. Additionally, the slider option will allow the user to navigate data for different years in situ, icnreasing data accessibility.

## 5. Technology stack
The data sources and description, as well as the processing tools used for this project, are explained in detail in the second section of this page.

In the construction of the digital map, I will use Leaflet JS library to set all the map features and UI capabilities. Additionally, Google Fonts will be used through their CSS API too call the necessary font families, thus enriching the map's style. 

