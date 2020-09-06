+++
title = "Ensembles of novelty detection classifiers for structural health monitoring using guided waves"
date = 2017-11-17
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Gerges Dib", "Oleksii Karpenko", "Ermias Koricho", "Anton Khomenko", "Mahmoodul Haq", "Lalita Udpa"]

publication_types = ["2"]

# Publication name and optional abbreviated version.
publication = "Smart Material and Structures"
publication_short = "SMS"

# Abstract and optional shortened version.
abstract = "Guided wave structural health monitoring uses sparse sensor networks embedded in sophisticated structures for defect detection and characterization. The biggest challenge of those sensor networks is developing robust techniques for reliable damage detection under changing environmental and operating conditions (EOC). To address this challenge, we develop a novelty classifier for damage detection based on one class support vector machines. We identify appropriate features for damage detection and introduce a feature aggregation method which quadratically increases the number of available training observations. We adopt a two-level voting scheme by using an ensemble of classifiers and predictions. Each classifier is trained on a different segment of the guided wave signal, and each classifier makes an ensemble of predictions based on a single observation. Using this approach, the classifier can be trained using a small number of baseline signals. We study the performance using Monte-Carlo simulations of an analytical model and data from impact damage experiments on a glass fiber composite plate. We also demonstrate the classifier performance using two types of baseline signals: fixed and rolling baseline training set. The former requires prior knowledge of baseline signals from all EOC, while the latter does not and leverages the fact that EOC vary slowly over time and can be modeled as a Gaussian process."
abstract_short = ""

# Is this a featured publication? (true/false)
featured = false

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["gwshm"]

# Slides (optional).
#   Associate this page with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["SHM", "machine learning"]

# Links (optional).
url_pdf = "https://www.dropbox.com/s/mos9u5omerh1doy/2017-sms.pdf?dl=0"
url_preprint = ""
url_code = "https://github.com/dibgerge/gwshm-machine-learning"
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
doi = "10.1088/1361-665X/aa973f"

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++
