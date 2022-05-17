
# Road pothole detection multinet

This repository contains instruction for the topic which I have selected as part of self case study on Deep learning using one of the state of art architecture multinet (see documentation [here](https://github.com/MarvinTeichmann/MultiNet)) to detect pothole in road.


# 1. Solution Description:

To solve this problem, I had implemented 2 Models each with by using Kitti segmentation road, only Indian dataset and by combining both the dataset.
  * Model 1: Implemented Model 1 on all the above mentioned datasets Kitti segmentation road.
  * Model 2: Implemented Model 2 on all the above mentioned datasets by computing custom anchor boxes using Dataset section 3 referenced in this wrok.

# 2. Dataset:
Dataset can be found from here [dataset pothole](https://drive.google.com/drive/folders/1vUmCvdW3-2lMrhsMbXdMWeLcEz__Ocuy) which consists of 4 filders for train images consisting of already annotated text files and images.

# 3.  Requirements

The code requires [Python 2.7](https://www.python.org/download/releases/2.7/), [Tensorflow 1.0](https://www.tensorflow.org/install/), as well as the following python libraries: 

* matplotlib
* numpy
* Pillow
* scipy
* runcython
* commentjson

Those modules can be installed using: `pip install numpy scipy pillow matplotlib runcython commentjson` or `pip install -r requirements.txt`.

# 4. Hardware:

Due to GPU limitations on my system, I implemented and trained all models in aws serveur.

# 5. Modifying Model & Train on your own data

The model is controlled by the file `hypes/multinet3.json`. This file points the code to the implementation of the submodels. The MultiNet code then loads all models provided and integrates the decoders into one neural network. To train on your own data, it should be enough to modify the hype files of the submodels. A good start will be the [KittiSeg](https://github.com/MarvinTeichmann/KittiSeg#kittiseg) model, which is very well documented.

```
    "models": {
        "segmentation" : "../submodules/KittiSeg/hypes/KittiSeg.json",
        "detection" : "path to json datset"
    },
```

