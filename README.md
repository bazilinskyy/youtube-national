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

[![Locations of cities with footage in dataset](figures/map.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map.html)
The 133 countries with dashcam footage included in analysis on the political map (coloured by continent). Black dots show the cities included.

<!-- [![Mean time to start crossing and Mean speed of crossing (in m/s, sorted by countries)](figures/consolidated.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/consolidated.html)
Mean time to start crossing and Mean speed of crossing (in m/s, sorted by countries). -->

[![Total time of footage over number of detected pedestrians](figures/scatter_total_time-person.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_total_time-person.html)
Total time of footage over number of detected pedestrians.

### Time to start crossing
[![Mean time to start crossing (in s, sorted by countries](figures/time_crossing_alphabetical.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_alphabetical.html)
Mean time to start crossing (in s, sorted by countries).

[![Mean time to start crossing (in s, sorted by average of day and night)](figures/time_crossing_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg.html)
Mean time to start crossing (in s, sorted by average of day and night).

[![ Map with mean time to start crossing (in s, sorted by average of day and night)](figures/map_time_crossing_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map_time_crossing_avg.html)
Map with heatmap based on time to start crossing (in s, sorted by average of day and night).

[![Mean time to start crossing (in s, sorted by average of day)](figures/time_crossing_avg_day.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg_day.html)
Mean time to start crossing during daytime (in s).

[![Mean time to start crossing (in s, sorted by average of night)](figures/time_crossing_avg_night.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg_night.html)
Mean time to start crossing during night time (in s).

### Speed of crossing
[![Mean speed of crossing (in m/s, sorted by countries](figures/crossing_speed_alphabetical.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_alphabetical.html)
Mean speed of crossing (in m/s, sorted by countries).

[![Mean speed of crossing (in m/s, sorted by average of day and night)](figures/crossing_speed_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_avg.html)
Mean speed of crossing (in m/s, sorted by average of day and night).

[![ Map with mean speed of crossing (in m/s, sorted by average of day and night)](figures/map_speed_crossing_avg.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map_speed_crossing_avg.html)
Map with heatmap based on mean speed of crossing (in m/s, sorted by average of day and night).

[![Mean speed of crossing (in m/s, sorted by average of day)](figures/crossing_speed_avg_day.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_avg_day.html)
Mean speed of crossing during daytime (in m/s).

[![Mean speed of crossing (in m/s, sorted by average of night)](figures/crossing_speed_avg_night.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_avg_night.html)
Mean speed of crossing during night time (in m/s).

### Relationship between computed and statistical metrics
[![Speed of crossing over crossing decision time](figures/scatter_speed_crossing_avg-time_crossing.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-time_crossing.html)
Mean speed of crossing (in m/s) over Mean time to start crossing (in s) (in s).

[![Speed of crossing over Mean time to start crossing daytime](figures/scatter_speed_crossing_avg_day-time_crossing_day.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg_day-time_crossing_day.html)
Mean speed of crossing (in m/s) over Mean time to start crossing (in s), during daytime.

[![Speed of crossing over Mean time to start crossing night time](figures/scatter_speed_crossing_avg_night-time_crossing_night.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg_night-time_crossing_night.html)
Mean speed of crossing (in m/s) over Mean time to start crossing (in s), during night time.

[![Speed of crossing over population of country](figures/scatter_speed_crossing_avg-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-population_country.html)
Mean speed of crossing over population of country.

[![Mean time to start crossing over population of country](figures/scatter_time_crossing_avg-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-population_country.html)
Mean time to start crossing over population of country.

[![Speed of crossing over traffic mortality](figures/scatter_speed_crossing_avg-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-traffic_mortality.html)
Mean speed of crossing over traffic mortality.

[![Mean time to start crossing over traffic mortality](figures/scatter_time_crossing_avg-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-traffic_mortality.html)
Mean time to start crossing over traffic mortality.

[![Speed of crossing over literacy rate](figures/scatter_speed_crossing_avg-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-literacy_rate.html)
Mean speed of crossing over literacy rate.

[![Mean time to start crossing over literacy rate](figures/scatter_time_crossing_avg-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-literacy_rate.html)
Mean time to start crossing over literacy rate.

[![Speed of crossing over Gini coefficient](figures/scatter_speed_crossing_avg-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-gini.html)
Mean speed of crossing over Gini coefficient.

[![Mean time to start crossing over Gini coefficient](figures/scatter_time_crossing_avg-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-gini.html)
Mean time to start crossing over Gini coefficient.

[![Speed of crossing over traffic index](figures/scatter_speed_crossing_avg-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_avg-traffic_index.html)
Mean speed of crossing over traffic index.

[![Mean time to start crossing over traffic index](figures/scatter_time_crossing_avg-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-traffic_index.html)
Mean time to start crossing over traffic index.

[![Mean time to start crossing over traffic index](figures/scatter_time_crossing_avg-traffic_index.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_avg-traffic_index.html)
Mean time to start crossing over traffic index.

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
