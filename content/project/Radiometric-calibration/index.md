---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Radiometric calibration of UAV-based spectral imagery"
summary: ""
authors: [Ali Moghimi]
tags: []
categories: []
date: 2019-10-14T16:50:48-07:00

# Optional external URL for project (replaces project detail page).
external_link: ""
# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Various methods to convert raw digital number to reflectance"
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:

#name: Follow
#url: https://twitter.com/a_moghimi/status/1232779692555390976?s=21
#icon_pack: fab
#icon: twitter

# name: Follow
# url: https://twitter.com/a_moghimi/status/1232779692555390976?s=21
# icon_pack: fab
# icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: "Poster_Phenome2020_AliMoghimi.pdf"
---
# Research Objective:

Radiometric calibration of aerial spectral images is a key step before post-processing to assure the repeatability of a proposed analysis pipeline over various flight missions, dates, weather conditions, and imagers. An appropriate radiometric calibration process has two main steps: (i) converting raw images to radiance (Wm-2sr-1nm-1) to account for sensor-dependent factors such as spatial and spectral inconsistency in detectors of the camera (e.g., gain, offset, and quantum efficiency), (ii) converting radiance images to reflectance to account for variation in intensity of incident light over time. The objectives are to (i) examine the importance of radiometric calibration with the focus on radiance conversion, and (ii) to identify the appropriate approach for reflectance conversion. In this study, we used a multispectral camera (Micasense RedEdge) and a hyperspectral camera (Resonon PIKA L).

# Micasense RedEdge
We mounted the RedEdge camera on a DJI Matrice 210. To convert the raw multispectral images to radiance, we developed a Python script that generates radiometrically-calibrated stacked multispectral images in a batch processing manner using the information embedded in the header file of images. To convert radiance images to reflectance, the algorithm offers three options to calculate the incoming irradiance: (i) using the images captured from the Micasense panel (or a tarp with a known reflectivity) before the flight mission, (ii) using the downwelling light sensor (DLS) data, and (iii) using the DLS data refined by a site-specific compensation factor which is a ratio between the irradiance computed using the panel to the irradiance measured by DLS.

![](/img/MS_radiometric-calibration.png)

# Resonon PIKA L
We mounted the PIKA L camera on a DJI Matrice 600Pro. To convert the raw hyperspectral images to radiance, we used a vendor-supplied calibration file and Spectronon software. Similar to the multispectral images, we converted the hyperspectral images in radiance to reflectance using the incoming irradiance calculated through the above-mentioned options. However, instead of the Micasense panel, we used a tarp with 26% reflectivity.  

![](/img/HS_radiometric-calibration.png)


# Flight Missions
We flew with both sensors over a tarp composed of three 1x3 meter fabric with 6%, 12%, and 25% reflectivity several times, each of which with various gain/exposure settings. We examined six and four gain/exposure settings for multispectral and hyperspectral imaging, respectively.

The quantitative results in the figures demonstrates the significance of radiance conversion in reduction of the uncertainty caused by inconsistence sensor factors, and subsequently, assure the repeatability of a proposed analysis pipeline.

# Conclusion
In this study, we examined the importance of radiometric calibration with the focus on radiance conversion which is commonly overlooked in the calibration process. However, radiance conversion is important to account for sensor-dependent factors such as gain and exposure time. The results demonstrated that the reflectance values of each tarp (with 6%, 12%, and 25% reflectivity) was a function of camera settings due to ignoring radiance conversion (i.e., converting raw images directly to reflectance). Our findings underscore the importance of radiance conversion to assure the repeatability of a proposed analysis pipeline over various flight missions, dates, weather conditions, and imagers. 
