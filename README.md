# AcuCount_Imageset
 
This repository contains all nesscessary files and scripts required for running the AcuCount telegram detection bot. Follow the instructions, and execute the corresponding cells in the .ipynb scripts to reproduce the result in our AcuCount paper.

The *dataset* folder contains the raw images for the *training set*, and the *validation set*. For the *training set*, the needle annoatations are provided in .txt files in DOTA format as their corresponding images.

The *research* folder contains the validations records infered by the our Oriented R-CNN model. We have also provided the sample config file and checkpoint file for the Oriented R-CNN model.

There is also a *testing* folder inside the *dataset* folder containing the testing images and annotations. This *testing* set is provided as a quick reference to ensure that the model training is properly converged. The *testing* dataset is **not** intended for validation purpose and therefore not reported in our AcuCount paper.

We have also carried out an ablation experiment on different NMS and aspect ratio settings. The full record is avabile on [Google Drive](https://drive.google.com/drive/folders/1wTaLVpOjawfp6IXa_BR2L_zufGuKYRNF?usp=drive_link). You are also welcomed to train and test your own model by changing our config settings!

## Model Training

The model_training.ipynb is modified on top of the Colab tutorial provided in the [MMrotate github page](https://github.com/open-mmlab/mmrotate).

### Installing the prerequisite packages

Install the necessary packages. This repository is tested under Colab Pro enviroment with Pytorch 1.12.1, torchvision 0.13.1, MMrotate 0.3.4 and CUDA 11.6.

You may check your installation and GPU enviroment by running <code>collect_env()</code>.

### Prepare for custom dataset training

Clone this repository for the training imageset and the annotations files under the *training* folder. 

Follow the instructions to check the config settings or modify them for you own need.

### Model Training

Execute the `train_detector` cell to initate the training. If you want to monitor the training progress, you can run the tensorboard to check up on the learning losses.

Type Ctrl+C to terminate the training. You may find your inference graph under <code>./tutorial_exps</code> folder.

### Model Vaildation

Import the counting function and the logging module, and thus you can perform an out-of-box inference on the validation dataset. 

## Telegram object_detection bot

Switch to telegram_bot.ipynb for hosting the telegram bot on Google Colab. Install the nesscessary packages with [Python-Telegram-Bot](https://github.com/python-telegram-bot/python-telegram-bot). Mount the Google Drive for accessing the previosuly saved inference graph, and storing the inward/outward files. 

Follow the instutions on [telegram botfather](https://core.telegram.org/bots#6-botfather) to create a new telegram bot of your own and place the token in the script. 

Some pointing drectory contain `xx/yy/zz` in their pathname. Replace them with your filepath in Google Drive.  

This script uses `logging` modlule for recording the inward/outward timestamp. Place an empty .log file in your Google Drive for proper record. 

## Now try it yourself!

 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Deadfish-hk/AcuCount_imageset/blob/main/MMrotate_training_github_v0_11.ipynb) Access the model training notebook.

 [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Deadfish-hk/AcuCount_imageset/blob/main/telegram_bot_colab_mmrotate_github.ipynb) Access the telegram-detection bot.
 
 ## Acknowledgement
 
 This repository is built on top of the contributions from [Python-Telegram-Bot](https://github.com/python-telegram-bot/python-telegram-bot) and [MMrotate](https://github.com/open-mmlab/mmrotate).
 
 
 
