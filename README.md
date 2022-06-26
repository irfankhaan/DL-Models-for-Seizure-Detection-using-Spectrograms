## Deep Learning Models for Seizure Detection using Spectrograms

This repositories contains a series of notebooks for binary classification of seizure and non-seizure EEG signals in the Temple University Hospital (TUH) EEG dataset. 
The EEG signals are first converted into spectrogram images and deep learning models are then used to classify these images.

The dataset is publicly available [here](https://isip.piconepress.com/projects/tuh_eeg/html/downloads.shtml) (Version: 1.5.1).


### Libraries used
* [MNE](https://mne.tools/stable/index.html#)
* [Numpy](https://numpy.org/)
* [Matplotlib](https://matplotlib.org/)
* [TensorFLow](https://www.tensorflow.org/)
* [Keras](https://keras.io/)
* [livelossplot](https://pypi.org/project/livelossplot/)


### Results

**Model** | **Precision**| **Recall** | **AUC** | **Accuracy** | **Number of parameters (in million)**
---|---|---|---|---|---
*Base CNN Model* | 91.1 | 93.5 | 97.9 | 90.9 | 3.94
*VGG16* | 80.3 | 95.6 | 96.3 | 88.5 | 138.4
*ResNet* | 86.4 | 95.6 | 97.2 | 90.3 | 25.6
*DenseNet* | 88.6 | 94.1 | 97.3 | 92.6 | 8.1
*Inception* | 85.3 | 94.9 | 95.7 | 88.8 | 23.9


### Preprocessing and Spectrogram generation

- Only files with generalized seizure (gnsz) and background (bckg) events are used in this repo.
- Seizure events are split from non-seizure events and stored as separate files.
- All the files have 21 common channels and sampling rate of 256 Hz.
- 4th order Butterworth filter from 0.5 Hz to 50 Hz is used for filtering the EEG signal. 
- Epochs of 3 seconds of the EEG signal are used to generate spectrograms.


#### Spectrograms fed to the Deep Learning networks 
![Spectrograms](https://github.com/irfankhaan/DL-Models-for-Seizure-Detection-using-Spectrograms/blob/master/image-spectrograms.png)

#### 3D visualization of Spectrograms 
![3D Spectrogram](https://github.com/irfankhaan/DL-Models-for-Seizure-Detection-using-Spectrograms/blob/master/image-specgrams-3d.png)


## Citation
If you find this work useful, please cite

```
@INPROCEEDINGS{9800802,  
    author={Khan, Mohd Maaz and Mabood Khan, Irfan and Farooq, Omar},  
    booktitle={2022 10th International Symposium on Digital Forensics and Security (ISDFS)},   
    title={Deep Learning based Lightweight Model for Seizure Detection using Spectrogram Images},   
    year={2022},  
    pages={1-6},  
    doi={10.1109/ISDFS55398.2022.9800802}}
}
```