# cv_project

# Abstract
Reliable road obstacle identification is a critical requirement for the safe operation of autonomous driving systems. Traditional object detection methods often struggle to recognize unexpected or unknown obstacles, as they are typically limited to predefined categories. The ability to detect obstacles beyond known classes, particularly in dynamic and complex environments, is essential for the safety of autonomous vehicles. Recent advancements in semantic segmentation, anomaly detection, and uncertainty quantification offer new avenues to improve detection accuracy and reliability, enabling systems to recognize both known and unknown road obstacles. Such uncertainty-aware methods provide formal statistical guarantees on the reliability of predictions, a crucial aspect for ensuring safe and robust decision-making in real-world driving conditions.

# Methodology
The ability to detect both know objects and unexpected anomalies is crucial in autonomous driving systems, where unpredictable elements can pose serious safety risk. The goal of this project was to develop a system capable of performing semantic segmentation of road scene while also detecting unknown or anomalous object, things that don’t belong to the typical road classes. The system also had to provide an uncertainty estimate for each prediction, helping assess how confident the model was. 
We worked with several datasets: Cityscapes, LostAndFound, Road Anomaly and Fishyscapes. Applying the same transformation to the images and masks and converting the annotations into a format suitable for multi-label training. We trained DeepLabV3 model to recognize major road scene classes plus a special object class. The initial training was done on Cityscapes, after we fine-tuned the model on the LostAndFound dataset to specialized it in detecting unusual obstacles on the road. We added a mechanism to compute how uncertain the model is about each pixel, this helped identify areas where the model is unfamiliar whit what it sees. We used also a calibration set to compute a statistical threshold: if a pixel’s uncertainty exceeds this threshold, it’s considered anomalous. We tested the system on new images, including real and synthetic anomalies. In the end we computed performance metrics in order to analyze the model’s strengths and limitations.

# Datasets
Cityscapes: <br>
    This dataset was taken from its official website: (https://www.cityscapes-dataset.com/downloads/) <br>
    the version that was used was the 11gb with Fine annotation masks. <br>
    Dataset link: https://drive.google.com/drive/folders/1f8Pxl8iGoRym0cagDvaweP3lbBNO2tuk?usp=share_link <br>
    
LostAndFound: <br>
    This dataset was taken from its official website: https://wwwlehre.dhbw-stuttgart.de/~sgehrig/lostAndFoundDataset/index.html <br>
    the version that was used was the 6gb with Coarse annotation masks. <br>
    Dataset link: https://drive.google.com/drive/folders/1P1EWaOmNgNlVIr1V1hFfNMq2CLRtzpRE?usp=sharing <br>

RoadAnomaly: <br>
    This dataset was taken from its official website: https://www.epfl.ch/labs/cvlab/data/road-anomaly/ <br>
    Dataset link: https://drive.google.com/drive/folders/1frfml1PU7hENftQ-cvY-gx0QYi0OcSnQ?usp=sharing <br>

FishyScapes: <br>
    This dataset was created following its official website's guidelines since it is no longer available for download. <br>
    Official website: https://fishyscapes.com <br>
    Dataset Link: https://drive.google.com/drive/folders/1n0F6MufU0YPJ66ixIrYGLRAyNmvRXxA1?usp=sharing <br>

# References
"Chihiro Noguchi, Toshiaki Ohgushi, Masao Yamanaka. Road Obstacle Detection based on​ Unknown Objectness Scores" <br>
"Luca Mossina, Joseba Daimau, Lèo Andrèol, Conformal Semantic Image Segmentation: Post-hoc Quantification of Predictive Uncertainty​" <br>
"Liang-Chieh,Chen, George Papandreou, Florian Schroff, Hartwig Adam, Rethinking Atrous Convolution for Semantic Image Segmantion​" <br>
"Anastasios N. Angelopoulos and Stephen Bates, A Gentle Introduction to Conformal Prediction and Distribution-Free Uncertainty Quantification" <br>
