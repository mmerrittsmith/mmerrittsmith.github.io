---
layout: post
title:  "Rothko: A Set of Color Palettes for R"
date:   2021-03-03 11:00:00
categories: r color
excerpt_separator: <!--more-->
---

{% newthought 'Rothko' %} is a set of color palettes for R in the form of an R package. It follows directly from Karthik Ram's <a href = "https://github.com/karthik/wesanderson">wesanderson</a> package, but instead uses color palettes derived from the paintings of Mark Rothko. I used <a href = "https://imagemagick.org/">ImageMagick</a> to get these palettes, but there's many websites out there that can do the same thing. 
<!--more-->


### Installation
It's simple to install, and has options for both continuous and discrete data. Install it using the following commands:

```R

install.packages("devtools")
devtools::install_github("mmerrittsmith/Rothko")
```

### Usage & Examples
The palettes are named after the paintings they are derived from. This leads to some having rather long names like "Violet, Black, Orange, Yellow on White and Red". Others are named simply "Untitled 1949". My favorites are shown below under the command used to generate them. 

```R

rothko_palette("Number 10")
```
{% maincolumn 'images/img/Number10-1.png' 'Number 10'    %}

```R

rothko_palette("Light Cloud, Dark Cloud")
```
{% maincolumn 'images/img/LightCloudDarkCloud-1.png' 'Light Cloud, Dark Cloud'    %}

```R

rothko_palette("Number 16")
```
{% maincolumn 'images/img/Number16-1.png' 'Number 16'    %}

You can use these palettes in the same way you would use any other R color palette, for example as an argument to the <a href = "https://ggplot2.tidyverse.org/reference/scale_manual.html">scale_fill_gradientn</a> function in ggplot2. 