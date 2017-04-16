+++
abstract = "Monte Carlo simulations of the Ising model play an important role in the field of computational statistical physics, and they have revealed many properties of the model over the past few decades. However, the effect of frustration due to random disorder, in particular the possible spin glass phase, remains a crucial but poorly understood problem. One of the obstacles in the Monte Carlo simulation of random frustrated systems is their long relaxation time making an efficient parallel implementation on state-of-the-art computation platforms highly desirable. The Graphics Processing Unit (GPU) is such a platform that provides an opportunity to significantly enhance the computational performance and thus gain new insight into this problem. In this paper, we present optimization and tuning approaches for the CUDA implementation of the spin glass simulation on GPUs. We discuss the integration of various design alternatives, such as GPU kernel construction with minimal communication, memory tiling, and look-up tables. We present a binary data format, Compact Asynchronous Multispin Coding (CAMSC), which provides an additional 28.4% speedup compared with the traditionally used Asynchronous Multispin Coding (AMSC). Our overall design sustains a performance of 33.5 picoseconds per spin flip attempt for simulating the three-dimensional Edwards-Anderson model with parallel tempering, which significantly improves the performance over existing GPU implementations."
authors = ["Ye Fang", "Sheng Feng", "Ka-Ming Tam"]
date = "2014-05-24"
image_preview = ""
math = true
publication_types = ["2"]
publication = "Computer Physics Communications"
publication_short = "In *CPC*"
selected = true
title = "Parallel Tempering Simulation of the three-dimensional Edwards-Anderson Model with Compact Asynchronous Multispin Coding on GPU"
# url_code = "#"
# url_dataset = "#"
url_pdf = "https://arxiv.org/pdf/1311.5582"
url_project = "project/geauxising/"
# url_slides = "#"
# url_video = "#"

# [[url_custom]]
# name = "Custom Link"
# url = "http://www.example.org"

# Optional featured image (relative to `static/img/` folder).
[header]
image = "gpu.jpg"
caption = "A NVIDIA TESLA GPU."

+++


