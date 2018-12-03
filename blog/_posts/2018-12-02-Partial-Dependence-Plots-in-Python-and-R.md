---
layout: post
title:  "Partial Dependence Plots in Python and R"
date:   2018-12-2 19:30:27
categories: python r sklearn randomforest
---

## Introduction
{% newthought 'In writing my undergrad thesis' %} on wealth inequality and using various techniques for predicting it, I found myself disappointed that there was no simple method in Python's scikit-learn to generate partial dependence plots for random forests. The ability to create partial dependence plots for gradient boosted regressors <a href ="https://scikit-learn.org/stable/auto_examples/ensemble/plot_partial_dependence.html">exists</a>, so why not for random forests? 

### State of the code: Python

I'm obviously not the first one to ask this question. There's been <a href = "https://github.com/scikit-learn/scikit-learn/issues/4405">motion</a> <a href = "https://github.com/scikit-learn/scikit-learn/pull/5653">on</a> <a href = "https://github.com/scikit-learn/scikit-learn/pull/12599">this topic</a> since 2015 within sklearn, as well as some external work towards <a href = "https://github.com/nyuvis/partial_dependence">a generalized partial dependence plot library</a> that can connect to the extant classifiers and regressors. Stylistically, I'm a much bigger fan of the latter than the former, but I certainly see the utility of 3-d partial dependence plots. 

{% maincolumn 'assets/img/pdplibrarypdp.png' 'Partial Dependence Plot of '   %}

