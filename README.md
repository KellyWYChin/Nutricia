# Danone Nutricia

Internship Oct. 2021 - Feb. 2022

Author: Kelly Wen-Yu Chin

### ‼️ Due to the confidential reasons, this file is only for sharing statistics concepts and some useful coding.

# Background

Dairy raw materials (RMs) are good source of proteins and nutrients such as vitamins and minerals. The amount of these nutrients in dairy RMs differs among seasons and regions, because of different farm management and nutritional values in the diet consumed by cows. Nutritional values fluctuate in dairy RMs result in nature variation. These natural variations of nutrients influence recipe calculation and quality and food safety. The more variability it is in RMs, the more difficult it is to have stable amount of nutrients in our products.

According to the current recipe calculation mehod, the variation of nutrients is based on the 6-sigma approach, allowing 99% of the values of each nutrient in recipe design for nutrition calculation. This is a very safe and conservative way to estimate the nutrient levels. Highly processed dairy RMs and additional single dose vitamin and minerals were therefore, added in the recipe to reduce the variation and fortify the nutrient levels.

However, the nutrients in RMs might be more stable and consistent in certain pattern. Nutrients which are contributed largely by dairy RMs would have seasonal changes and are more various in certain regions due to the different farming management. Therefore, the more we understand the nutrient levels in the RMs, the more efficient we can make good use of the natural variation and reduce the unnecessary overestimated variation in our recipe design.

The objective of this internship is to understand the variation of nutrients. Based on the comprehension of the natural variation of nutrients in RMs, an advanced way of recipe design principle will be developed. Also, a modified recipe is developed to further evaluate if we can use more natural RMs in the recipe design and to understand if nutrient levels will be in compliance with the original recipe. 

# Materials and Methods

## Available data

**BestMix** provided the weight of RMs and nutritional values.

**Raw Material Monitoring Program (RMMP)** provided nutirent levels of dairy RMs.

**Factory measurements**to understand the nutrient levels in the blended milk powder. Data between April 2019 to September 2019 are used in the analysis.

**Quality and Food Safety (QFS) Standard** for Specialized Nutrition (SN) has set nutritional standards (ownership of R&I Developmental Physiology and Nutrition Platform) for nutritional composition of all products to assure and promote consumers’ health. The ranges of nutrients are regulated as +/- percentages around the target value on the label and are used to judge whether the actual nutritional composition of a product is in line with the labelled values at any point during the shelf life.

## R version

Data editing and analysing was performed with RStudop (Version 4.0.2, URL: https://cran.rstudio.com)

## Computational Statistics

**Beta PERT distribution** is used to assume the distribution of stable RMs, which we merely have minimum, most likely (target), and maximum values of nutrient levels. The mean of the distribution is therefore defined as the weighted average of the minimum, most likely and maximum values that the variable may take, with four times the weight applied to the most likely value. The three parameters defining the distribution are intuitive the estimator.

**Non-parameteric - Bootstrap** is a compuational resampling technique of inference about a population of interest using sample data, with the only input being the procedure for calculating the estimate (or estimator) of interest on a sample of data. It works by treating the observed sample as if it were the population, and we can repeatedly take R number of samples (of the same size as the original sample), *with replacement*. 

The BS process in as follows: 
  
* For each dairy RM that has RMMP data, sample one value, with replacement.
* For each RM that has only min, target, and max values, make a beta PERT distribution and sample from the beta distribution with replacement.
* Sum these sampling values
* Repeat 100000 times
* Calculate the mean and 2.5\% and 97.5\% percentiles

# Overall findings and room for improvements

* Bootstrap works well in the estimation of nutrient in original recipe and the simulated variation is indeed smaller than the 6 sigma approach. Bootstrap can be used in future recipe calculation.

* The nutritional values in modified recipe are in compliance with the nutritional values in original recipe. We can indeed try to reduce the use of highly-processed dairy RMs.

* Small sample size and limited data points of the nutritional values of dairy RMs were available, which may lead to a baised estimation for bootstrap simulation. More annual measurements of dairy raw materials will help to develop a more precise estimation.

* Improvement of data integration from different sources is desired. Data from BestMix, RMMP, Factory, and QFS standard can be integrated. A more direct way of nutrient data integration can be developed.

## License

This project is licensed under the terms of the [MIT License](/LICENSE.md)

