# Raisin Dataset Classification

## Overview

This project evaluates three machine learning algorithms—Decision Tree (J48), Naïve Bayes, and Multilayer Perceptron (MLP)—using the Raisin Dataset. The goal is to analyze the performance of each model through various preprocessing techniques and hyper-parameter adjustments.

## Dataset

- **Name:** Raisin Dataset
- **Instances:** 900
- **Attributes:** 8 (Area, MajorAxisLength, MinorAxisLength, Eccentricity, ConvexArea, Extent, Perimeter, Class)

Attribute Information:

1. **Area**: Gives the number of pixels within the boundaries of the raisin. 
2. **Perimeter**: It measures the environment by calculating the distance between the boundaries of the raisin and the pixels around it.
3. **MajorAxisLength**: Gives the length of the main axis, which is the longest line that can be drawn on the raisin.
4. **MinorAxisLength**: Gives the length of the small axis, which is the shortest line that can be drawn on the raisin.
5. **Eccentricity**: It gives a measure of the eccentricity of the ellipse, which has the same moments as raisins. 
6. **ConvexArea**: Gives the number of pixels of the smallest convex shell of the region formed by the raisin.
7. **Extent**: Gives the ratio of the region formed by the raisin to the total pixels in the bounding box.
8. **Class**: Kecimen and Besni raisin.

## Project Structure

1. **Introduction**
2. **Dataset and Attributes**
3. **Experiments and Results**
   - Decision Tree (J48)
   - Naïve Bayes
   - Multilayer Perceptron (MLP)
4. **Conclusion**

## Experiments and Results

### Decision Tree (J48)

- **Preprocessing:** Discretized attributes into 5 bins using the Discretize filter.
- **Initial Hyper-Parameters:**
  - confidenceFactor: 0.25
  - minNumObj: 2
  - useLaplace: FALSE
  - binarySplits: FALSE
  - Seed: 1
- **Updated Hyper-Parameters:**
  - confidenceFactor: 0.15
  - minNumObj: 5
  - useLaplace: TRUE
  - binarySplits: TRUE
  - Seed: 1

**Results:**

| Metric      | Initial   | Updated   |
|-------------|-----------|-----------|
| F measure   | 0.805     | 0.807     |
| Accuracy    | 80.56%    | 80.67%    |
| Precision   | 0.807     | 0.808     |
| Recall      | 0.806     | 0.807     |

### Naïve Bayes

- **Preprocessing:** Applied Normalize filter to all numeric attributes.
- **Initial Hyper-Parameters:**
  - useKernelEstimator: FALSE
- **Updated Hyper-Parameters:**
  - useKernelEstimator: TRUE

**Results:**

| Metric      | Initial   | Updated   |
|-------------|-----------|-----------|
| F measure   | 0.834     | 0.852     |
| Accuracy    | 83.56%    | 85.22%    |
| Precision   | 0.848     | 0.857     |
| Recall      | 0.836     | 0.852     |

### Multilayer Perceptron (MLP)

- **Preprocessing:** Discretized attributes into 5 bins using the Discretize filter.
- **Initial Hyper-Parameters:**
  - hiddenLayer: a
  - trainingTime: 500
  - learningRate: 0.3
  - momentum: 0.2
- **Updated Hyper-Parameters:**
  - hiddenLayer: 2,a,2
  - trainingTime: 1000
  - learningRate: 0.1
  - momentum: 0.3

**Results:**

| Metric      | Initial   | Updated   |
|-------------|-----------|-----------|
| F measure   | 0.865     | 0.863     |
| Accuracy    | 86.56%    | 86.33%    |
| Precision   | 0.866     | 0.864     |
| Recall      | 0.866     | 0.863     |

## Conclusion

Tuning hyper-parameters improved the performance of Decision Tree and Naïve Bayes models, but did not significantly enhance the Multilayer Perceptron. The optimized settings led to higher accuracy and precision, particularly for Naïve Bayes. These results highlight the importance of hyper-parameter adjustments in enhancing machine learning models. Future work should focus on further fine-tuning and validation to ensure robust performance.

## Authors

- Mohammed Abed Alkareem
- Mosa Sbeih

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
