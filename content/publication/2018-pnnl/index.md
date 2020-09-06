+++
title = "Ultrasound Modeling and Simulation: Status Update"
date = 2018-12-01
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Gerges Dib", "Michael R Larche", "Matthew S Prowant", "Richard E Jacob", "Pradeep Ramuhalli", "Aaron A Diaz"]

publication_types = ["4"]

# Publication name and optional abbreviated version.
publication = "PNNL"
publication_short = ""

# Abstract and optional shortened version.
abstract = "The Pacific Northwest National Laboratory (PNNL) is conducting confirmatory research for the U.S. Nuclear Regulatory Commission for establishing standard methods of modeling and simulation to assess the effectiveness and reliability of ultrasonic inspections of nuclear power plant (NPP) components. This work is part of an ongoing effort to define best practices required for using computational models for ultrasonic testing (UT) reliability applications. In addition to model validity (i.e., the ability of a model to accurately reproduce all conditions of interest for a particular application), a number of other factors need to be taken into account, such as computational complexity, uncertainty in model predictions, and the ability to extrapolate findings from model predictions to realistic scenarios. In this part of the ongoing effort, we focus on beam modeling and evaluating the use of both beam models and flaw models for simulating weld inspections. We evaluate the dynamic ray tracing model capability for handling smoothly varying heterogeneous materials, as this approach is often applied for simulating UT behavior in weld geometries. Two types of beam models based on two commercial simulation software platforms common to the NDE nuclear industry, CIVA and UltraVision, are compared. The two software platforms implement different approaches to modeling the ultrasound beam, and this assessment assumes correctness of the implementation. Differences observed in the computed beam between the two software platforms are not surprising, given that different types of models are being compared. The dynamic ray tracing model (CIVA implementation of beam models) is used to evaluate beam simulation of austenitic weld inspection. This is done by attempting to reproduce empirically measured sound beams using simulations. Challenges in this approach are seen due to the complexity of weld modeling and the large number of parameters required to define welds. The correlation between beam amplitude incident onto flaws and the expected response amplitude from the flaw is also investigated. Beam simulations using 23 different types of single and dual-element probes are used to extract an amplitude metric representing the sound beam amplitude incident onto flaws of different dimensions. Then, this metric is compared with the maximum expected response amplitudes from circumferentially oriented crack-like flaws of different depths. This study shows the complex relationship between flaw scattering and incident beams, thus limiting the interpretability of beam simulations for NDE reliability. Different types of normalizations and methods to quantify access limitations are also considered in this study. To further understand the ability to use flaw models to simulate ultrasonic weld inspection, a welded specimen with a machined reflector (saw-cut flaw) was scanned using different types of transducers. Those measurements are compared with simulated results using the dynamic ray tracing model in CIVA. This work illustrates the importance and the necessity for requiring well characterized weld properties as model inputs. Finally, initial work in transducer characterization is conducted to illustrate the possible variations in performance of transducers that have similar specifications. This study shows that even with the same transducer specifications and manufacturers, the frequency response and near-field distance of transducers can vary significantly. This variance is likely to have a direct effect on signal-to-noise ratio and must be taken into account when conducting model-based studies of ultrasonic inspections."
abstract_short = ""

# Is this a featured publication? (true/false)
featured = false

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["ut-modeling"]

# Slides (optional).
#   Associate this page with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["nuclear", "NDE", "ultrasound"]

# Links (optional).
url_pdf = "https://www.dropbox.com/s/0fv3ptbwqtuhhgi/2018-pnnl.pdf?dl=0"
url_preprint = ""
url_code = ""
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{name = "Custom Link", url = "http://example.org"}]

# Digital Object Identifier (DOI)
doi = ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++
