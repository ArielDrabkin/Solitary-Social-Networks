# Social Network Analysis in an Extreme Solitary Reptile Species

This repository contains the code and data for a data science project that explores the existence of a social network in an extreme type of solitary reptile species. The study focuses on the Sinai chameleon (Chamaeleo chamaeleon musae), an annual lizard that inhabits desert shrubs and does not have permanent burrows. The aim of the project is to examine the hypothesis that even in such extreme solitary species, a social network can be identified by analyzing the locations of the individuals.

## Introduction
The social structure of different species has been studied using social networks, which capture encounters or interactions between individuals in a population. However, the social networks of extremely solitary species, like the Sinai chameleon, have not been explored extensively. This project aims to fill this gap by investigating the potential for microorganism transmission in extreme solitary species.

## Dataset
The dataset used in this project consists of 1984 records of chameleon sleeping locations collected in two field sites near Ashalim, Israel. The data was collected monthly from 2009 to 2017, covering a period of six full years (2012-2017). It includes a total of 880 sleeping locations.

## Methods
The analysis was performed using R language and various packages such as geosphere and igraph. The following steps were followed to construct the social network:

### Part 1: Checking which point is in which polygon
1. Fixed the list of coordinates associated with the road using the geosphere package.
2. Extracted azimuth information from the polygons raster file.

### Part 2: Correcting coordinates
1. Read and merged data from AzPolygons.csv and cham-by-polygon.csv files using the sp and rgdal packages.
2. Calculated the corrected coordinates based on azimuth and quarter.
3. Checked and fixed angles outside the range of 0-360 using R base functions.

### Part 3: Checking distances between points
1. Read and converted coordinates to a spatial data frame using the sp package.
2. Created a template of all possible point combinations.
3. Calculated distances between each pair of points using the distGeo function from the geosphere package.

### Part 4: Creating the social network
1. Created a graph object and adjacency matrix using the igraph package.
2. Calculated weighted degrees and average weighted degree using the igraph package.
3. Calculated betweenness centrality and average betweenness centrality using the igraph package.

## Results
The analysis revealed the presence of a social network in the Sinai chameleon population for each year studied. The social networks varied in complexity and were based on different numbers of encounters between individuals. Notably, 2015 had the most complicated social network with 319 encounters, while 2013 had the fewest (89) encounters and the simplest social network.

## Discussion
The study's findings suggest that the Sinai chameleon, despite being an extreme solitary reptile species without permanent burrows, exhibits a social network. This supports previous observations of social networks in solitary reptiles with permanent burrows. The existence of encounters among individuals in extreme solitary species can lead to microorganism transmission, potentially affecting individual fitness. Further research is required to understand the stability and transmission of microorganisms among reptiles, but the study provides a theoretical foundation and highlights the importance of collecting field data.

## Citation
If you use this code or dataset in your research, please cite the following references:

- Godfrey, S. S. Networks and the ecology of parasite transmission: A framework for wildlife parasitology. Int. J. Parasitol. Parasites Wildl. 2, 235–245 (2013).
- Ibrahim, A. A. Some aspects of ecology of the common chameleon, Chamaeleo chamaeleon musae ( Squamata : Chameleonidae) in northern Sinai, Egypt.
- Shachal, R. and Bouskila, A., 2011. Unusual life history of Chamaeleo chamaeleon musae forms unique population dynamics (abstract), Isr. J. of Ecol. Evol. 57:267.
- Sih, A., Spiegel, O., Godfrey, S., Leu, S. & Bull, C. M. Special Issue: Social Networks Integrating social networks, animal personalities, movement ecology and parasites: a framework with examples from a lizard
