# Reproduction of an existing publication

Two examples where I attempted to 
**reproduce results from publications analysing cardiotocograph data**:
* One with **no code available**, Daydulo et al. 2023 [[GitHub respository]](https://github.com/birth-outcomes/ctg_exploratory)
* One with **MATLAB code available**, Boudet et al. 2020 [[GitHub repository]](https://github.com/birth-outcomes/fhrma_python)

## Context

* Working with Mike Allen, who was hoping to submit new bid which broadly involves using cardiotograph data - alongside other maternal and labour information - to predict birth outcomes.
* We had never worked with this type of data before, so I focussed on exploring existing approaches, and reproducing some results

## Cardiotocograph data

CTG is a continuous recording of the **fetal heart rate** and **maternal uterine contractions** during labour.
* **Cardio**: Fetal heartbeat
* **Toco:** Uterine contractions
* **Graphy:** Drawing representing recording

![CTG example](img/ctg.jpg 'CTG')
*CTG image from [source](https://upload.wikimedia.org/wikipedia/commons/b/b6/Cardiotocography.jpg).*

![CTG output example](img/ctg_output.jpg 'CTG output')
*CTG output image from [source](https://commons.wikimedia.org/wiki/File:CTG_Output.jpg#/media/File:CTG_Output.jpg).*

A combination of **abnormalities** in the CTG indicate an increased likelihood of fetal distress - these include:
* **Baseline fetal heart rate outside normal range** (110-160bpm)
* **Baseline variability <5bpm** (beat-to-beat changes in 1 minute) 
* **Reduced or absent accelerations** (periodic, transient increases >15bpm for >15sec)
* **Presence of decelerations**(periodic, transient decreases in FHR categorised in relation to UC)

There are several different ways to process this type of data before using it in a machine learning model - I worked to reproduce a few examples.

## Reproducing Daydulo et al. 2023

This paper analysed an **open dataset of CTG data** using MATLAB but with **no code shared**. I attempted to **recreate three key sections** of the paper...

### (1) Data cleaning and augmentation

Figure 5 from Daydulo et al. 2023:

![Daydulo cleaning](img/daydulo_figure5.png)

My replication:

![My cleaning](img/daydulo_figure5_replication.png)

### (2) Continuous wavelet transformation (CWT)

This is a type of transformation where you use a wavelet (small wave) to find the frequencies present in a signal at different scales (based on similarity to the wavelet). This is used to produce a 2D colour image representing the signal called a scaleogram.

X axis is time, Y axis relates to the frequencies present.

Figure 6 from Daydulo et al. 2023:

![Daydulo CWT](img/daydulo_figure6.png)

My replication:

![My CWT](img/daydulo_figure6_replication.png)

### (3) Model

They then use ResNet-50, a pre-trained convolutional neural network, to classify the images as abnormal (fetal distress) or not.

Figure 9a from Daydulo et al. 2023:

![Daydulo ResNet50](img/daydulo_figure9a.png)

My replication:

![My ResNet50](img/daydulo_resnet_1.png)
![My ResNet50](img/daydulo_resnet_2.png)

**Comments:**

* Not a perfect paper (flawed augmentation, and suspicious accuracy and loss curves).
* Was able to overfit model but couldn't improve.
* This was exploratory work that was part of helping us understand concepts and potential methods we could use.
* Differs to formal reproducibility study, as planned for STARS (hence, no timings, etc).

## Replicating elements from MATLAB FHRMA package

Boudet et al. 2020 produced a publication implementing various published methods for identifying features in the fetal heart rate, like the baseline heart rate, accelerations and decelerations. They shared this as a **MATLAB package** with accompanying data:

![FHRMA package page](img/fhrma_page.png)

I worked through a few examples of methods, **converting MATLAB to Python** and attempting to get the same results, including:
* Importing and cleaning the data
* A method for baseline heart rate
* A method for baseline heart rate, accelerations and decelerations