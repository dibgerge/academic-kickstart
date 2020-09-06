+++
# Project title.
title = "Wireless Senor Networks for Structural Health Monitoring"

# Date this page was created.
date = 2010-04-27T00:00:00

share = false

# Project summary to display on homepage.
summary = "Building hardware interfaces for integrating ultrasound guided waves sensors with wireless sensors."

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["SHM", "NDE", "ultrasound"]

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
<div style="text-align: center;">
{{<figure src="featured.jpg" width="400px" caption-position="bottom" caption-effect="fade" caption="Schematic of sensor network with centralized architecture.">}}
</div>

The use of wireless sensor networks in structural health monitoring can significantly increase safety and reduce manufacturing and maintenance costs. In this project, we integrate guided wave sensors with wireless sensor modules for continuous monitoring of civil structures. The wireless sensors eliminate the need for cables, reducing overall structure weight (especially important in aerospace industry) and single points of failure. We designed sensor interface boards for the Iris wireless nodes allowing transmitting and receiving guided waves using piezoelectric sensors. A distributed control algorithm is also implemented for controlling a wireless sensor network from a base station.
{{<gallery caption-position="center" caption-effect="fade">}}
  {{<figure width="300px" src="project/wsn/wsn_board.png" link="wsn_board.png" caption="Sensor interface circuit board for guided wave reception.">}}
  {{<figure width="300px" src="project/wsn/wsn_demo.jpg" link="wsn_demo.jpg" caption="Two sensor nodes configured for in transmit-receive mode.">}}
{{</gallery>}}
