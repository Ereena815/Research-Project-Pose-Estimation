# Real-Time Posture Correction System (RTPCS)

This document presents the comprehensive development and evaluation of the RTPCS aimed at addressing the critical challenge of real-time posture correction during manual lifting. The proposed system integrates computer vision techniques, sequential data collection, an LSTM-based posture classification model, risk analysis framework, and a basic web component for interactive user feedback. This submission details the scope and requirements, provides insights into the prioritization process, outlines the development plan with technology stack, includes code snippets and diagrams, and evaluates the performance and functionality of the developed system. The iterative and incremental nature of the development process, along with future considerations for system enhancement, is discussed.

## Scope and Requirements

### Real-Time Pose Detection:

- Detect and display key landmarks in real-time using computer vision.
- Use the MediaPipe library for holistic pose detection.

### Sequential Data Collection:

- Record sequential data representing keypoint values during manual lifting.
- Implement logic to store this data for training the LSTM model.

### LSTM-Based Posture Classification:

- Develop an LSTM neural network to classify keypoint sequences into different postures.
- Train the model using the collected dataset.

### Risk Analysis Framework:

- Implement a simple risk analysis framework to categorize postures based on risk levels.
- Display risk levels for each detected posture.

### Web Component:

- Develop a basic web interface to visualize real-time posture feedback.
- Display the detected posture, risk level, and provide any necessary corrective instructions.

## Development 

### Technology Stack:

-	Python: Core programming language for overall development.
-	TensorFlow and Keras: Used for building, training, and integrating the LSTM model.
-	Flask: Web framework for developing the basic web component.
-	MediaPipe and OpenCV: Libraries for real-time pose detection.

### System Architecture: 

The RTPCS integrates computer vision, and an LSTM-based AI model to monitor and correct employees' postures during manual lifting. A web cam captures real-time data, and the computer vision system processes this information for posture analysis. The LSTM model, trained on a diverse dataset, evaluates the data to identify correct or incorrect postures.

 ![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/2519f2de-2dfd-441a-9f23-b26235f91f78)

### Workflow:

1.	Real Time Pose Estimation
The initial part of the implementation involves real-time pose estimation using the MediaPipe Holistic model. This is achieved by capturing video frames, processing them through the model, and visualizing the detected landmarks on the face, pose, and hands.
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/d199b1e8-7d54-4a2c-930f-dc6f93758b2d)
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/b3f77b37-b695-4fc3-9361-8ae3ce4e9a09)
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/8e979acb-def8-48f0-9681-feb23125c0e8)

2.	Data Collection for Training
To create a robust dataset for training the posture classification model, the code captures real-time frames, extracts keypoint values using the MediaPipe model, and saves the keypoints to structured folders. This dataset includes different actions and sequences, allowing for a diverse training set.
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/5b25340f-012b-45a5-a451-21f36b604f1d)

3.	LSTM Neural Network
 ![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/b89ba489-48b3-4032-bc08-effc7bf5477f)

The core of the implementation is the LSTM-based neural network. The model is designed to learn temporal patterns from the sequence of keypoint values. It consists of multiple LSTM layers followed by dense layers. The model is compiled with the Adam optimizer and categorical crossentropy loss. The training process involves iterating over the dataset for a specified number of epochs. An early stopping callback is implemented, monitoring categorical accuracy and stopping training once a predefined threshold is reached. This ensures that the model does not overfit the training data.

4.	Evaluation and Real-time Testing
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/fefd86db-b9be-42e4-8234-a5a5921b9d4f)

The trained model is evaluated using a test set. The evaluation includes calculating a confusion matrix and accuracy score, providing insights into the model's performance on unseen data.
The final part demonstrates the real-time application of the trained model. The code captures live video frames, performs pose estimation, and feeds the sequence of keypoints into the LSTM model for action prediction. The predicted actions are displayed on the screen, along with a visual representation of the model's confidence in its predictions.
By focusing on these crucial aspects, the implementation section provides a concise yet comprehensive overview of the code's workflow, from real-time pose estimation to LSTM-based posture classification.
![image](https://github.com/Ereena815/Research-Project-Pose-Estimation/assets/85027159/8e12645e-6775-4c73-b697-aab41c303d4d)

### Demonstration Video Link: 
https://www.youtube.com/watch?v=yHCX1u5-rrk

## Evaluation 

### Performance and Functionality:

-	The MVP successfully achieved real-time posture correction, demonstrating effective integration of computer vision, an LSTM model, and a risk analysis module.
-	Risk-based interventions improved adaptability and addressed varying degrees of risk severity.
-	It provided intuitive real-time feedback, contributing to user engagement.

### Testing and Scientific Evidence:

- Rigorous testing involved simulated manual lifting scenarios, validating the accuracy of posture classification and the effectiveness of interventions.
- User testing provided valuable feedback on the web interface and overall system usability.
- Scientific evidence showcased the system's ability to promptly identify and correct improper postures.

### Future Iterations and Reflection:

-	Future iterations will focus on refining risk analysis algorithms for more precise intervention strategies.
-	User feedback will inform updates to the web component, enhancing user interaction and experience.
-	An extensive data collection will be performed.
-	Lessons learned from MVP development, including the balance between core functionalities and completeness, will guide the overall development roadmap.


