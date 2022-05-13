# Final Project for UVA ML Class


## Downloading the Training Data
go to [this](https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/published-archive.html)
page and download the `GTSRB_Final_Training_Images.zip` dataset. Unzip the folder and move its contents into the root of the project. The unziped contents for me were a folder called `GTSRB` with a subfolder `Final_Training` and a text file.
The code below relies on this folder structure so if your folders are called something different, change the `DATA_DIR` and `TRAINING_DATA_PATH` constants.

## Downloading the Testing Data
On the website, the test images are in the `GTSRB_Final_Test_Images.zip` link. This set is formatted 
slightly different from the Training images so we will use a new function to read them into numpy arrays.

Additionally, the images do not have ground truth values (classes) associated with them. To get these, we have to
download the `GTSRB_Final_Test_GT.zip` link and extract a `.csv` file. We will move this `.csv` file into the `Final_Test`
folder from the extracted test image zip. 

## Setting up Virtual Environment
To install the required packages in a virtual environment use this command
``` shell
python3 -m venv env
source env/bin/activate
pip3 install -r requirements.txt
```


## Project Structure
### Notebooks
* [exploration.ipynb](./exploration.ipynb): The primary file in the project. This notebook contains the exploration
of convolutional neural networks.
* [corrupted.ipynb](./corrupted.ipynb): This file explores the camera attacks, blurring and adding lines, as well as
how to defend against them.
* [grayscale.ipynb](./grayscale.ipynb): This short notebooks is an experiment with adding a grayscale conversion to
our image preprocessing step.

### Models
* [basic_cnn.h5](./basic_cnn.h5): The initial cnn model we trained in [exploration.ipynb](./exploration.ipynb)
* [cnn_v2.h5](./cnn_v2.h5): The CNN model trained with the updated architecture in [exploration.ipynb](./exploration.ipynb)
* [cnn_v3.h5](./cnn_v3.h5): The CNN trained with the tuned hyperparameters in [exploration.ipynb](./exploration.ipynb)
* [cnn_grayscale.h5](./cnn_grayscale.h5): The CNN trained on grayscale images in [grayscale.ipynb](./grayscale.ipynb)

### Misc
* [requirements.txt](./requirements.txt): The file that holds all of the python packages needed to run the notebooks