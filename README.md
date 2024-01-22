# Predict-Product-Categories-and-Brands-Using-CLIP-Embeddings
In this project, we aim to classify product categories (based on the Google taxonomy) and brands using fine-tuned CLIP embeddings. Our primary focus will be on aggregating textual and image embeddings to achieve a more representative depiction of the products, leading to enhanced performance.

## Google Taxonomy
In general, a taxonomy refers to a classification system, often hierarchical, used to organize and categorize information. Simply put, Google Taxonomy is the list of categories used by Google to help departmentalize products in a shopping feed. There are more than 6,000 categories and the full Taxonomy and category list can be found here: https://support.google.com/merchants/answer/6324436?hl=en.

![google_taxo](https://github.com/Abdennacer-Badaoui/Predict-Product-Categories-and-Brands-Using-CLIP-Embeddings/assets/106801897/22203e4a-3df7-4ecd-b12a-2761bdf2dc1d)

## Why predict a product category and brand?
Even if partners provide product data with predefined categories and brands, it is always beneficial to attempt predicting them anew. This is primarily due to the inherent uncertainty and potential inconsistencies in partner-supplied data, making it unwise to rely solely on external information. In addition to this, there are other crucial reasons for attempting to predict both the category and brand of products. Constructing audiences, for instance, becomes more effective when based on accurate predictions, ensuring a targeted and relevant approach. Moreover, by limiting the categories to those aligned with the Google Taxonomy, we establish a universal and standardized framework, simplifying data management and enhancing consistency. Normalizing brands, such as aggregating variations like "Nike," "NIKE," and "Nike Air" into a single brand, contributes to cleaner and more accurate datasets, facilitating streamlined analysis and decision-making processes. Overall, predictive modeling not only addresses data reliability concerns but also optimizes audience construction and standardizes product categorization for improved data quality and coherence.

## Models overview
The classification model used is a fully connected neural network with a softmax layer, layer normalization after each linear transformation, and the tanh activation function.

|                          | Category model                                     | Brand model                  |
| :-----------             |:--------------:                                    | :-------------:              |
| Textual features         | Title, Description, Brand, Cat1, Cat2, Cat3        | Title, Description, Brand    |
| Visual Features          | Product Image                                      | Product Image                |
| Finetuning               | Yes                                                | No                           |
| Output classes           | 3215                                               | 7978                         |

The category model was fine-tuned on a more specific dataset for business reasons.
Note that we use the categories and brands given in the data to predict the universal category and the universal brand.
