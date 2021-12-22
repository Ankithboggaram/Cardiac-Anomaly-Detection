
# Cardiac Anomaly Detection

Sudden Cardiac Arrest (SCA) is a devastating
heart abnormality which leads to millions of casualties per
year. Thus, early detection or prediction of SCA could save
human lives in a greater scale. 

In this work, we aim to
predict SCA before its occurrence and significant results
has been obtained using the proposed signal processing
methodology. Models were trained using a CNN, CNN +
Long Short Term Memory (LSTM) model and a Random
Forest Classifier.



## Methodology

We use PhysioNet’s MIT-BIH Arrhythmia
dataset for our experiment. The MIT-BIH Arrhythmia
Database contains 48 half-hour excerpts of twochannel
ambulatory ECG recordings. 

The dataset contains Electrocardiogram
waveform data and in order to pre-process this
data, we require specialized libraries to extract the information
required. We use the wfdb package for this
purpose.

```python
  pip install --upgrade wfdb
```
We then extract the label information using the specified
package and split the hour long excerpts into smaller
chunks.  

The dataset contains approximately
82,873 inputs after pre-processing. To detect these abnormalities,
we came up with 3 solutions:
- Random Forest Classifier
- Convolutional Neural Network
- CNN+LSTM model.  


## Hardware Estimation
 
We use Intel’s OpenVino Toolkit to perform the estimation.  

We estimate the performance of our models on various CPUs and GPUs.

- Intel Core i5-6500TE CPU
- Intel Core i7-8865UE CPU
- Intel Xeon Gold 6258R CPU
- Intel Xeon E3-1268L v5 CPU
- Intel Core i5-6500TE GPU
- Intel Atom x7-E3950 UP2 GPU

We use our own model which we converted into an OpenVino model for hardware estimation. The python scripts available by OpenVino helped us convert our models.

## Results
The CNN models were compressed
using quantisation. Our early results indicated 96% on
accuracy with approximately 33.16% reduction in size.
We propose to apply variable width quantisation and
retraining to further improve compression.  

Our primary objectives were to minimize
the memory footprint and propose a computationally
less intensive approach to detect cardiac anomalies.
Using Lightweight CNNs and a Random Forest classifier
presented the desired results.


## Future work

Implementing these models on a FPGA.

## Authors

- Anktih B V
- Aaptha B V
- Aryan Sharma
