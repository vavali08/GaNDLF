# deep-semantic-seg

## Name candidates

- DeepSAGE: Deep SemAntic seGmEntation

## Installation

### Prerequisites

- Python3 with a preference for [conda](https://www.anaconda.com/)
- [CUDA](https://developer.nvidia.com/cuda-download) and a compatible [cuDNN](https://developer.nvidia.com/cudnn) installed system-wide

### Instructions

```powershell
conda create -p ./venv python=3.6.5 -y
conda activate ./venv
conda install pytorch torchvision cudatoolkit=10.2 -c pytorch -y # install according to your cuda version https://pytorch.org/get-started/locally/
pip install -e .
```

## To Do

- Consistent data I/O in a separate module so that this can be expanded for different tasks
- Generic multi-class segmentation support
- Data augmentation using `torchio`
- Ability to change [interpolation type](https://torchio.readthedocs.io/transforms/transforms.html?highlight=interpolation#interpolation) from config file
- Separate the training route into a separate function that takes the training + validation data and parameters as pickled objects from the main function
- Separate training code to make training more efficient for multi-fold training. Can possibly use https://schedule.readthedocs.io/en/stable/
- Single entry point for user (for both training and testing)
- Add more models that could potentially handle sparse data better
- Put as many defaults as possible for different training/testing options in case the user passes bad argument in config file
- Put CLI parameter parsing as a separate class for modularity and readability and this can be used by both the single interface for both training and testing
- Put downsampling as a parameter instead of hard-coding to 4