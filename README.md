Peer Group 8
Christian Mutabazi
Samuel Dushime
Raini Benaiah 
Insights from experiments and challenges

Raini:

Insights
    Training VS Validation 
Training accuracy: 72.80%
Validation accuracy: 66.50%
Training loss: 0.5354
Validation loss: 0.6011
    The model is learning well and generalizing data better with comparison with the previous values suggesting a slight improvement in the model. 
The model is experiencing a slight overfitting due to the gap between the training and validation accuracy. 
  Comparison between Christian’s Model and Raini’s Model
Raini’s  model performs significantly better than Christian’s in accuracy, recall, and generalization.
Christian’s model uses  L1 regularization which might have caused the low training accuracy (62%), making it harder for the model to learn.
Christian’s model struggles to correctly classify positives (low recall) and has lower overall performance.
Samuel’s model uses Nadam which is a variation of Adam that incorporates Nesterov Accelerated Gradient (NAG), which can improve convergence, however it might have  caused instability, leading to low validation accuracy (47%).
Raini’s model performs better in accuracy, precision, and overall generalization.

Challenges 
Fine-tuning Drop-out and Learning rate. I spent most of my time trying to change the values for the learning rate, Drop-out , patience, factor and epoch to ensure that the training and validation values for accuracy and loss have a minimal gap to avoid overfitting and underfitting.
Encountered overfitting and underfitting several times. Despite the several tuning of the hyper-parameters, most of the time I encountered overfitting.
Due to overfitting, most of the time the training loss was changing but for thevalidation loss kept on fluctuating making it difficult to fine-tune the hyperparameters.
 	Samuel 
	Insights:
Class Imbalance Reduces Recall: The model detects non-potable water well but struggles with potable water (recall = 0.39). Balancing the dataset using SMOTE or class weighting could improve this.
Overfitting is Present: The model performs well on training data but loses accuracy on validation data, suggesting overfitting. Adding Dropout layers or reducing L2 regularization could help.
Optimizer Choice Impacts Performance: Switching from Adam to Nadam showed some improvement, but fine-tuning the learning rate or using learning rate decay could further boost results.
Feature Engineering is Needed:  Simply scaling the data with StandardScaler may not be enough. Selecting important features or trying different scaling methods could improve predictions.
Model Complexity May Be Insufficient: A two-layer network (128, 64 neurons) may not extract enough information. Adding more layers or using LeakyReLU could enhance learning.
Challenges :
I faced challenges in optimizer selection, as switching from Adam to Nadam showed some improvement, but further tuning of the learning rate was needed.
low recall for class 1, meaning the model missed many actual potable water samples, making predictions unreliable for safe water classification.
I faced overfitting, as validation accuracy was lower than training accuracy, indicating the model performed well on training data but struggled with new data.
I faced class imbalance, leading to poor recall (0.39) for potable water. The model struggled to identify safe water correctly.
	
Comparison:
Among the three models, Raini Benaiah’s model (Adam + Dropout) achieved the highest accuracy (66%) and F1 score (64%), indicating a balanced performance. The dropout layers (0.3 and 0.2) likely helped reduce overfitting while maintaining good precision (67.52%) and recall (61.67%). Christian Mutabazi’s model (RMSprop + L1 Regularization) had the lowest accuracy (62%) and F1 score (53%), possibly due to weaker generalization despite using L1 regularization and dropout (0.1 per layer). my model (Nadam + L2 Regularization) showed competitive accuracy (66%), but had the lowest recall (39%), meaning it struggled to identify potable water correctly. While Nadam optimized convergence, the lack of dropout might have affected generalization. 
Overall, Benaiah’s model performed best in balancing accuracy, recall, and F1 score, while Mutabazi’s underperformed, and mine showed potential but required better recall handling.


	Christian:
	Insights
Precision and Recall: My model's precision (52%) and recall (39%) are relatively low. This means it struggles with both correctly identifying positive cases and minimizing false positives. Improving these metrics should be a priority for better overall performance.
Dropout Rate: I set my dropout rate at 0.1 for both layers. This might be too low, and increasing it could help prevent overfitting. A higher dropout rate would likely improve the model's generalization.
Optimizer: I’m using RMSprop, which is solid but might not be the best choice for my model. Experimenting with Adam or Nadam could speed up convergence and improve performance.
Regularization: I’m using L1 regularization, which might not be ideal for my dataset. Trying L2 regularization could help better balance model complexity and prevent overfitting.
	Challenges
Low Precision and Recall: These metrics indicate the model struggles to both identify positives correctly and avoid false positives. It's not doing great at either task.
Dropout Rate: With a dropout rate of only 0.1, the model may be overfitting to the training data, limiting its ability to generalize well to new data.
Optimizer Choice: While RMSprop works decently, it might not be the best fit for my model. I'm considering experimenting with Adam or Nadam to see if they improve training speed and results.
Regularization Method: L1 regularization forces some weights to zero, but it may not be ideal for my data. Switching to L2 regularization might prevent overfitting better while keeping the model more stable.
Comparison: Comparing my model to others, Raini's model performs best with higher precision (67.52%) and recall (61.67%) likely due to a stronger dropout rate (0.3/0.2) and the Adam optimizer. Samuel's model has good accuracy (66%) but lower precision and recall, possibly due to Nadam and L2 regularization. My model's accuracy is 62%, but lower precision (52%) and recall (39%) suggest that my choices of L1 regularization, RMSprop, and a lower dropout rate (0.1) might be limiting performance.


Summary Table: 


Train Instance
Engineer Name
Regularizer
Optimizer
Early Stopping
Dropout Rate
Accuracy
F1 Score
Recall
Precision
2797
Raini Benaiah
Drop Out
Adam
Yes
First Layer = 0.3
Second layer = 0.2
66.00
64.00
61.67
67.52


Christian Mutabazi
L1
RMSprop
Yes
First Layer =0.1
Second Layer = 0.1
0.62
0.53
0.54
0.52


Samuel Dushime
L2
Nadam
Yes
None 
0.66
0.47
0.39
0.58


     Presentation Video Link
       recorded video
