# Kerala-Trend-Detective

NASA Space Apps Challenge 2026 | Challenge: Be An Earth System Trend Detective!

Team: Kerala Statistics | Members: Faizan , Gaurang , Ephraim , Megha , Razal | Local Event: Calicut

A tool that lets anyone pick an Earth-science variable, a season and a Kerala district, then answers: what is changing?, where?, how much?, and whether the change is statistically significant?.

Live dashboard: https://faizanshiroj.github.io/kerala-trend-detective/ |Slide Deck: https://github.com/faizanshiroj/kerala-trend-detective/blob/main/NASA%20Space%20Apps%20Challenge%202026.pdf | Code and data: https://github.com/faizanshiroj/kerala-trend-detective | Notebook: kerala_trend_detective.ipynb

## What we found (1991-2025)
- Temperature is rising almost everywhere. 13 of 14 districts show a significant annual increase (about 0.5 to 0.9 °C over 35 years). In the monsoon and post-monsoon seasons, all 14 districts show a significant increase.
- Monsoon (Jun-Sep) rainfall shows no significant trend in any district.
- Pre-monsoon (Mar-May) rainfall is increasing significantly in 12 districts.

## How it works
1. Data:monthly values from the NASA POWER API (built from NASA satellite and model products such as MERRA-2 and GPM IMERG) for the 14 Kerala districts: rainfall (PRECTOTCORR), 2 m air temperature (T2M), root-zone soil wetness (GWETROOT), surface soil wetness (GWETTOP) and relative humidity (RH2M).
2. Analysis: each variable is averaged per season per year, then tested with the Mann-Kendall trend test (significant if p < 0.05). Sen's slope gives the size of the change per year.
3. Outputs: an interactive notebook, a results file, and a web dashboard with a district map, trend charts and a comparison table.

## Files
| `kerala_trend_detective.ipynb` | Google Colab notebook: downloads data, runs the tests, interactive tool, exports results |
| `kerala_trends.json`, `kerala_trends.csv` | Results for 14 districts x 5 variables x 5 seasons (produced by running the notebook code) |
| `index.html` | Web dashboard (data embedded).

## Running the code
Open the notebook in [Google Colab](https://colab.research.google.com)[no login required}, choose Runtime > Run all, then use the dropdowns in the last section.

## Use of AI (Super Intelligence) disclosure
The code for kerala_trend_detective.ipynb was built with the assistance of Claude,and debugging certain areas of code was with the assistance of claude and chatgpt. The result obtained from colab(The .json and .csv file) was annalyzed and summarized by claude to use as data for the dashboard. The way to make a dashboard and help for building it was taken from claude and chatgpt. Points and important topics were summarized and shortened by claude for the ppt slide deck. 


## NASA data
NASA POWER (Prediction Of Worldwide Energy Resources), NASA Langley Research Center, monthly point data for 1991-2025, accessed through the POWER API. Its values are derived from NASA satellite and model products (MERRA-2, GPM IMERG).

## Other resources and tools
Python, Google Colab, GitHub and GitHub Pages; Python libraries: requests, numpy, pandas, matplotlib, pymannkendall, ipywidgets. Default icons in ppt for the slide. No third-party images are used. (Claude and Chatgpt were used for research ,debugging,analyzing and summarizing as stated above)

## Limitations
- NASA POWER is a coarse grid (about 50 km), so neighbouring districts have similar values.
- We ran 350 tests, so roughly 5% of "significant" results could be false alarms by chance. Look for patterns across districts rather than single results.
- 35 years is a short record for climate trends, and a significant trend does not by itself show the cause.
-Results exported on 14 November 2026; small differences may appear if NASA POWER updates its data.
