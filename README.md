# PixelRec: A Large-Scale Video Cover Dataset for Image Recommendation


# Dataset


Download link: coming soon

We also provide an auto-downloader to make each image easy to download and available permanently. 

# Benchmark
## Environments
```
Pytorch==1.12.1
cudatoolkit==11.2.1
sklearn==1.2.0
python==3.9.12
```
## Dataset Preparation
Run `get_lmdb.py` to get lmdb database for easier image loading. Run `get_behaviour.py` to convert the user-item pairs into item sequences format.
## Run Experiments
Run `train.py` for pre-training and transferring. Run `test.py` for testing.

# Leaderboard
coming soon.
