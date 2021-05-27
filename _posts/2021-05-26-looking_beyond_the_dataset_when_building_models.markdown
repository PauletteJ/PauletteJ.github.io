---
layout: post
title:      "Looking Beyond the Dataset When Building Models"
date:       2021-05-27 03:41:29 +0000
permalink:  looking_beyond_the_dataset_when_building_models
---


It's easy to think of a dataset as a defined unit. After all, it was created with specific criteria. But what do you do when you build a model from that data, and a small subset of point just won't behave. Perhaps they are outliers to be ignored. Or perhaps there's something more. This is where data science gets interesting.

Recently, I was given a project to model sale prices of King County homes. This was a Flatiron bootcamp project that used sale prices from 2015 (note that this is prepandemic data).

Zipcode was an important feature of the model. Most zipcodes had a p-value of <0.05, indicating that the model produced significant predictions. However, there were seven zipcodes that had p-values above that benchmark.

One represented a relatively isolated suburban community, Enumclaw, near Mount Rainier National Park. It is easy to understand why that would be an outlier. The others, however, were urban/suburban communities (Kent, Auburn, and Federal Way) that were part of the Seattle metropolis. 

Why were they different than the rest of the greater metropolitan area? Let's consider a map of the county.

![Map of King County WA](https://www.wmnorthwest.com/kingcounty/gif/map.gif)

These zipcodes created a line that was just above the border between King County and Pierce County.

Borders are interesting. Any historian will tell you that. Think of the French-German border in the early 20th century. Ecologists find borders equally interesting. The border between a forest and a field has more biodiversity than either ecological niche. Small animals than can find shelter in the forest and food in the field will not stray far from either. I have a strong background in biology, so my mind drew from the ecological niche paradigm. 

What is not labeled on this map, because it is in Pierce County, is the city of Tacoma. In the lower left of the map you can see the outline of the port just southwest of Federal Way.

These cities have a different uniqueness, as they are on major commuting routes. Kent and Auburn are along State Route 167, and Federal Way is along I-5. These cities are as far south as most people in the county are willing to live and still commute north to Seattle or Bellevue/Redmond, the two biggest job centers in the county. Federal Way is a bit further south than Kent, and that make sense when you consider that SR167 gets more conjested than I-5 during commuting hours. The commute times from Seattle and Bellevue/Redmond are comparable. 

They are also close enough to Tacoma that one could commute to that major city. However, anything north of Federal Way and Kent would typically be too expensive for commuters on a Tacoma salary. These zipcodes could be influenced be being acceptable markets for commuters in both cities.

What this model seems to suggest is that Kent, Auburn, and Federal Way home prices have different influences not predicted by this model. A reasonable influence could be proximity to both the Seattle and Tacoma job markets, and are therefore acting as a border between the two markets. Auburn's p-value was not as high, and that could be explained by it being less influenced by this effect and more like rural zipcodes in the county. That would align with the fact that is has a longer commute to Seattle than Kent or Federal Way. 

While this model doesn't define this as *the* reason behind the model behaving differently for these zipcodes, it does point to them being an area of interest for further study. And more to the point, it was a surprise. Had I treated these zipcodes as mere outliers and not considering them as a whole, I would have missed an interesting observation that may have significant implications for anyone buying or selling in those communities.


