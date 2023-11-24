# Hybrid Architecture Pipeline for Cursive Handwritting recognition

Description
This project is based on a hybrid architecture that utilizes two different state-of-the-art models:

Segmentation Model: Developed by Harald Scheidl

Recognition Model (AttentionHTR): Developed by Ekta Vats and Dmitrijs Kass

By combining these two models, this project aims to achieve improved performance in cursive handwriting recognition. The segmentation model is responsible for identifying and segmenting individual words in the cursive text, while the recognition model is responsible for recognizing the characters within each segmented word.

How to Run
Prerequisites

Install all the required dependencies:
Bash
pip install -r requirements.txt
Use code with caution. Learn more

Model Download

Download the necessary models:

Segmentation Model (.json and weights files)
Recognition Model (AttentionHTR file)
Model Placement

Create a folder named model and place the downloaded segmentation model files (.json and weights) inside it.

Create a folder named models and place the downloaded recognition model (AttentionHTR) file inside it.

Execution

Run the provided Jupyter Notebook file (ipynb) to execute the pipeline.
Algorithm for Sorting Bounding Boxes in Correct Order
The algorithm ensures that the correct bounding boxes of the words are fed into the recognition model. This is achieved by:

Sorting all bounding boxes according to their height.

Saving the coordinates of the bounding box with the highest xmin (width coordinate) and ymin (height coordinate).

Iterating over other bounding boxes and subtracting the height (ymin) of the current bounding box from the saved ymin.

If the difference is less than the difference between the saved ymax and ymin, then the current bounding box is considered to be part of the same line as the saved bounding box.

If the condition fails, then the saved ymin and ymax are updated, indicating that a new line has been encountered.

The list of bounding boxes for the previous line is emptied, and a new list is created for the current line.

This process ensures that the bounding boxes are sorted in the correct order for feeding into the recognition model.

Results
The output of the pipeline consists of:

Segmentation model output: This includes the identified and segmented words in the cursive text.

Recognition model output: This includes the recognized characters within each segmented word.

Conclusion
This project demonstrates the effectiveness of using a hybrid architecture to improve cursive handwriting recognition. By combining two state-of-the-art models, the pipeline achieves improved performance compared to other available models.
