# PixelRec: A Large-Scale Video Cover Dataset for Image Recommendation



# Dataset



### Interaction Data

Interactions can be downloaded from https://sandbox.zenodo.org/record/1166723, containing **Pixel200K**, **Pixel1M**, **Pixel8M** and **PixelRec**.

### Item Information Data

See  `dataset/item_info.csv` 

### Image Data

It will take us one week or two to make all the images public, here we first provide images used in **Pixel200K**, containing 96,282 images, they can be downloaded via https://sandbox.zenodo.org/record/1167935#.Y_rvqnZByUk 

The download link of all the images: coming soon.



We also provide image urls and an auto-downloader to permanently access and download related image data.  



The downloader: coming soon.



**!!! Please kindly note that the images we now provide are watermarked and the texts are truncated and randomly shuffled, we will  recover them after acceptance.** 



# Experiments



## Environments

```
Pytorch==1.10.2
cudatoolkit==11.2.1
python==3.9.7
```

See requirements.txt for other packages:
```python
pip install -r requirements.txt
```


## Run Baselines

To run the baselines:

- Download the interaction data and images.

- Generate lmdb database from the images:

```python
cd code && python generate_lmdb.py
```

- You can choose different `yaml` files to run different baselines, the `yaml` files are under folders `IDNet`, `PixelNet` ,`ViNet` and `overall`

To run IDNet, for example, run `SASRec` model on one card:

```python
python main.py --device 0 --config_file IDNet/sasrec.yaml overall/ID.yaml
```

Change the `IDNet/sasrec.yaml` to run other IDNet baselines.



To run PixelNet, for example, run `SASRec` model with `ViT` encoders on four cards:

```python
python main.py --device 0,1,2,3 --config_file PixelNet/sasrec.yaml overall/ViT.yaml
```

Change  `PixelNet/sasrec.yaml` to run other PixelNet baselines with `ViT` as item encoder,  change  `overall/ViT.yaml` to run `sasrec` model with other image encoders.



To run ViNet, e.g. run `VBPR` model on one card:

```python
python main.py --device 0 --config_file ViNet/vbpr.yaml
```

Change  `ViNet/vbpr.yaml` to run other ViNet



Note: you may need to modify some path in files under folders `ViNet` and `overall` and file `generate_lmdb.py` , depending on where you put the downloaded data.



# Leaderboard

coming soon.