---
layout: post
title:  "Partial Dependence Plots in Python and R"
date:   2018-12-2 19:30:27
categories: python r sklearn randomforest
---

{% newthought 'In writing my undergrad thesis' %} on wealth inequality and using various techniques for predicting it, I found myself disappointed that there was no simple method in Python's scikit-learn to generate partial dependence plots for random forests. The ability to create partial dependence plots for gradient boosted regressors <a href ="https://scikit-learn.org/stable/auto_examples/ensemble/plot_partial_dependence.html">exists</a>, so why not for random forests, or anything else for that matter? In this post, I'll discuss partial dependence plots, what they are, how they're useful in ensemble methods, and dive into the state of the art for partial dependence plots in both Python and R.


<br>
### What's a partial dependence plot?

A partial dependence plot is an attempt to open up the black box of ensemble methods. Normally, we can compute the importance of a given variable in estimating the response varaible, but do not have a great intuition as to the decision surface of even the most important variables. Partial dependence plots allow us to see the marginal effect of a given variable on the response variable by integrating out all of the other variables. They allow us to see the effect of a single variable on the response variable, which is otherwise not possible in ensemble methods. Thus, they're a very powerful tool. Ensemble methods are being left by the wayside in 2018 for ever more complicated neural nets, but ensemble methods continue to provide a powerful and much more interpretable option for both regression and classification thanks to partial dependence plots. Now let's see what they look like!


### State of the code: Python

 There's been <a href = "https://github.com/scikit-learn/scikit-learn/issues/4405">motion</a> <a href = "https://github.com/scikit-learn/scikit-learn/pull/5653">on</a> <a href = "https://github.com/scikit-learn/scikit-learn/pull/12599">the topic</a> of partial dependence plots since 2015 within sklearn, as well as some external work towards <a href = "https://github.com/nyuvis/partial_dependence">a generalized partial dependence plot library</a> that can connect to the extant classifiers and regressors. I decided to test each of these tools out. The sklearn partial dependence plot is still going through edits, but it performs admirably, creating simple R-style partial dependence plot matrices.


{% maincolumn 'assets/img/SklearnPDP.png' 'Partial Dependence Plots of fixed acidity and volatile acidity on perceived wine quality using data from UCI Machine Learning Repository Wine Quality Dataset, specifically using white wine portion.'    %}


<br>
The code also extends easily to create three dimensional partial dependence plots, should that tickle your fancy. Not normally my cup of tea, but in this case it allows for a more pithy data visualization and efficiently demonstrates variable interaction. 

{% maincolumn 'assets/img/SklearnPDP3D.png' '3D Partial Dependence Plot of fixed acidity and volatile acidity on perceived wine quality using data from UCI Machine Learning Repository Wine Quality Dataset,
specifically using white wine portion. '%}

<br>

What's more, this tool, if implemented, would be integrated seamlessly into the most commonly used Python machine learning library and would be a plotting option for every single ensemble method within sci-kit learn. That's big. 

<br> 

A more established and feature-rich Python library for plotting partial dependence is the NYU Visualization Lab's 'partial_dependence'. 