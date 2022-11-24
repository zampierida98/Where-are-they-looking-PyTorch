# Where are they looking?

This repository contains an implementation of the "Where are they looking?" paper by A. Recasens*, A. Khosla*, C. Vondrick and A. Torralba.

## Introduction

A deep neural network-based approach for gaze-following automated using a SFD face detector.

## Installation

* [CUDA and Pytorch](https://stackoverflow.com/a/70509457)
* Additional libraries: debug :) or `pip install -r requirements.txt`

## Training

* First, download [pretrained Places365 AlexNet model](https://urlzs.com/ytKK3) and [GazeFollow Data](http://gazefollow.csail.mit.edu/download.html).

* Then run:
    ```
    python main.py --data_dir=../GazeFollowing/GazeFollowData/ --batch-size=64 --workers=8 --epochs=1 --verbose=True --printfreq=1
    ```

* Please check out `opts.py` for other parameter changing.

## Testing

* Adjust `checkpoint` variable in `modeltester.py` if you have your own saved model.

* Run:
    ```
    python modeltester.py --data_dir=../GazeFollowing/GazeFollowData/ --batch-size=64 --workers=8
    ```

## Inference on images

* First, download [s3fd_convert.7z](https://github.com/clcarwin/SFD_pytorch/releases/tag/v0.1) and extract the content to `../s3fd_convert.pth`.

* Place input images in `imgs`.

* Run:
    ```
    python modeltester_withssd.py
    ```

* Output images are in `outputs/imgs`.

## References

* sfzhang15's SFD detector is used for face detection (https://github.com/sfzhang15/SFD).
* Link to the NIPS 2015 paper from MIT: http://people.csail.mit.edu/khosla/papers/nips2015_recasens.pdf. Please cite them if you decide to use this project for your research.
* Original implementation (https://github.com/rohitgajawada/Where-are-they-looking-PyTorch).
