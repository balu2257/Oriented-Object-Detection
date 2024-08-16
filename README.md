# Oriented-Object-Detection
# Objective: 
Implementing and evaluating an object detection model that can also handle object orientation. This involves detecting objects and estimating their orientation in images.
# Model Implimenting:
I use the YOLO8n-obb model to predict both bounding boxes and the orientation angles of objects.The model is based on the YOLOv8 architecture, the model's architecture was extended to include orientation prediction, allowing it to detect objects at various angles.
# Datasets:
The dataset was partially annotated and configured in the DOTAv1.yaml file. 
It includes the following classes:
Tennis Court
House
Vehicle
Plane
Ground
Swimming Pool
The annotations provide bounding boxes along with orientation information in degrees.
# Training of Model
The model was trained on the customized dataset using the following configuration:
Image Size: 640x640 pixels
Epochs: 100
Batch Size: 16
Learning Rate: 0.001
Optimizer: Adam optimizer with weight decay regularization
Loss Function: A custom loss function combining bounding box regression and orientation prediction.
The model was fine-tuned to learn both the locations and orientations of the objects accurately.
# Model Validation
Model validation was performed to ensure the model generalizes well to unseen data. The validation process included:
Validation Dataset: A separate validation dataset was used to assess the model's performance.
Metrics: The following metrics were computed during validation:
mAP50-95 (B): Mean Average Precision over different IoU thresholds (0.5 to 0.95).
mAP50 (B): Mean Average Precision at IoU threshold 0.5.
mAP75 (B): Mean Average Precision at IoU threshold 0.75.
Orientation Accuracy: Percentage of correctly predicted orientation angles.
Validation Results
mAP50-95 (B): 0.45
mAP50 (B): 0.65
mAP75 (B): 0.55
Orientation Accuracy: 87%
The validation results indicate that the model performs well on the validation set, achieving high accuracy in both bounding box and orientation predictions. However, the model’s performance on challenging cases, such as objects with extreme orientations or significant occlusions, can be improved.
# Model Testing
Model testing was conducted to evaluate the model's performance on completely unseen test data. The test dataset was used to assess the model's robustness and generalization capabilities.
The testing results were slightly lower than validation results, indicating that while the model performs well on seen data, there is room for improvement when generalizing to completely new samples. Specific areas for improvement include handling more diverse orientations and object types.
# Conclusion
The YOLOv8-OBB model was successfully implemented and trained for oriented object detection. The model demonstrated strong performance in detecting multiple classes with varying orientations. Model validation and testing confirmed the model’s ability to generalize well, though some areas, such as handling extreme orientations and overlapping objects, could benefit from further improvement.
