# Hybrid Architecture Pipeline for Cursive Handwriting Recognition

##Description:

This project is based on a hybrid architecture that utilizes two different state-of-the-art models

[**Segmentation Model**](https://drive.google.com/drive/folders/1tgRiiQk3793rexpa0fjNa0f21RnScOkv?usp=share_link): Developed by Harald Scheidl

[**Recognition Model (AttentionHTR)**](https://drive.google.com/file/d/1dXTJC57QcrZLjVDKRiqwx6s37Q6_oZxq/view?usp=share_link
): Developed by Ekta Vats and Dmitrijs Kass

By combining these two models, this project aims to achieve improved performance in cursive handwriting recognition. The segmentation model is responsible for identifying and segmenting individual words in the cursive text, while the recognition model is responsible for recognizing the characters within each segmented word.

## How to Run

### Prerequisites

#### Install all the required dependencies:

pip install -r requirements.txt

### Model Download

#### Download the necessary models:

* Segmentation Model (.json and weights files)
* Recognition Model (AttentionHTR file)

### Model Placement

* Create a folder named model and place the downloaded segmentation model files (.json and weights) inside it.

* Create a folder named models and place the downloaded recognition model (AttentionHTR) file inside it.

### Execution

* Run the provided Jupyter Notebook file (ipynb) to execute the pipeline.
* Algorithm for Sorting Bounding Boxes in Correct Order
* The algorithm ensures that the correct bounding boxes of the words are fed into the recognition model. This is achieved by:

## Sorting all bounding boxes from top to bottom and left to right.

* Saving the bounding box coordinates with the highest ymin and ymax (height coordinates).

* Iterating over other bounding boxes and subtracting the height (ymin) of the current bounding box from the saved ymin.

* If the difference is less than the difference between the saved ymax and ymin, then the current bounding box is considered to be part of the same line as the saved bounding box.

* If the condition fails, the saved ymin and ymax are updated, indicating that a new line has been encountered.

* The list of bounding boxes for the previous line is emptied, and a new list is created for the current line.

This process ensures that the bounding boxes are sorted in the correct order for feeding into the recognition model.

## Results

### The output of the pipeline consists of:

**Segmentation model output**: This includes the identified and segmented words in the cursive text.

<img width="592" alt="image" src="https://github.com/JeethuSrini/HybridCursiveRecognition/assets/85613102/f4995bef-6ebd-4021-b71e-b5ab1bc10f3a">


<br />
**Recognition model output**: This includes the recognized characters within each segmented word.

<img width="409" alt="image" src="https://github.com/JeethuSrini/HybridCursiveRecognition/assets/85613102/8ca49b85-dca2-484c-9423-ed0518b0a9e6">


## Conclusion

This project demonstrates the effectiveness of using a hybrid architecture to improve cursive handwriting recognition. By combining two state-of-the-art models, the pipeline achieves improved performance compared to other available models.
