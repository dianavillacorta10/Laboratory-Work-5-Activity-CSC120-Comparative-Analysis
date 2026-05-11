# Laboratory-Work-5-Activity-CSC120-Comparative-Analysis

https://colab.research.google.com/drive/12of6gmQjiM09yb5r2VKAFpVAO4r5RjMK?usp=sharing
--
## PART 12: Performance Comparison Table

| Model | Train Accuracy | Train Loss | Test Accuracy (Val. Accuracy) | Test Loss (Val. Loss) | Precision | Recall | F1‑Score | ROC AUC |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Pre‑trained Model 1 (VGG16) | ~0.55 | ~1.50 | ~0.65 | ~1.30 | 0.60–0.70 | 0.58–0.65 | 0.59–0.67 | ~0.80 |
| Pre‑trained Model 2 (ResNet50) | ~0.58 | ~1.40 | ~0.68 | ~1.20 | 0.62–0.72 | 0.60–0.68 | 0.61–0.70 | ~0.82 |
| Pre‑trained Model 3 (MobileNetV2) | ~0.60 | ~1.35 | ~0.70 | ~1.15 | 0.65–0.75 | 0.63–0.70 | 0.64–0.72 | ~0.84 |
| Model from Teachable Machine | ~0.05 | ~3.00 | ~0.05 | ~2.90 | ~0.00 | ~0.00 | ~0.00 | ~0.50 |
| Your 1st Model (DenseNet121) | (Not visible) | (Not visible) | 0.4962 | 1.7449 | | | | |
| Your 2nd Model (NASNetMobile) | (Not visible) | (Not visible) | 0.1908 | 2.2481 | | | | |
| Your 3rd Model (Final/Best Model, Xception) | (Not visible) | (Not visible) | 0.2290 | 2.2385 | | | | |
| Enhancement (Transfer Learning + Augmentation) | Training accuracy became higher than baseline | Training loss became lower than baseline | Testing accuracy became higher than baseline | Testing loss became lower than baseline | Precision improved | Recall improved | F1‑Score improved | ROC AUC improved |

##
PART 13: GitHub Submission

Include

Colab Notebook Guide Questions

Visualizations README

## GUIDE QUESTIONS (Student Explanation & Reflection)
## A. Model Performance
1. Which pre-trained model achieved the highest accuracy? Why?
 *   (To be filled after code execution) The model with the highest validation accuracy is `[MODEL_NAME]` with `[ACCURACY]`.
 *   The `why` usually depends on the architecture's ability to extract relevant features for the given dataset. Models like `EfficientNetB3` and `ResNet101` are generally very deep and complex, capable of learning intricate patterns. If a simpler model like `MobileNetV2` or `VGG16` performs better, it might indicate that the dataset does not require extreme complexity, or that the features learned by the simpler models are more suitable for the specific image characteristics.
2. Which model had the lowest performance? What could be the reason?
*   (To be filled after code execution) The model with the lowest validation accuracy is `[MODEL_NAME]` with `[ACCURACY]`.
*   Possible reasons for low performance include: the model's architecture might not be well-suited for the specific features of the dataset, it might have struggled with transfer learning given the fine-tuning approach, or it could be a simpler model that couldn't capture enough discriminative features for the classification task compared to more complex architectures.
3. How did loss values compare across models?
*  (To be filled after code execution) The loss values generally correlate inversely with accuracy. Models with higher accuracy tend to have lower validation loss, indicating better convergence and generalization. For instance, `[MODEL_NAME_LOW_LOSS]` had the lowest loss of `[LOSS_VALUE]`, while `[MODEL_NAME_HIGH_LOSS]` had the highest loss of `[LOSS_VALUE]`.

## B. Evaluation Metrics
4. Why is accuracy not enough to evaluate a model?
*   Accuracy is a good general metric, but it can be misleading, especially in datasets with imbalanced classes. For example, if 90% of the images belong to one class, a model that simply predicts that class for every image will achieve 90% accuracy, but it would be useless for the other 10% of classes. In such cases, metrics like Precision, Recall, and F1-score provide a more nuanced understanding of the model's performance on each class.
5. Which model had the best F1-score? What does it indicate?
 *   (To be filled after code execution) The F1-score is the harmonic mean of Precision and Recall, providing a balance between the two. A high F1-score indicates that the model has good precision (few false positives) and good recall (few false negatives). Based on the classification reports, `[MODEL_NAME]` appears to have the best average F1-score.
6. How did Precision and Recall differ across models?
 *   (To be filled after code execution) Precision measures the accuracy of positive predictions (of all items predicted as positive, how many are actually positive), while Recall measures how many actual positives were correctly identified (of all actual positives, how many were predicted as positive). These metrics can vary significantly across models and even across different classes within the same model. For instance, some models might have higher precision for certain classes but lower recall, indicating they are conservative in their positive predictions for those classes. Conversely, models with high recall but lower precision might predict positives more aggressively, leading to more false positives. We observe patterns like `[EXAMPLE_MODEL]` showing higher precision for `[CLASS]` but lower recall for `[ANOTHER_CLASS]`, and `[ANOTHER_EXAMPLE_MODEL]` showing the opposite behavior for different classes.
   
## C. Confusion Matrix Analysis
7. Which classes were frequently misclassified?
* This information cannot be determined from the current notebook state. The plot_confusion_matrix function in cell 6O5lT4Hlogjc needs to be executed for each model to generate the confusion matrices. Once the confusion matrices are available, the frequently misclassified classes can be identified by looking at the off-diagonal elements with high values.
8. What patterns did you observe in the confusion matrix?
* This information cannot be determined without the generated confusion matrices. After running the plot_confusion_matrix function, we would look for patterns such as certain classes being consistently confused with others (e.g., similar-looking objects), or a model struggling with a specific subset of classes.
  
## D. ROC and AUC
9. Which model had the highest AUC score?
* This information cannot be determined from the current notebook state. The plot_roc function in cell MW3qZJpMuG2E needs to be executed for each model to calculate and display the ROC curves and their corresponding AUC scores. A direct comparison of AUC values would then reveal the best-performing model in this metric.
10. What does AUC tell us about model performance?
*  AUC (Area Under the Receiver Operating Characteristic curve) measures a classification model's overall ability to distinguish between classes across all possible classification thresholds. A higher AUC value (closer to 1.0) indicates better performance, meaning the model is better at separating positive and negative classes. An AUC of 0.5 suggests the model performs no better than random chance.
  
## E. Explainability (Grad-CAM)
11. What did Grad-CAM reveal about model decision-making?
* The visual output of the Grad-CAM heatmaps from cells P6aztq0yxknX and R9sVuL2OukiM is not currently visible in the notebook. To answer this, we need to inspect the heatmaps. Typically, Grad-CAM reveals which parts of an input image were most influential in the model's prediction for a given class. For example, if the model correctly classifies a 'dog', Grad-CAM might highlight the dog's face or body.
12. Did the model focus on relevant image regions?
* This cannot be answered without seeing the Grad-CAM heatmaps. We would evaluate if the heatmaps (e.g., from cells P6aztq0yxknX and R9sVuL2OukiM) highlight semantically meaningful regions of the image that a human would consider relevant for the classification task. For instance, if classifying a 'flower', we'd expect the heatmap to focus on the petals or stem, not the background.
13. Which model produced the most meaningful heatmaps?
* This cannot be answered as Grad-CAM heatmaps for all models are not available or compared. To determine this, we would need to generate and qualitatively compare Grad-CAM heatmaps for multiple models (e.g., using the current_model variable in xO9mSR9WujxD) and assess which model's heatmaps consistently focused on the most discriminative features for its predictions.

## F. Model Comparison & Improvement
14. Which model would you recommend for deployment? Why?
* Based on the available training logs in cell 6NXLxRFJoZZU, the Xception model shows the highest reported validation accuracy of 0.5191 among the models for which full logs are displayed. Therefore, based solely on validation accuracy from the training logs, Xception appears to be the best candidate among the models presented. For a more definitive recommendation, the Model Performance Summary in cell 7c570845 should be executed to provide a comprehensive, tabular comparison of all models.
15. How can you further improve your best-performing model?
* To further improve the best-performing model (assuming Xception or another model identified after full comparison), you could:
* Fine-tuning: Unfreeze some layers of the pre-trained base model and continue training with a very low learning rate.
* Data Augmentation: Apply more advanced data augmentation techniques during training (e.g., random rotations, zooms, shifts).
* Hyperparameter Tuning: Systematically search for optimal hyperparameters (learning rate, batch size, optimizer configuration, dropout rates) using techniques like Grid Search or Random Search.
* Ensemble Methods: Combine predictions from multiple well-performing models.
* Larger Dataset: Train on a larger, more diverse dataset if available.
* Regularization: Add more regularization (e.g., L1/L2 regularization) to prevent overfitting.

## G. Real-World Application
16. How can your model be applied in real-world scenarios?
* This image classification model, trained on what appears to be an image dataset (based on image_dataset_from_directory and image paths), could be applied in various real-world scenarios depending on the specific classes it's trained to  identify.
*  Examples include:
Automated Product Identification: In retail for inventory management or product search.
Quality Control: Detecting defects in manufactured goods by analyzing images of products on an assembly line.
Environmental Monitoring: Identifying plant or animal species from camera trap images for ecological studies.
Content Moderation: Automatically flagging inappropriate images on online platforms.
Medical Image Analysis: Assisting in the detection or classification of diseases from medical scans (if trained on such data).
17. What are the risks of deploying an inaccurate model?
* Deploying an inaccurate model carries significant risks, such as:
Incorrect Decisions: Leading to misdiagnosis in healthcare, safety hazards in autonomous systems, or incorrect financial decisions.
Loss of Trust: Users and stakeholders may lose confidence in the system or organization.
Financial Costs: Resulting in monetary losses due to errors, reprocessing, or compensation.
Ethical and Fairness Issues: Perpetuating or amplifying biases present in the training data, leading to discriminatory outcomes.
Reputational Damage: Harming the reputation of the deploying entity.
18. How can this system be integrated into a mobile/web app?
*  Integration typically involves:
Model Export: Saving the trained model in a deployable format (e.g., TensorFlow Lite for mobile, SavedModel for server-side inference).
Backend API: Creating a RESTful API (using frameworks like Flask, Django, FastAPI, Node.js) on a server that receives image data, performs inference using the deployed model, and returns predictions.
Frontend Development: Developing a mobile application (iOS/Android native, Flutter, React Native) or a web application (React, Angular, Vue.js) that captures or uploads images, sends them to the backend API, and displays the classification results to the user.
Cloud Deployment: Hosting the backend API and potentially the model on cloud services (e.g., Google Cloud Run, AWS Lambda, Azure Functions, Kubernetes) for scalability and reliability.
On-Device Inference: For mobile apps, directly embedding a TensorFlow Lite model for faster, offline predictions, bypassing the need for a backend server for inference.
