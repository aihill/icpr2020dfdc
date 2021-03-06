# Video Face Manipulation Detection Through Ensemble of CNNs
![](assets/faces_attention.png)

This is the official repository of **Video Face Manipulation Detection Through Ensemble of CNNs**,
submitted to [ICPR2020](https://www.micc.unifi.it/icpr2020/) and currently available on [arXiv](https://arxiv.org/abs/2004.07676).

We participate as **ISPL** team on [Kaggle Deepfake Detection Challenge](https://www.kaggle.com/c/deepfake-detection-challenge/).
With this implementation, we reached the 43rd position over 2116 teams (**top 2%**) on the [private leaderboard](https://www.kaggle.com/c/deepfake-detection-challenge/leaderboard).

This repository is currently under mantainance, feel free to notify us any lack by opening an issue.
## Getting started

### Prerequisites
- Install [conda](https://docs.conda.io/en/latest/miniconda.html)
- Create the `icpr2020` environment with *environment.yml*
```bash
$ conda env create -f environment.yml
$ conda activate icpr2020
```

### Dataset preprocessing
You need to preprocess dataset in order to index all the samples and extract faces. Just run the script [make_dataset.sh](scripts/make_dataset.sh)

```bash
$ ./scripts/make_dataset.sh
```

Please notice that we use only 32 frames per video. You can tweak easily tweak this parameter in [extract_faces.py](extract_faces.py)

### Train
In [train_all.sh](scripts/train_all.sh) you can find a comprehensive list of all the commands for training the models presented in the paper. 
Please refer to the comments into the script for hints on their usage.

### Test 
In [test_all.sh](scripts/test_all.sh) you can find a comprehensive list of all the commands for testing the models presented in the paper. 

#### Pretrained weights
We also provide pretrained weights for all the architectures presented in the paper. 
Please refer to this [Dropbox link](https://www.dropbox.com/sh/cesamx5ytd5j08c/AADG_eEmhskliMaT0Gbk-yHDa?dl=0).
Each directory is named `$NETWORK_$DATASET` where `$NETWORK` is the architecture name and `$DATASET` is the training dataset.
In each directory, you can find `bestval.pth` which are the best network weights according to the validation set.


Additionally, you can find notebooks for results computations in the [notebook](notebook) folder.

## Datasets
- [Facebook's DeepFake Detection Challenge (DFDC) train dataset](https://www.kaggle.com/c/deepfake-detection-challenge/data)
- [FaceForensics++](https://github.com/ondyari/FaceForensics/blob/master/dataset/README.md)

## References
- [EfficientNet PyTorch](https://github.com/lukemelas/EfficientNet-PyTorch)
- [Xception PyTorch](https://github.com/tstandley/Xception-PyTorch)

## Credits
[Image and Sound Processing Lab - Politecnico di Milano](http://ispl.deib.polimi.it/)
- Nicolò Bonettini
- Edoardo Daniele Cannas
- Sara Mandelli
- Luca Bondi
- Paolo Bestagini