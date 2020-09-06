+++
title = "Validation of Ultrasound NDE Simulation Models"
date = 2018-09-01
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["NDE", "ultrasound", "signal processing"]

# Project summary to display on homepage.
summary = "Supporting regulatory guides for the nuclear power plant industry in relation to using ultrasound computational models for non-destructive inspection."

# Slides (optional).
#   Associate this page with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Optional external URL for project (replaces project detail page).
external_link = ""

# Links (optional).
url_pdf = ""
url_code = ""
url_dataset = ""
url_slides = ""
url_video = ""
url_poster = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "smart"
+++


[Non-destructive evaluation and testing (NDE)](https://en.wikipedia.org/wiki/Nondestructive_testing) is essential for ensuring the safety of operational nuclear power plants around the world. Ultrasonic testing is an NDE technique which is largely utilized for inspecting pipelines in the nuclear industry due to its ability to detect flaws hidden within the inner diameter of pipelines.

Computer modeling and simulation is becoming an essential tool for transducer design and insight into ultrasonic nondestructive evaluation. For computational models to be of use in practical situations, it is important to develop techniques for inferring the reliability of inspections using simulated results. This includes information about the detectability of different defect types within different material varying in complexity and grain structure. To address this problem, we need to develop techniques to quantify confidence in simulations, and methods to incorporate experimental and structural noise into model outputs.

In this project, we are building a large database of ultrasound inspection empirical data using different types of probes, materials, and defects. We are using this empirical data to: (1) Develop techniques for validating ultrasound inspection simulations; (2) Uncertainty quantification due to uncertain or unknown simulation input parameters; and (3) Develop noise models which can be fused with simulation data for analyzing inspection reliability using simulated data.