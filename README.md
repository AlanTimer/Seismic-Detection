[![](https://img.shields.io/badge/license-GPL--3.0-blue)](https://www.gnu.org/licenses/)
[![](https://img.shields.io/badge/Python-3.7.2-green)](https://www.python.org/downloads/release/python-372/)

# CrowdQuake: A Networked System of Low-Cost Sensors for Earthquake Detection via Deep Learning

<!---This is a Python3 implementation of Convolutional Recurrent Neural Networks for the task of binary classification of seismic detection, as described in our paper.--> 

## Overview

Here we provide the implementation of Artificial Neural Network (ANN) and Convolutional Recurrent Neural Network (CRNN) used in our paper. The repository is organised as follows:
* ```Processing/```contains the codes for processing the data.
* ```Models/``` contains the implementation of the ANN and CRNN models.


## Requirements
<!---*tensorflow (gpu-1.14)--> 
<!---* Keras (2.2.4)--> 
<!---* scikit-learn (0.21.2)--> 
<!---* pandas (0.24.1)--> 
<!---* numpy (1.16.1)--> 
<!---* obspy (1.1.1)--> 
<!---* matplotlib (3.0.3)--> 


[![](https://img.shields.io/badge/tensorflow-gpu--1.14-green)](https://www.tensorflow.org/)
[![](https://img.shields.io/badge/Keras-2.2.4-green)](https://keras.io/)
[![](https://img.shields.io/badge/scikit--learn-0.21.2-green)](https://scikit-learn.org/stable/index.html)
[![](https://img.shields.io/badge/pandas-0.24.1-green)](https://pandas.pydata.org/pandas-docs/stable/index.html)
[![](https://img.shields.io/badge/numpy-1.16.1-green)](https://numpy.org/devdocs/index.html)
[![](https://img.shields.io/badge/obspy-1.1.1-green)](https://docs.obspy.org/)
[![](https://img.shields.io/badge/matplotlib-3.0.3-green)](https://matplotlib.org/3.0.3/index.html)

```bash
$ pip install -r requirements.txt
```

In addition, CUDA 10.0 and cuDNN 7.4 have been used.


## Data
The dataset contains two classes of three-component time-series acceleration waveforms:
1. Earthquake: Downloaded from National Research Institute for Earth Science and Disaster Resilience (NIED).
  [![](https://img.shields.io/badge/Earthquake-Download-yellow)](http://www.kyoshin.bosai.go.jp/kyoshin/data/index_en.html)

> Note: In our paper, we use two earthquake datasets. 
> 1. 2299 K-NET records of Japan earthquakes from Jan. 1st 1996 to May 31th 2019, each of whose x-axis component peak ground acceleration (PGA) is greater than 0.1 gravity (g). 
> 2. 8980 K-NET records of Japan earthquakes from Jan. 1st 1996 to May 31th 2019, each of whose x-axis component PGA is greater than 0.05 g.

> To download the earthquake data for reproducing our results, please visit [NIED](http://www.kyoshin.bosai.go.jp/kyoshin/data/index_en.html), sign in, and select Network -- K-NET; Peak acceleration -- from 100 to 10000. Due to the limitation of the website, please select Recording start time annually.

2. Non-Earthquake: Background noise of the low-cost sensors measured in several environments and various human activities recorded by our low-cost sensors.
  [![](https://img.shields.io/badge/Non--Earthquake-Download-yellow)](https://drive.google.com/file/d/11sivVlx7z-cBwjBWPNY9D2Wmfv-FY-CM/view?usp=sharing)

You can also use your own data, but the data should contain three-component time-series accelerations.

## Models

You can choose between the following models: 
* ANN: A multi-layer perceptron with three input features (IQR,ZC,and CAV) and a hidden layer of 5 neurons. See more details in our paper or [MyShake](https://advances.sciencemag.org/content/2/2/e1501055) paper.
<!---* CNN--> 
* CRNN: A combination of Convolutional Neural Network (CNN) and Recurrent Neural Network (RNN). See more details in our paper.

## Running the code
1. Download the data as described above.
2. Run ```Processing/processing.py``` to process the raw data.
3. Run ```Models/ANN.py``` and ```Models/CRNN.py``` to train and test two models.
4. ```Models/ANN_kfold.py``` and ```Models/CRNN_kfold.py``` can be used for k-fold cross validation.
> Note: 
  1.To reproduce our results, please download the same set of data as we used in the paper.
  
  2.For different test cases, please change the setting as described in each code file.



<!---## Cite--> 

<!---Please cite our paper if you use this code in your own work:--> 
