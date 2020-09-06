+++
# Project title.
title = "Eddy Current Inspection Autoanalysis of Steam Generator Tubes in Nuclear Power Plants"

# Date this page was created.
date = 2012-06-01T00:00:00
share = true

# Project summary to display on homepage.
summary = "Building signal processing and machine learning pipelines for defect detection and classification within steam generator tubes."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["NDE", "signal processing"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com/georgecushen"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder.
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
  preview_only = true
+++

<center>
{{<figure src="featured.png" width="400px" caption-position="bottom" caption-effect="fade" caption="Processing pipeline for autoanalysis software.">}}
</center>

Steam generators (SG) are heat exchanger units used in nuclear power plants. Each SG unit typically contains 10000 - 20000 tubes which are exposed to harsh environmental conditions such as high temperatures, high pressures, high fluid flow rates and material interactions resulting in various types of tube degradations - mechanical wear, stress corrosion cracking (SCC), pitting, volumetric degradation, inter granular attack (IGA), loose parts and denting. Electromagnetic methods at low frequencies such as eddy current (EC) have been widely used for inspecting SG tubes. Generally, trained experts will analyze the acquired data looking for any damage indication. However, due to the large volume of data, manual inspection is highly susceptible for a person to miss an indication of damage in the data. The goal of this project is to automate damage detection and classification for eddy current inspection of steam generator tubes in nuclear power plants.

The automated signal analysis system pipeline involves 1) pre-processing and region of interest (ROI) detection, 2) feature extraction and 3) classification. We used physics based feature extraction and machine learning techniques to automate and enhance the current state-of-the-art performance of manual signal analysis. We tested the pipelines using data from a performance demonstration database consisting of on-site inspection data obtained from multiple nuclear power plants in the USA.
