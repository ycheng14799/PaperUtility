# Paper Utility
## 11 August 2019 Progress 
Currently:
* We collected crowdsource results for 14 out of 20 of our attributes (except 15.Physical Manipulation, 16.Feedback, 17.Privacy, 18.Security, 19.Accessibility, and 20.Cost)
* We calculated the product preference rankings and absolute distance data for each attribute using the Bradley-Terry model
* We visualized our results in 4 ways: 
  * Bump chart to show ranking correlations 
  * A parallel coordinates plot 
  * [Radar graphs](https://github.com/ycheng14799/PaperUtility/tree/master/Radar_Chart%20of%20Products%20and%20Attributes) 
  * Heatmaps
  
  
### Bump chart 
![Bump Chart](https://github.com/ycheng14799/PaperUtility/blob/master/Data_Ranking_Plot.png)

### Crowdsource Results
We now have results for the following attributes: 1.Temporality, 2.Spatiality, 3.Range of Content Input, 4.Physical Reconfigurability, 5.Personalization, 6.Information Volume, 7.Information Variety, 8.Information Organization, 9.Information Findability, 10.Information Exploration, 11.Environment, 12.Durability, 13.Digitalization, and 14.Collaboration

We still need to publish HITs for: 15.Physical Manipulation, 16.Feedback, 17.Privacy, 18.Security, 19.Accessibility, and 20.Cost
We decided to hold off on these attributes because we could not decide on what questions to ask in order to ensure the quality of the survey response. 

For the attributes we now have results for, we relied on two quality check mechanisms: 
1. Including duplicate questions 
2. Asking for a comparison between a product from our set of 12 and tissues
We ended up rejecting about 37% of the completed assignments we received. Method 1 was helpful. Method 2 we quickly realized could be highly subjective. 

For the remaining 6 attributes, perhaps we should only use duplicate questions. 


### Bradley-Terry & Visualization 
With our pairwise comparisons, we calculated a preference score for each product. We tried out several off-the-shelf solutions (in [R](https://github.com/hturner/BradleyTerry2), MATLAB, and [Python](http://choix.lum.li/en/latest/index.html)). We have not yet decided on which solution to use. Besides from which off-the-shelf solution to use, we also have to decide on what estimation method to use for the BTL parameters. We are leaning towards using the MM algorithm as that was used previously by Professor [Andrew Horner](https://pdfs.semanticscholar.org/c3b2/10be60cfbff06e18f6047d1854a97e985b61.pdf). 

The following is a parallel coordinates plot of our results: 
![Parallel Coordinates Plot](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/ParallelCoordinatesPlotOne.png)
The plot shows the Bradley-Terry-Luce scale values of the products for each attribute. All values are shifted so the lowest BTL score is at 1. We decided not to normalize the values as the distance between each score is indicative of how much more one product was preferred over another. For instance, books received an absurdly high shifted score of approximately 8 in durability because it was highly preferred over the other products. Aside from one user comparison, all other user comparisons marked books as more preferable in durability than any other product.  

We also generated a radar graph for each product. Here is an example: 
![Radar Chart](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/Semi-structuredWrittenForms.png)
We have included more examples below.

Lastly, in Professor Horner's paper, he visualized the probability that one product will be prefered over another using a heatmap. We thought that that the visualization was highly informative, so we decided to do the same: 
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/heatmapExample.png)
This graph compares products for each attribute. The darker the color of a cell, the more positive votes its "row product" received when compared to its "column product". There are also more examples below.

#### Description of Radar Chart

After collecting and filtering data from M-Turk, we tried to use the Bradley-Terry-Luce model to calculate an absolute preference score of each product using: [*" A Matlab function to estimate choice model parameters from paired-comparison data "*](https://link.springer.com/article/10.3758/BF03195547)  

##### Description of the folder "Radar_Graph_Per_Attribute"

The graphs contained in the "Radar_Graph_Per_Attribute" folder show the product preference scores for each attribute. 

By measuring the "ratio scale" using the log-likelihood estimate of BTL, we draw a radar chart of each attribute. The bigger the "ratio scale", the higher preference one product will have for that particular attribute. 
Below is the radar chart for the "Collaboration" attribute:
![Collaboration](https://github.com/ycheng14799/PaperUtility/blob/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Attribute/Collaboration.png?raw=true)

##### Description of the folder "Radar_Graph_Per_Product"

The graphs contained in the "Radar_Graph_Per Product" folder show the attribute preference scores for each product. 

We use the same "ratio scale" as above. Books, Calendars, Large-Scale Paper Display, Magazines & Pamphlets and Maps & Spatial Plans are using the absolute result of BTL. We shifted all the values so that the lowest score is at 0.2. 

Below is the radar chart for "Paper Crafts & Artwork":
![Paper Crafts & Art Work](https://github.com/ycheng14799/PaperUtility/blob/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Paper%20Crafts%20%26%20Artworks(set%20minimum%20value%20%3D%200.2).png)

### Radar Charts (Plotly)
The following 5 radar charts were produced in Python using Plotly. The plots show the Bradley-Terry-Luce scale values of the products for each attribute. All values are shifted so the lowest BTL score is at one.
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/Books.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/Calendars.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/LargeScalePaperDisplays.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/Maps&SpatialLayouts.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PlotlyRadarGraphs/Notebooks&LooseLeafs.png)

### Radar Charts (Excel)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Books.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Calendars.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Large-Scale%20Paper%20Display%20(i.e.%20Posters).png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Maps%20%26%20Spatial%20Plans.png)
![Radar](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/Radar_Chart%20of%20Products%20and%20Attributes/Radar_Graph_Per_Product/Newspapers(set%20minimum%20value%3D0.2).png)

### Heatmaps
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PreferenceProbabilityHeatmaps/Collaboration.png)
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PreferenceProbabilityHeatmaps/Digitalization.png)
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PreferenceProbabilityHeatmaps/Durability.png)
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PreferenceProbabilityHeatmaps/Environment.png)
![Heatmap](https://raw.githubusercontent.com/ycheng14799/PaperUtility/master/PreferenceProbabilityHeatmaps/InformationExploration.png)
