# Vision Transformers for Image Regression Task on Pet's Popularity Score

Edited by Edgar Corrales on 12/10/21



# Data
To get the data used in these models:

 1. Go to https://www.kaggle.com/c/petfinder-pawpularity-score/data 
 2. Accept the competition terms and select **Download all**
 3. Create an account if asked to.



# Instructions

To reproduce the results from the notebook you should change the Config dictionary values inside the notebook to match those of your downloaded files path.

    

    Config = {    
    'CSV_PATH':  "**Add the csv path for the train.csv file**",    
    'IMG_PATH':  "**Add the path of the train images**",    
    'TEST_PATH':  '**Add the path of the test images**',    
    'N_SPLITS':  5,    
    'TRAIN_BS':  16,    
    'VALID_BS':  16,    
    'N_EPOCHS':  10,    
    'NUM_WORKERS':  4, 
    'LR':  1e-5,    
    'ARCH':  'vit_large_patch16_224',    
    'OPTIM':  "AdamW",    
    'SCH_STEP':  4,    
    'GAMMA':  0.1,    
    'SCHEDULER':  'CosineWarm',    
    "T_0":  20,    
    "η_min":  1e-6,    
    'PATIENCE':  3,    
    'LOSS':  "RMSE",    
    'IMG_SIZE':  224,    
    'DEVICE':  "cuda",    
    'infra':  "Colab",    
    'competition':  'pawpularity',    
    '_wandb_kernel':  'tanaym',    
    "wandb":  True,    
    }

 You can also make your own adjustments

## Wandb

Wandb is a powerful tool to keep your models organized. All the logs and plots for the models were generated using Wandb. 
Use the following API key if asked during the code execution if you want to use Wandb, otherwise set `Config["wandb"] = False` to disable it.

    API key: 1c05ee9164fece7f1855ad5e270ce5d2c9531b47
  Also here is the link for the Wandb project: https://wandb.ai/edgarlcs/pawpularity_kaggle_final

## Using Google Colab

If you are using Google Colab you can download the dataset using the Kaggle API here are the commands:

    ! mkdir ~/.kaggle
    
    ! cp /YOUR_JSON_PATH/kaggle.json ~/.kaggle/
    
    ! chmod 600 ~/.kaggle/kaggle.json
    
    ! kaggle datasets download schulta/petfinder-pawpularity-score-clean
    
    ! unzip /content/petfinder-pawpularity-score-clean.zip -d /EXTRACTION_PATH/
    
  The `kaggle.json` file  can be found in your Kaggle account settings.
  For more information and detailed steps go to:  https://github.com/Kaggle/kaggle-api

## Notebooks    
Here are the links to the notebooks used for the project. I used both Kaggle and Colab notebooks in order to run more than one model at the same time. Note these are only 2 links. I reused the online notebooks for convenience just by adjusting the configurations but you can find the code for all 4 in this repository.
Colab: https://colab.research.google.com/drive/11P-DvPu5o6HmJU9JyzpAFfSrFtuaCSej?usp=sharing
Kaggle: https://www.kaggle.com/edgarcorrales/resnet18/

