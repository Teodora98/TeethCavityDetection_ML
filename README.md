# Teeth Cavity Detection
Detection of teeth anomalies 

[![Python 3.7](https://img.shields.io/badge/python-3.7-blue.svg)](https://www.python.org/downloads/release/python-370/)

Keras implementation of VGG16 fine tuned model for hail damage detection.
------------




## Trained model
Trained Model Download ([Link](https://drive.google.com/file/d/1FYmIUx9zbJ4QnUsQueO6O48U0SOfx93I/view?usp=sharing))

## Dataset  

### Official Dataset
Images Located in :  ([Link](https://drive.google.com/drive/folders/1CJsVA3ggEg0lE_oS1dnnIE1OxWzOaeXV?usp=sharing))



## File hierarchy
Once you download pretrained model and dataset, please follow this project structure:
```
  
    |── requirements.txt                      Dependencies 
    |── NotebookTrain.ipynb                   Training model
    |── NotebookPrediction.ipynb              Prediction script
```    

## Requirements
3 <= Python <= 3.7 (Please note that python serialization algorithm is changed from v3.6+)



#### Example Data generation command:
```
python data_generation.py -config config/generator.json
```



## Validation performance 
```
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.465
 Average Precision  (AP) @[ IoU=0.50      | area=   all | maxDets=100 ] = 0.811
 Average Precision  (AP) @[ IoU=0.75      | area=   all | maxDets=100 ] = 0.499
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = -1.000
 Average Precision  (AP) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.437
 Average Precision  (AP) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.474
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=  1 ] = 0.353
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets= 10 ] = 0.617
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=   all | maxDets=100 ] = 0.623
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= small | maxDets=100 ] = -1.000
 Average Recall     (AR) @[ IoU=0.50:0.95 | area=medium | maxDets=100 ] = 0.617
 Average Recall     (AR) @[ IoU=0.50:0.95 | area= large | maxDets=100 ] = 0.618
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



##  Conclusion
Both models are with roughly the same performance : 
* Architecture I(OD Based) showed some better results on recall
* Architecture II (Classification-based) showed some better results on precision

Architecture I (Object detection approach) with adding the synthetization and the  classes "Damage", "Looks Like Damage" and "Bg" is more production ready approach because : 
* It’s fast 
* Capture more spatial information
* I strongly believe that it can be trained even better in order to extract the maximum performance

It can be further more improved with : 
* Label More data
* Synthetize with more and different effects
* Use faster architectures
* Architecture that solves class imbalance problem

Architecture II works well and it’s a great approach but it’s recommended only for high speed development 
*  It will cost a lot in production
* Unable to estimate execution time
    * Speed is dependent on number of detected objects


## Team Members


