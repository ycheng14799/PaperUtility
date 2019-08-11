# Paper Utility
## 11 August 2019 Progress 
Currently:
* We collected crowdsource results for 14 out of 20 of our attributes
* We calculated the product preference rankings for each attribute using the Bradley-Terry model
* We visualized our results in 3 ways: 
  * A parallel coordinates plot
  * Radar graphs
  * Heatmaps
### Crowdsource Results
We now have results for the following attributes: Temporality, Spatiality, Range of Content Input, Physical Reconfigurability, Personalization, Information Volume, Information Variety, Information Organization, Information Findability, Information Exploration, Environment, Durability, Digitalization, and Collaboration

We still need to publish HITs for: Physical Manipulation, Feedback, Privacy, Security, Accessibility, and Cost
We decided to hold off on these attributes because we could not decide on what questions to ask in order to ensure the quality of the survey response. 

For the attributes we now have results for, we relied on two quality check mechanisms: 
1. Including duplicate questions 
2. Asking for a comparison between a product from our set of 12 and tissues
We ended up rejecting about 37% of the completed assignments we received. (1) was helpful. (2) we quickly realized could be highly subjective. 

For the remaining 6 attributes, perhaps we could just use (1). 
### Bradley-Terry & Visualization 
With our pairwise comparisons, we calculated a preference score for each product, using the BT(L) model, for each attribute. We tried out several off-the-shelf solutions (in [R](https://github.com/hturner/BradleyTerry2), MATLAB, and [Python](http://choix.lum.li/en/latest/index.html)). We have not yet decided on which solution to use. Besides from which off-the-shelf solution to use, we also have to decide on what estimation method to use for the BT(L) parameters. We are leaning towards using the MM algorithm as that was used previously by Professor Andrew Horner. 

The following is a parallel coordinates plot of our results: 
![Parallel Coordinates Plot](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/ParallelCoordinatesPlot.png)
The plot shows the Bradley-Terry-Luce scale values of the products for each attribute.

We also generated a radar graph for each product. Here is an example: 
![Radar Chart](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Semi-structuredRadarExample.png)

Lastly, in Professor Horner's paper, he visualized the probabilities that one product will be prefered over another using a heatmap. We thought that the visualization was highly informative, so we decided to do the same: 
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/heatmapExample.png)
The graph shows the comparison between products for each attribute. The darker the color of a cell, the more positive votes its "row product" received when compared to its "column product". 


