## Overview

Pedestrian crossing behaviour varies globally. This study analyses dashcam footage from the CROWD dataset, covering 233 countries and territories, to examine crossing initiation time, crossing speed, and contextual variables, including detected vehicles, traffic mortality, GDP, and Gini coefficient. Qatar had the longest mean crossing initiation time (6.44s), while China exhibited the fastest crossing speed (1.69m/s). On average, worldwide, pedestrians exhibited a crossing initiation time of 3.18s and crossing speed 1.20m/s. Crossing speed and crossing initiation time are negatively correlated (r = -0.18), indicating slower crossings after longer hesitation. Crossing speed is negatively correlated with Gini coefficient (r = -0.19) and positively correlated with traffic mortality (r = 0.18). Similar crossing times in countries with different infrastructures, such as Bangladesh (3.42s) and the Netherlands (3.40s), underscore the complex interaction between infrastructure and behavioural adaptation. These findings emphasise the importance of culturally aware road design and the development of adaptive interfaces for vehicles.

## Usage of the code
The code is open-source and free to use. It is aimed for, but not limited to, academic research. We welcome forking of this repository, pull requests, and any contributions in the spirit of open science and open-source code 😍😄 For inquiries about collaboration, you may contact Md Shadab Alam (md_shadab_alam@outlook.com) or Pavlo Bazilinskyy (pavlo.bazilinskyy@gmail.com).

## Citation
If you use the gans-traffic for academic work please cite the following paper:

> Alam, M. S., Martens, M.H., & Bazilinskyy, P. (2025). Pedestrian Planet: What YouTube Driving from 231 Countries and Territories Teaches Us About the World. 17th International Conference on Automotive User Interfaces and Interactive Vehicular Applications. Brisbane, QLD, Australia. https://doi.org/10.1145/3744333.3747827

## Getting Started
[![Python Version](https://img.shields.io/badge/python-3.9.19-blue.svg)](https://www.python.org/downloads/release/python-3919/)
[![Package Manager: uv](https://img.shields.io/badge/package%20manager-uv-green)](https://docs.astral.sh/uv/)

Tested with **Python 3.9.19** and the [`uv`](https://docs.astral.sh/uv/) package manager.  
Follow these steps to set up the project.

**Step 1:**

Install `uv`.

`uv` is a fast Python package and environment manager. Install it using one of the following methods:

**macOS / Linux (bash/zsh):**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**
```powershell
irm https://astral.sh/uv/install.ps1 | iex
```

**Alternative (if you already have Python and pip):**
```bash
pip install uv
```

**Step 2:**

After installing, verify:
```bash
uv --version
```

**Step 3:**

Clone the repository
```command line
git clone https://github.com/bazilinskyy/youtube-national
cd youtube-national
```

**Step 4:**

Ensure correct Python version. If you don’t already have Python 3.9.19 installed, let uv fetch it:
```command line
uv python install 3.9.19
```
The repo should contain a .python-version file so uv will automatically use this version.

**Step 5:**

Create and sync the virtual environment. This will create **.venv** in the project folder and install dependencies exactly as locked in **uv.lock**:
```command line
uv sync --frozen
```

**Step 6:**

Activate the virtual environment
```command line
pip install -r requirements.txt
```
**macOS / Linux (bash/zsh):**
```bash
source .venv/bin/activate
```

**Windows (PowerShell):**
```powershell
.\.venv\Scripts\Activate.ps1
```

**Windows (cmd.exe):**
```bat
.\.venv\Scripts\activate.bat
```

**Step 7:**

Ensire that dataset are present. Place required datasets (including **mapping.csv**) into the **data/** directory.


**Step 8:**

Run the code:
```command line
python3 analysis.py
```

### Configuration of project
Configuration of the project needs to be defined in `config`. Please use the `default.config` file for the required structure of the file. If no custom config file is provided, `default.config` is used. The config file has the following parameters:
- **`data`**: Directory containing data (CSV output from YOLO).
- **`videos`**: Directories containing the videos used to generate the data.
- **`mapping`**: CSV file that contains mapping data for the cities referenced in the data.
- **`prediction_mode`**: Configures YOLO for object detection.
- **`tracking_mode`**: Configures YOLO for object tracking.
- **`always_analyse`**: Always conduct analysis even when pickle files are present (good for testing).
- **`display_frame_tracking`**: Displays the frame tracking during analysis.
- **`save_annotated_img`**: Saves the annotated frames produced by YOLO.
- **`delete_labels`**: Deletes label files from YOLO output.
- **`delete_frames`**: Deletes frames from YOLO output.
- **`delete_youtube_video`**: Deletes saved YouTube videos.
- **`compress_youtube_video`**: Compresses YouTube videos (using the H.255 codec by default).
- **`delete_runs_files`**: Deletes files containing YOLO output after analysis.
- **`monitor_temp`**: Monitors the temperature of the device running the analysis.
- **`check_missing_mapping`**: Identifies all the missing csv files.
- **`client`**: Specifies the client type for downloading YouTube videos; accepted values are `"WEB"`, `"ANDROID"` or `"ios"`.
- **`model`**: Specifies the YOLO model to use; supported/tested versions include `v8x` and `v11x`.
- **`countries_analyse`**: Lists the countries to be analysed.
- **`confidence`**: Sets the confidence threshold parameter for YOLO.
- **`update_ISO_code`**: Updates the ISO code of the country in the mapping file during analysis.
- **`update_pop_country`**: Updates the country’s population in the mapping file during analysis.
- **`update_continent`**: Updates the continent information in the mapping file during analysis.
- **`update_mortality_rate`**: Updates the mortality rate of the country in the mapping file during analysis.
- **`update_gini_value`**: Updates the GINI value of the country in the mapping file during analysis.
- **`update_upload_date`**: Updates the upload date of videos in the mapping file during analysis.
- **`update_fps_list`**: Updates the FPS (frames per second) information for videos in the mapping file during analysis.
- **`update_pytubefix`**: Updates the `pytubefix` library each time analysis starts.
- **`font_family`**: Specifies the font family to be used in outputs.
- **`font_size`**: Specifies the font size to be used in outputs.
- **`plotly_template`**: Defines the template for Plotly figures.
- **`logger_level`**: Level of console output. Can be: debug, info, warning, error.
- **`sleep_sec`**: Amount of seconds of pause between going over the mapping files.

## Description and analysis of dataset
[![Locations of cities with footage in dataset](figures/map_screenshots_total_time.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map_screenshots_total_time.html)
A political world map colored by continent, showing **233 countries** included in the analysis. The shading represents the total duration of dashcam footage from each country, adjusted with a logarithmic scale so that countries with very large or very small totals are both visible. Black dots indicate the cities from which footage was collected.

[![Histogram of pedestrian crossing speeds](figures/hist_speed.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/hist_speed.html)  
Histogram of pedestrian crossing speeds (in m/s), computed **per individual pedestrian** and pooled across all locations/countries (i.e., not aggregated by city or country).

[![Histogram of pedestrian crossing initiation time](figures/hist_time.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/hist_time.html)  
Histogram of pedestrian crossing initiation time (in s), computed **per individual pedestrian** and pooled across all locations/countries (i.e., not aggregated by city or country).


### Dataset after filtering
The dataset undergoes a filtering process to ensure quality and sufficient coverage before being used in analysis. The following thresholds are applied:

- **`footage_threshold`: `1800`**  
  A city is included **only** if it has more than **1800 seconds** (30 minutes) of recorded footage.  
  This ensures each city has a substantial amount of data for reliable insights.

- **`min_crossing_detect`: `100`**  
  A country is included **only** if at least **100 pedestrian crossings** are detected within its boundaries.  
  This ensures that pedestrian-related statistics are meaningful at the country level.

[![Histogram of pedestrian crossing speeds](figures/hist_speed_filtered.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/hist_speed_filtered.html)  
Histogram of pedestrian crossing speeds (in m/s), computed **per individual pedestrian** and pooled across all locations/countries (i.e., not aggregated by city or country).

[![Histogram of pedestrian crossing initiation time](figures/hist_time_filtered.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/hist_time_filtered.html)  
Histogram of pedestrian crossing initiation time (in s), computed **per individual pedestrian** and pooled across all locations/countries (i.e., not aggregated by city or country).

[![Location of the cities included in the dataset after filtering](figures/mapbox_map.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/mapbox_map.html)

[![Total time of footage after filtering](figures/mapbox_map_time.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/mapbox_map_time.html)

### Time to start crossing
[![Map with mean time to start crossing (in s)](figures/map_crossing_time.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map_crossing_time.html)
Map with heatmap based on mean time to start crossing (in s).

[![Mean time to start crossing (in s, sorted by average of day and night)](figures/time_crossing_avg_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg_country.html)
Mean time to start crossing (in s, sorted by average of day and night).

[![Mean time to start crossing (in s, sorted by average of day)](figures/time_crossing_combined_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_combined_country.html)
Mean time to start crossing (in s, sorted by day).

[![Mean time to start crossing at day (in s, sorted alphabetically)](figures/time_crossing_alphabetical_day_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_alphabetical_day_country.html)  
Mean time to start crossing at day (in s, sorted by values)

[![Mean time to start crossing at night (in s, sorted alphabetically)](figures/time_crossing_avg_night_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/time_crossing_avg_night_country.html)  
Mean time to start crossing at night (in s, sorted by values)

### Speed of crossing
[![Map with mean speed of crossing (in m/s)](figures/map_speed_crossing.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/map_speed_crossing.html)
Map with heatmap based on mean speed of crossing (in m/s).

[![Mean speed of crossing (in m/s, sorted by average of day and night)](figures/crossing_speed_avg_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_avg_country.html)
Mean speed of crossing (in m/s, sorted by average of day and night).

[![Mean speed of crossing (in m/s, sorted by average of day)](figures/crossing_speed_combined_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_combined_country.html)
Mean speed of crossing (in m/s, sorted by day).

[![Mean speed of crossing at day (in s, sorted alphabetically)](figures/crossing_speed_alphabetical_day_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_alphabetical_day_country.html)  
Mean speed of crossing at day (in m/s, sorted by values)

[![Mean speed of crossing at night (in s, sorted alphabetically)](figures/crossing_speed_alphabetical_night_country.png?raw=true)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/crossing_speed_alphabetical_night_country.html)  
Mean speed of crossing at night (in m/s, sorted by values)



### Relationship between computed and statistical metrics
[![Mean speed of crossing during daytime over mean time to start crossing](figures/scatter_speed_crossing_day_country-time_crossing_day_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_country-time_crossing_day_country.html)  
Mean speed of crossing (in m/s) during daytime over mean time to start crossing (in s).

[![Mean speed of crossing vs. proportion of pedestrians detected using a cellphone](figures/scatter_speed_crossing_day_night_country_avg-cellphone_normalised.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-cellphone_normalised.html)  
Mean speed of crossing (in m/s) versus the proportion of pedestrians detected using a cellphone.

[![Mean speed of crossing over Gini index](figures/scatter_speed_crossing_day_night_country_avg-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-gini.html)  
Mean speed of crossing (in m/s) over Gini index (income inequality).

[![Mean speed of crossing over literacy rate](figures/scatter_speed_crossing_day_night_country_avg-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-literacy_rate.html)  
Mean speed of crossing (in m/s) over literacy rate (% of population).

[![Mean speed of crossing over median age](figures/scatter_speed_crossing_day_night_country_avg-med_age.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-med_age.html)  
Mean speed of crossing (in m/s) over median age of the population.

[![Mean speed of crossing over population](figures/scatter_speed_crossing_day_night_country_avg-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-population_country.html)  
Mean speed of crossing (in m/s) over total population of the country.

[![Mean speed of crossing over mean time to start crossing](figures/scatter_speed_crossing_day_night_country_avg-time_crossing_day_night_country_avg.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-time_crossing_day_night_country_avg.html)  
Mean speed of crossing (in m/s) over mean time to start crossing (in s).

[![Mean speed of crossing over traffic mortality rate](figures/scatter_speed_crossing_day_night_country_avg-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_day_night_country_avg-traffic_mortality.html)  
Mean speed of crossing (in m/s) over traffic-related mortality (per 100,000 people).

[![Mean speed of crossing at night over mean time to start crossing](figures/scatter_speed_crossing_night_country-time_crossing_night_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_speed_crossing_night_country-time_crossing_night_country.html)  
Mean speed of crossing (in m/s) at night over mean time to start crossing (in s).

[![Mean time to start crossing vs. proportion of pedestrians detected using a cellphone](figures/scatter_time_crossing_day_night_country_avg-cellphone_normalised.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-cellphone_normalised.html)  
Mean time to start crossing (in s) versus the proportion of pedestrians detected using a cellphone.

[![Mean time to start crossing over Gini index](figures/scatter_time_crossing_day_night_country_avg-gini.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-gini.html)  
Mean time to start crossing (in s) over Gini index (income inequality).

[![Mean time to start crossing over literacy rate](figures/scatter_time_crossing_day_night_country_avg-literacy_rate.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-literacy_rate.html)  
Mean time to start crossing (in s) over literacy rate (% of population).

[![Mean time to start crossing over median age](figures/scatter_time_crossing_day_night_country_avg-med_age.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-med_age.html)  
Mean time to start crossing (in s) over median age of the population.

[![Mean time to start crossing over population](figures/scatter_time_crossing_day_night_country_avg-population_country.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-population_country.html)  
Mean time to start crossing (in s) over total population of the country.

[![Mean time to start crossing over traffic mortality rate](figures/scatter_time_crossing_day_night_country_avg-traffic_mortality.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_time_crossing_day_night_country_avg-traffic_mortality.html)  
Mean time to start crossing (in s) over traffic-related mortality (per 100,000 people).

[![Total footage time over bicycle count (normalised)](figures/scatter_total_time-bicycle_norm.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_total_time-bicycle_norm.html)  
Total footage time (in s) over number of bicycles (normalised per detected persons).

[![Total footage time over pedestrian count (normalised)](figures/scatter_total_time-person_norm.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_total_time-person_norm.html)  
Total footage time (in s) over number of pedestrians (normalised per detected pedestrian).

[![Total footage time over pedestrian count](figures/scatter_total_time-person.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_total_time-person.html)  
Total footage time (in s) over total number of pedestrians.

[![Footage with traffic light over footage without traffic light (normalised)](figures/scatter_with_trf_light_norm-without_trf_light_norm.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_with_trf_light_norm-without_trf_light_norm.html)  
Footage with traffic lights over footage without traffic lights, both normalised per population.


### Correlation matrices
[![Correlation matrix based on average speed and time to start cross](figures/correlation_matrix_heatmap_averaged.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/correlation_matrix_heatmap_averaged.html)
Correlation matrix of average values of day and night.

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

### Analysis of pedestrian crossing road without traffic lights (jaywalking)

[![Road crossings with and without traffic signals](figures/scatter_with_trf_light_norm-without_trf_light_norm.png)](https://htmlpreview.github.io/?https://github.com/bazilinskyy/youtube-national/blob/main/figures/scatter_with_trf_light_norm-without_trf_light_norm.html)
Road crossings with and without traffic signals (normalised over time and number of detected pedestrians).

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contact
If you have any questions or suggestions, feel free to reach out to md_shadab_alam@outlook.com.
