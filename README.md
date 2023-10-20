# Easy Instruction about how to install and use labelImg

## Install 

Install virtual environment and packages

``` shell
# Window OS and Python 3.9
python -m venv venv
.\venv\Scripts\activate
# Upgrade pip
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
# Install labelImg
pip install labelImg
```

## Setup directory

Create a folder structure same as below

```
├── data
    ├── images
    └── labels
```

Put all of your image in `images` directory. And create a `classes.txt` contain all class you want to label. Example of `classes.txt` as below

``` txt
dog
cat
pig
```

Put `classes.txt` in 2 place, in `labels` directory and same level as `labels` directory

Full structure of workspace as below

```
├── data
    ├── images
    │   ├── img1.jpg
    │   ├── img2.jpg
    │   └── ...
    ├── labels
    │   └── classes.txt
    └── classes.txt
```

## Run labelImg

Run labelImg with

``` shell
# labelImg [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
labelImg .\data\images\ .\data\classes.txt
```

On GUI of labelImg: 

- `File -> Change Save Dir -> (save label directory)`
- Choose `YOLO` format on the left tray

Next and previous image with `D -> A`

Label with `W`

Delete `.\data\classes.txt` after labeling

## Label format

With `YOLO` format, label will be saved with format `label_index x_center y_center w h` and normalize to scale `[0, 1]`

``` txt
1 0.415842 0.863095 0.102970 0.101190
1 0.228713 0.315476 0.077228 0.053571
1 0.756436 0.328869 0.114851 0.050595
```
