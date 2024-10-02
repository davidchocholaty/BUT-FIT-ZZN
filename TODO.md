Classification
----------------
Mezi vhodné algoritmy pro tuto úlohu patří rozhodovací stromy, náhodné lesy, podpora vektorových strojů (SVM) a logistická regrese

Clustering
------------
K-Means, DBSCAN, Hierarchical Clustering

jestli provest one-hot encoding na kategoricke atributy??? - ne napsat do textu
jestli provest binning na vek - ne napsat do textu


jestli na rozdeleni datasetu pouzit jenom Split Validation nebo Cross Validation - Cross Validation, do textu napsat, ze to bylo lepsi jak split a proc jsme to vybrali.

---------------------------------------------
Modely:
Naive Bayes
Generalized Linear Model
Logistic Regression
Fast Large Margin
Deep Learning
Decision Tree
Random Forest
Gradient Boosted Trees
Support Vector Machine
k-Nearest Neighbor (k-NN)
----------------------------------------------

Cross:
acc: 87.05 +- 4.9
precision: 87.432857143
recall: 86.885714286
F1 score: 87.158427041

Cross binning:
acc: 85.75 +- 2.36
precision: 86.08
recall: 85.718571429
F1: 85.898905529

Cross one-hot:
acc: 85.99 +- 4.92
precision:86.318571429 
recall: 85.788571429
F1: 86.052755368

Split:
precision: 87.21
recall: 85.998571429
F1 score: 86.600049321




Cross One-hot:

Analysis:

    Precision: Cross validation has slightly better precision (+0.22%).
    Recall: Cross validation also has a better recall (+0.89%).
    F1 Score: Cross validation shows a higher F1 score (+0.56%), indicating better balance between precision and recall.

Conclusion:

Cross Validation performs slightly better in all metrics (precision, recall, F1 score). Given that it also provides a more robust estimate of performance (since it evaluates the model on multiple data splits), it would be a better choice for your dataset. Therefore, I would recommend using Cross Validation in this case.

-----------------
Better Performance with Distance-Based Algorithms:

    Algorithms that rely on distance measures (e.g., k-nearest neighbors, support vector machines) can interpret binary features more effectively because one-hot encoding represents categorical variables in a multi-dimensional space. Without one-hot encoding, numeric values may distort the distance calculations.

Captures Non-Linearity in Models:

    In algorithms such as decision trees or gradient-boosted trees, one-hot encoding allows the model to capture complex interactions between categories. The model can decide which categories are more important, helping with interpretability and performance.
    
    Works Well with Linear Models:

    Linear models (e.g., logistic regression) benefit from one-hot encoding since it allows the model to weigh each category independently. This provides more flexibility and ensures that no artificial linear relationships are imposed by the encoding.
    
---------------------
Here’s a comparison of your model’s performance with and without binning based on the metrics you provided:
1. Accuracy:

    Without binning: 87.05% ± 4.9
    With binning: 85.75% ± 2.36
    Conclusion: The model without binning has a higher accuracy (87.05% vs. 85.75%) and slightly larger variance. This suggests the model without binning performs better in terms of accuracy, although its consistency is slightly lower.

2. Precision:

    Without binning: 87.43%
    With binning: 86.08%
    Conclusion: Precision is higher without binning, meaning the model without binning is better at minimizing false positives.

3. Recall:

    Without binning: 86.89%
    With binning: 85.72%
    Conclusion: The model without binning also has a slightly higher recall, meaning it’s better at identifying true positives.

4. F1 Score:

    Without binning: 87.16%
    With binning: 85.90%
    Conclusion: The F1 score, which balances precision and recall, is higher without binning. This indicates better overall performance in terms of classification quality when binning is not applied.

Key Takeaway:

    Without binning, your model shows better performance across all metrics (accuracy, precision, recall, and F1 score).
    With binning, the model performs slightly worse but is more consistent (lower variance in accuracy).

Recommendation:

    Based on the provided metrics, you should choose the model without binning, as it demonstrates superior performance overall, even though it has a slightly larger variance in accuracy.
    
-------------------------------------------
Here’s a comparison of your model’s performance without one-hot encoding and with one-hot encoding based on the metrics you provided:
1. Accuracy:

    Without one-hot encoding: 87.05% ± 4.9
    With one-hot encoding: 85.99% ± 4.92
    Conclusion: The model without one-hot encoding has a slightly higher accuracy (87.05% vs. 85.99%), indicating better performance in this aspect, though both models show similar variance.

2. Precision:

    Without one-hot encoding: 87.43%
    With one-hot encoding: 86.32%
    Conclusion: The precision is higher without one-hot encoding, meaning the model without it is better at minimizing false positives.

3. Recall:

    Without one-hot encoding: 86.89%
    With one-hot encoding: 85.79%
    Conclusion: The recall is slightly better without one-hot encoding, indicating that the model is better at identifying true positives without one-hot encoding.

4. F1 Score:

    Without one-hot encoding: 87.16%
    With one-hot encoding: 86.05%
    Conclusion: The F1 score is higher without one-hot encoding, which balances precision and recall. This suggests that overall, the model without one-hot encoding performs better in terms of classification quality.

Key Takeaway:

    Without one-hot encoding, your model performs slightly better across all metrics (accuracy, precision, recall, and F1 score).
    With one-hot encoding, the model has slightly lower performance but a comparable variance to the model without one-hot encoding.

Recommendation:

    Based on the provided metrics, the model without one-hot encoding performs better overall. However, if you're using models that typically benefit from one-hot encoding (e.g., linear or distance-based models), you may still want to consider it for other reasons like interpretability or handling categorical data properly.
