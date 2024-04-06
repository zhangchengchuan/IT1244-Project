# Project Structure

## IT1244-Project (Main folder)
- **Dataset**
    - **Audio Dataset**
        - **Cats and Dogs**
            - **Data**
                - Given Cats and Dogs Dataset (277 .wav samples)
    - **Test_data**
        - BarkMeowDB additional data from [https://zenodo.org/records/3563521](https://zenodo.org/records/3563521)
- **Notebooks**
    - Exploratory_Data_analysis.ipynb
    - Results_analysis.ipynb
- **Python**
    - Evaluation.py
    - Main.py
    - Utils.py
    - Hp_tuning.py
    - Models.py
- **Requirements.txt**

## Virtual Environment
1. At the root of the folder, you may create a new virtual environment using: `python3 -m venv it1244project`
2. Activate it: `source it1244project/bin/activate`
3. Install the relevant libraries: `pip install -r requirements.txt`

## Running of Python files
1. Assuming that the structure of the folder looks like the one described in “Project Structure”, at the root-level directory, run (on a UNIX or bash system): `./run_pipeline.sh`
2. This script runs `python python/main.py` and `python python/evaluation.py` which runs the training and evaluation step for a template CNN model which takes a bit of time.
3. There is no /models/ folder in the submission, but it should be created when main.py or evaluation.py or notebook_main_evaluation.ipynb is executed.

## Running of Notebooks
1. For the actual training and evaluation code, look at notebook_main_evaluation.ipynb
    - The “arguments” are in the second cell. Modify them and run the entire file.
2. For the Data Visualization and results visualization, you can just refer to them.
    - To rerun these notebooks, the models and their logs.txt should exist.
    - Run the main training and evaluation file once at least, so that the ./models/ folder exists and contains a model to evaluate.

## Replicating the Hyperparameter Tuning Process
To replicate the hyperparameter tuning process we ran with 3 models and 12 versions each:
1. At root-level directory, run: `python python/hp_tuning.py`
2. If you want to modify the hyperparameters, you can change the numbers inside each for loop.

## Training Individual Models and Evaluating Them
1. At root-level directory, run: `python python main.py <COMMAND_LINE ARGUMENTS>` and `python python/evaluation.py <COMMAND_LINE ARGUMENTS>`.
2. Note that to evaluate the model that you just ran, ensure that the command line arguments are the same so that the model state can be found.
3. For the command line arguments:
    - -lr <LEARNING_RATE>
    - -bs <BATCH_SIZE>
    - -do <DROPOUT_RATE>
    - -t <TYPE of model: ‘cnn’, ‘lstm’, ‘base’>

## In Case of Errors
1. If there are errors pertaining to folder structure, the following files (and respective lines of code) have preset folder locations for convenience purposes. Do change them if needed.
    - Main.py line 142-153
    - Evaluation.py line 108-118
    - Hp_tuning.py line 14-16
2. For other errors, feel free to email me at [e0543837@u.nus.edu](mailto:e0543837@u.nus.edu)
