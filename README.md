# US Presidential Elections 2004-2024

## Introduction
For my final project, I will map US presidential election results from 2004 to 2024 at the state level. The map will be fixated in the contiguous US but the user will be able to pan and zoom around to search for specific state results including Alaska, Hawaii, or the District of Columbia.

## 1. Data
Data for this project comes from two main sources:
* MIT Election Data and Science Lab, 2017, "U.S. President 1976–2020", https://doi.org/10.7910/DVN/42MVDX, Harvard Dataverse, V8; 1976-2020-president.tab [fileName], UNF:6:a2yzwWNbv+Eff8aqVmkZKA== [fileUNF] 

* Data 2024: Dave Leip's Atlas of U.S Presidential Elections (https://uselectionatlas.org/RESULTS/national.php)

Electoral data from 2004 to 2020 was collected from the MIT Election Data and Science Lab. This data was enriched with 2024 election data from Dave Leip's Atlas of U.S Presidential Elections. Data on the Electoral college seats won by each parte in each election for the 2004-2024 period were also collected from [Dave Leip's Atlas of U.S Presidential Elections](https://uselectionatlas.org/).

The data was aggregated and edited using Visual Studio Code to obtain a CSV that can be retrieved [here](https://github.com/alexmunozviso/Election-Map-2004-2024/blob/main/data/us_election2004_2024.csv).

The US polygon data was be downloaded from  [Natural Earth Data](https://www.naturalearthdata.com/). Then, using QGIS, it was converted to a GEOJSON and enriched with the election data through a table join. The final GEPJSON can be retrieved [here](https://github.com/alexmunozviso/Election-Map-2004-2024/blob/main/data/us_50m_states_election2004_2024.geojson).  

_Note: The data included in this project relates only to the two majority parties (i.e., Demcoratic and Republican parties), as third party vote in the US is statistically insignificant and results in no actual institutional representation, which is the focus of this map. Additionally, adding the data on all third parties reduced the map's readability and played against the overall simplicity of its design._

## 2. Map style and representation
Electoral data is represented coloring each state polygon with the color of the election winner for that given year. Party colors for the <span style="color:#00AEF3;font-weight:700">Democratic (HEX #00AEF3)</span> and the <span style="color:#E81B23;font-weight:700">Republican (HEX #E81B23)</span> parties were extracted from [flagcolorcodes](https://www.flagcolorcodes.com/). 

As per the overall layout style, I designed a simple and sober greyscale design, aiming at providing a 'presidential' look. In line with this, [Halant](https://fonts.google.com/?query=halant) is the font used for titles and [Nunito Sans](https://fonts.google.com/specimen/Nunito+Sans) for all other texts.

## 3. Interactive Capabilities and UI
The map includes different interactive elements with a simple design to highlight user accessibility and familiarity. Most interactive elements, such as the slider to navigate through years of data, have a familiar design that the user can recognize, thus facilitating user experience and the map's functionality.

Regarding particular elements and the visuals of the UI, the map contains:
1. The map and data occupying the whole screen.
2. A title box in the top/left corner of the screen.
3. An information button to the right of the title. If clicked, a pop/up text appears including a map description and information on the data sources (including links).
4. A year slider at the top/left corner of the screen. When users interact with the slider, the map updates showing the election results for the selected year.
5. A legend showing election results for that particular year with the party color's, the candidate's name and last name, and the number of electoral seats won (thus showing the election winner).
6. Hovering affordances. When the user hovers over a given state, the state boundary is highlighted by changing colors. Automatically, a tooltip appears providing the following information:
   * State name.
   * Electoral college seats for each party in the given state.
   * Popular vote for each party in the given state.

## 4. Map objectives
The purpose of the map is to offer an summary of election data that is accessible, simple to comprehend, and easy to visualize. When looking for election results, it is not easy to find a single place where all data is accessible in the simplest of ways, especially in the way it will be presented in this digital map.

Moreover, mapping election results is a contested topic among cartographers, as it is hard to have the right balance between how elections are won (e.g., Electoral College seats ) and what people vote for (i.e., popular vote). I think the data represented at the state level plus a tooltip with detailed information will help bridge this gap. Additionally, the slider option will allow the user to navigate data for different years in situ, icnreasing data accessibility.

## 5. Technology stack
The data sources and description, as well as the processing tools used for this project, are explained in detail in the second section of this page.

In the construction of the digital map, I used Leaflet JS library to set all the map features and UI capabilities. Additionally, I used Google Fonts through their CSS API too call the necessary font families, thus enriching the map's style. 

## 6. Project updates
I doubted between using a slider or a drop/down button to navigate between the election maps and data. To solve this, I made two versions of the map as static mockups (one with a slider and one with a button) and showed them to three friends, treating them as 'testing users'. The three of them said to prefer the slider version. Overall, they said it was easier to identify as an interactive element and that it was better at visualizing change in 'swing' states. Interestingly, one of them mentioned that the slider added a certain "playfulness" to the map's interaction that they enjoyed.

The two static mockup versions of the map showed to the testers can be retrieved [here](https://github.com/alexmunozviso/Election-Map-2004-2024/blob/main/graphics/mockup-button.jpg) and [here](https://github.com/alexmunozviso/Election-Map-2004-2024/blob/main/graphics/mockup-slider.jpg).




