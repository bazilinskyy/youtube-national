# youtube-country

## Overview

## Usage of the code
The code is open-source and free to use. It is aimed for, but not limited to, academic research. We welcome forking of this repository, pull requests, and any contributions in the spirit of open science and open-source code 😍😄 For inquiries about collaboration, you may contact Md Shadab Alam (md_shadab_alam@outlook.com) or Pavlo Bazilinskyy (pavlo.bazilinskyy@gmail.com).

## Getting Started
Tested with Python 3.9.19. To setup the environment run these two commands in a parent folder of the downloaded repository (replace `/` with `\` and possibly add `--user` if on Windows:

**Step 1:**

Clone the repository
```command line
git clone https://github.com/bazilinskyy/youtube-dashcam
```

**Step 2:**

Create a new virtual environment
```command line
python -m venv venv
```

**Step 3:**

Activate the virtual environment
```command line
source venv/bin/activate
```

On Windows use
```command line
venv\Scripts\activate
```

**Step 4:**

Install dependencies
```command line
pip install -r requirements.txt
```

**Step 5:**

Ensure you have the required datasets in the data/ directory, including the mapping.csv file.

**Step 6:**

Run the code:
```command line
python3 analysis.py
```

## Description and analysis of dataset
### Description of dataset
<!-- [![Locations of cities with footage in dataset](figures/world_map.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/world_map.html)
Locations of cities with footage in dataset. -->

[![Locations of cities with footage in dataset](figures/mapbox_map.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/mapbox_map.html)
Locations of cities with footage in dataset. *Note:* continents are based on geography, i.e., the cities in Russia east from Ural mountains are shown as Asia.

<!-- [![Crossing decision time and crossing speed (sorted by countries)](figures/consolidated.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/consolidated.html)
Crossing decision time and crossing speed (sorted by countries). -->

[![Total time of footage over number of detected pedestrians](figures/scatter_total_time-person.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_total_time-person.html)
Total time of footage over number of detected pedestrians.

### Global behaviour of pedestrians
[![Crossing decision time (sorted by countries](figures/time_crossing_alphabetical.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_alphabetical.html)
Crossing decision time (sorted by countries).

[![Crossing speed (sorted by countries](figures/crossing_speed_alphabetical.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_alphabetical.html)
Crossing speed (sorted by countries).

[![Crossing decision time (sorted by average of day and night)](figures/time_crossing_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg.html)
Crossing decision time (sorted by average of day and night).

[![Crossing speed (sorted by average of day and night)](figures/crossing_speed_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_avg.html)
Crossing speed (sorted by average of day and night).

### Relationship between computed and statistical metrics
[![Speed of crossing over crossing decision time](figures/scatter_speed_crossing-time_crossing.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-time_crossing.html)
Crossing speed over crossing decision time.

[![Speed of crossing over crossing decision time daytime](figures/scatter_speed_crossing_day-time_crossing_day.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day-time_crossing_day.html)
Crossing speed over crossing decision time, during daytime.

[![Speed of crossing over crossing decision time night time](figures/scatter_speed_crossing_night-time_crossing_night.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_night-time_crossing_night.html)
Crossing speed over crossing decision time, during night time.

[![Speed of crossing over population of country](figures/scatter_speed_crossing-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-population_country.html)
Crossing speed over population of country.

[![Crossing decision time over population of country](figures/scatter_time_crossing-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-population_country.html)
Crossing decision time over population of country.

[![Speed of crossing over traffic mortality](figures/scatter_speed_crossing-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-traffic_mortality.html)
Crossing speed over traffic mortality.

[![Crossing decision time over traffic mortality](figures/scatter_time_crossing-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-traffic_mortality.html)
Crossing decision time over traffic mortality.

[![Speed of crossing over literacy rate](figures/scatter_speed_crossing-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-literacy_rate.html)
Crossing speed over literacy rate.

[![Crossing decision time over literacy rate](figures/scatter_time_crossing-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-literacy_rate.html)
Crossing decision time over literacy rate.

[![Speed of crossing over Gini coefficient](figures/scatter_speed_crossing-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-gini.html)
Crossing speed over Gini coefficient.

[![Crossing decision time over Gini coefficient](figures/scatter_time_crossing-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-gini.html)
Crossing decision time over Gini coefficient.

[![Speed of crossing over traffic index](figures/scatter_speed_crossing-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing-traffic_index.html)
Crossing speed over traffic index.

[![Crossing decision time over traffic index](figures/scatter_time_crossing-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-traffic_index.html)
Crossing decision time over traffic index.

[![Crossing decision time over traffic index](figures/scatter_time_crossing-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing-traffic_index.html)
Crossing decision time over traffic index.

### Correlation matrices
[![Correlation matrix based on average speed and time to start cross](figures/correlation_matrix_heatmap_averaged.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_averaged.html)
Correlation matrix.

[![Correlation matrix at daytime](figures/correlation_matrix_heatmap_day.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_day.html)
Correlation matrix at daytime.

[![Correlation matrix at night time](figures/correlation_matrix_heatmap_night.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_night.html)
Correlation matrix at night time.

[![Correlation matrix for Africa](figures/correlation_matrix_heatmap_Africa.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_Africa.html)
Correlation matrix for Africa.

[![Correlation matrix for Asia](figures/correlation_matrix_heatmap_Asia.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_Asia.html)
Correlation matrix for Asia.

[![Correlation matrix for Oceania](figures/correlation_matrix_heatmap_Oceania.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_Oceania.html)
Correlation matrix for Oceania.

[![Correlation matrix for Europe](figures/correlation_matrix_heatmap_Europe.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_Europe.html)
Correlation matrix for Europe.

[![Correlation matrix for North America](figures/correlation_matrix_heatmap_North%20America.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_North%20America.html)
Correlation matrix for North America.

[![Correlation matrix for South America](figures/correlation_matrix_heatmap_South%20America.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_South%20America.html)
Correlation matrix for South America.

### Analysis of pedestrian crossing road with and without traffic lights (jaywalking)
[![Road crossings with traffic signals](figures/crossings_with_traffic_equipment_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossings_with_traffic_equipment_avg.html)
Road crossings with traffic signals (normalised over time and number of detected pedestrians).

[![Road crossings without traffic signals](figures/crossings_without_traffic_equipment_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossings_without_traffic_equipment_avg.html)
Road crossings without traffic signals (normalised over time and number of detected pedestrians).

[![Road crossings with and without traffic signals](figures/scatter_with_trf_light_norm-without_trf_light_norm.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_with_trf_light_norm-without_trf_light_norm.html)
Road crossings with and without traffic signals (normalised over time and number of detected pedestrians).


## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contact
If you have any questions or suggestions, feel free to reach out to md_shadab_alam@outlook.com
