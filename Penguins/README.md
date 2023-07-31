# Overview 
- A scientific organization that works to support and sustain penguin colonies. The task is to help staff members learn more about penguins in order to achieve this mission. 

- The data for this project includes datapoints across a sample size of 345 penguins, such as species, island, and sex. A model is required to group this data and identify patterns that provide important insights about penguins. In other words, the model is trying to confirm if penguins of the same species exhibit different physical characteristics based on sex or not.

# Data Understanding
The data for this project consists of 344 observations, and each observation in the data represents a unique penguin.

| Column Name        | Type   | Description                                 |
|--------------------|--------|---------------------------------------------|
| species            | str    | Penguin species                             |
| island             | str    | Island name in the Palmer Archipelago       |
| bill_length_mm     | float  | Length of penguin’s bill in millimeters     |
| bill_depth_mm      | float  | Depth of penguin’s bill in millimeters      |
| flipper_length_mm  | float  | Length of penguin’s flipper in millimeters  |
| body_mass_g        | float  | Penguin’s body mass in grams                |
| sex                | string | Penguin’s sex                               |

# Modeling and Evaluation 
- The following line plot shows the relationship between `num_clusters` and `silhouette`
![LinePlot](/Penguins/images/1.png)

The line plot indicates that the `silhouette` score is closest to 1 when the data is partitioned into six clusters, although five clusters also yield a relatively good `silhouette` score.

-  The following bar plot verifies that clusters can be differentiated by `species`
![BarPlot](/Penguins/images/2.png)

- The following bar plot verifies that clusters can be differentiated by `species` AND `sex_MALE`.
![BarPlot](/Penguins/images/3.png)

# Conclusion
- The K-means clustering enabled this data to be effectively grouped. It helped identify patterns that can educate team members about penguins.
- The success of the cluster results suggests that the organization can apply clustering to other projects and continue augmenting employee education.
