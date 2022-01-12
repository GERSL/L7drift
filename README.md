# Landsat 7's Orbit Drift
Since 2017, the orbit of Landsat 7 has drifted outside its nominal mission requirement toward an earlier acquisition time because of limited onboard fuel resources (Figure 1). The real-time acquisition times for Landsat 5, 7 and 8 (and Sentinel-2A & -2B) can be found at [this Google Earth Engine script](https://colab.research.google.com/gist/tylere/6069908f90fbba4ceaa4767b19b0bdf3/satellite-platform-acquisition-time-comparison.ipynb#scrollTo=X7dhgCuYtOG1) (Thanks, 
[Tyler Erickson](https://twitter.com/tylerickson)). To comprehensively understand the effect of ongoing (2018-2021) orbit drift on Landsat 7 data, we compared surface reflectance and Top-Of-Atmosphere (TOA) reflectance of growing season observations (July 1 ± 30 days) from Landsat 7 with orbit drift and Landsat 8 with nominal orbit using a total of 10,000 randomly selected Northern Hemisphere (0 - 75N) terrestrial pixels. According to the results (see below for details), **we recommended that Landsat 7 can preserve its science capability until 2020, but will be less reliable for remote sensing applications that need accurate absolute radiometric values after 2020. Correction methods such as c-factor BRDF could be a potential viable approach to maintain its science capability going forward.**  

Landsat 7’s orbit drift has already led to a general decrease in surface reflectance and TOA reflectance in 2019, 2020, and 2021, with a limited impact before 2020 (overall reflectance changes less than 0.007), but **much more dramatic in 2021 (0.012 in SWIR1 band and 0.009 in NIR and SWIR2 bands)**. The influence of orbit drift is more substantial for the two shortwave infrared (SWIR) bands and the near infrared (NIR) band, but less for the three visible bands (i.e., Red, Green, and Blue). The Normalized Difference Vegetation Index (NDVI), derived from either surface reflectance or TOA reflectance, increased less than 0.003 till 2021 (Figure 2).

To reduce this influence, we examined the c-factor Bidirectional Reflectance Distribution Function (BRDF) normalization approach to correct the orbit drift impact for Landsat 7 surface reflectance data collected between 2019 and 2021. We found that the c-factor BRDF can reduce the data difference substantially, but how this approach works after Landsat 7’s orbit drifts further still requires more investigation (Figure 2). 



<img src="https://github.com/GERSL/L7Drift/blob/main/orbit_time_2021.png"/>
Figure 1. Local acquisition time (left y-axis) and solar angles (right y-axis) of EO-1, Landsat 7, and Landsat 8 for images collected at Worldwide Reference System Two (WRS-2) Path 177/ Row 45 (Center Latitude/Longitude: 21.6742/ 28.2286). EO-1’s orbit started to drift in February 2011 and ended in March 2017 (grey area). Landsat 7’s orbit started to drift in August 2017 (red area). The mean local acquisition time (without orbit drift) of EO-1, Landsat 7, and Landsat 8 is 10:21 a.m., 10:26 a.m., and 10:32 a.m., respectively. The solar azimuth/zenith angles are derived from the satellite observations in the growing season of each calendar year (the closest acquisition date to July 1). Observations from Landsat 7 and 8 acquired in the growing season of 2018, 2019, and 2020 are compared for quantifying the effect of ongoing Landsat 7’s orbit drift, and observations between EO-1 and Landsat 7 from 2010 to 2016 are used for estimating the effect of future Landsat 7’s orbit drift. The orbit status of EO-1 in 2012 and 2013 are similar to that of Landsat 7 in 2019 and 2020, and the future Landsat 7 orbit between 2022 and 2023 can be inferred from EO-1 orbit between 2015 and 2016. This Path/Row is selected as it contains a large number of EO-1 observations, and this figure is created based on the metadata from each sensor collected from January 1, 2000 to December 31, 2021. <br/><br/><br/>

<img src="https://github.com/GERSL/L7Drift/blob/main/dirft_effects_2021.png"/>
Figure 2. Effect of Landsat 7’s orbit drift in 2019, 2020, and 2021. (a) Surface reflectance of spectral bands and their derived NDVI values. (b) TOA reflectance of spectral bands and their derived NDVI values. (c) BRDF normalized surface reflectance of spectral bands and their derived NDVI values.<br/><br/><br/>

**Reference: [Qiu, S., Zhu, Z., Shang, R., & Crawford, C. J. (2021). Can Landsat 7 preserve its science capability with a drifting orbit?. Science of Remote Sensing, 100026.](https://doi.org/10.1016/j.srs.2021.100026)**
