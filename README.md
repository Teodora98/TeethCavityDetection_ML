<p align="center">
<img src="images/Teeth%20Cavity%20Detection.png" width=400)>
<br>
<h1 align="center">Dental Cavity Detection</h1>

<p align="center">Detection of teeth anomalies </p>

<p align="center">
<a href="https://www.python.org/downloads/release/python-370/" target="_blank">
  <img src="https://img.shields.io/badge/python-3.7-blue.svg">
</a>
  
Keras implementation of VGG16 fine tuned model for hail damage detection.
------------

## Introduction :wave:
Dental caries or cavities, more commonly known as tooth decay, are caused by a breakdown of the tooth enamel. This breakdown is the result of bacteria on teeth that breakdown foods and produce acid that destroys tooth enamel and results in tooth decay. Early cavity detection can mean less damage, less pain & less hassle down the road. While preventing decay is always the primary goal, we understand that not everyone has perfect oral health all the time, so early detection & treatment are essential tools for preserving your beautiful smile! X-rays can show tooth decay, fillings and gum disease.

The goal of our project was to develop a model that can process a panoramic x ray image and can separate the teeth with caries from the healthy teeth. With this model we speed up the process of cavity detection, and we also enable patients to have access to these information  and be informed about their health.

## File github structure

#### Dataset  
We croppied individual teeth from 400 panoramic x-ray images, afther taht we were able to create 2 datasets we needed in order to train our model. One dataset contains healthy theeth and the other containts theeth with caries. <br>
You can find the datasets we used to train our model [here](https://drive.google.com/drive/folders/1CJsVA3ggEg0lE_oS1dnnIE1OxWzOaeXV?usp=sharing).

#### File hierarchy
Once you download pretrained model and dataset, please follow this project structure:
```
  
    |── requirements.txt                      Dependencies 
    |── NotebookTrain.ipynb                   Training model
    |── NotebookPrediction.ipynb              Prediction script
```    

#### Requirements
3 <= Python <= 3.7 (Please note that python serialization algorithm is changed from v3.6+)

#### Example Data generation command:
```
python data_generation.py -config config/generator.json
```

# Best Validation performance on Synthetized Dataset

|precision|recall|f1-score|support|
|---|---|---|---|
| 0.89     | 0.93     | 0.91  |      81|
| 0.92   |   0.89  |    0.90        |80|



# Time Benchmark 
  * ~0.1s Inference Time on GPU (Tesla K80) 
--------------------

# Classification
We use binary classifier (cavity/no cavity) on detected objects

## Phases of project implementation
### 📥 Phase 1: Dataset collection
### 💪 Phase 2: Training the model
To solve this problem, we used several pre-trained CNN models. The results are shown below:


| Model         | Epochs        | Loss  | Train Accuracy| Test Accuracy|      
| ------------- | ------------- | -------------| -------------| -------------|
| ResNet50   | 50          |10(-5)  | 97.00% | 89.00%|
| **VGG16 - Used Data Augumentation** | **80**  | **10(-5)** | **99.54%** | **90.68%**|
| MobileNetV2  | 100          |10(-5)  | 99.84% | 88.13%|

Best overall results were achieved with transfer-learning using pre-trained **VGG16** an re-train it on our data.

The learning curves for this model are shown in the figure below.
  
<img src="/images/Accuracy%20curve.png"/>
  
<p align="right">
<img src="/images/Loss%20curve.png"/>
 
During model training we used callback function for saving best modes weights. The best model weights can be download from this link ([Link](https://drive.google.com/file/d/1FYmIUx9zbJ4QnUsQueO6O48U0SOfx93I/view?usp=sharing))


### ✔️ Phase 3: Detection of cavity in panoramic x-rays
This part of the project is still under construction 👷‍♀️



##  Conclusion

## Future work
This model has a lot of potential for future implementation. We can develop it into a model that detects more than cavity, it can also detect hidden dental structures(wisdom teeth), bone loss and..??
This model can be implented into an aplication that will make it easier for dentist to keep a visual track of a patient theeth health, and make it easier for patients to consult with diffrents dentists.

## 👧 Team Members 💪

- Teodora Mladenovska
- Ana Angelova
- Tanja Ivkovska
- Mihaela Miova


