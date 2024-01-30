# Audio To MIDI Transcriber

<details>
<summary>Table of Contents</summary>
  
1. [Summary](#summary)
2. [Documentation](#documentation)
3. [Features](#features)
4. [Visuals](#visuals)
5. [Technologies](#technologies)
6. [What We Learned](#what-we-learned)
7. [Setup and Installation](#setup-and-installation)
8. [Usage](#usage)
9. [Code Examples](#code-examples)
10. [Contact](#contact)
11. [Acknowledgments](#acknowledgments)

</details>

## Summary
A web application that automatically transcribes audio (.mp3 format) to MIDI notation.

## Documentation
- [Final Presentation Slides](web/_assets/AI%20Audio%20to%20MIDI%20Transcriber.pdf)
- [Final Paper](web/_assets/Convolutional_Neural_Network_Based_Approach_for_MIDI_Transcription_from_Raw_Audio.pdf)

## Features
- **Automatic Music Transcription**: Uses a machine learning neural network to predict the MIDI transcription of an audio file.
- **In-browser Music Player**: An in-browser music player to listen to uploaded audio files.
- **In-browser Piano Roll**: An in-browser piano roll to follow along with the transcribed MIDI as it is being played back.
- **Download MIDI Transcription**: A button to download the transcribed MIDI file.

## Visuals
<p float="left">
  <img src="https://raw.githubusercontent.com/alexfishy12/audio_to_midi_transcriber/main/screenshots/choose_file.png" width="100%" />
</p>
<p float="left">
  <img src="https://raw.githubusercontent.com/alexfishy12/audio_to_midi_transcriber/main/screenshots/generated_midi.png" width="100%" />
</p>

## Technologies
- Front-end: HTML, CSS (with Bootstrap), Javascript
- Backend: Docker, Python, FastAPI, Tensorflow ML Framework

## What We Learned
- **Fundamentals of TensorFlow**: How to use TensorFlow ML Framework to build data processing pipelines for ML training.
- **Containerization**: How to dockerize software including all of its dependencies for easier portability.
- **Implementing AI into a web application**: Used FastAPI to interface with Python backend to run model and produce MIDI predictions.
- **Audio data processing**: How to extract, transform, and load audio data and process it to enable a machine learning model to perform audio to MIDI transcription training and prediction

## Setup and Installation

### General Setup
1. Clone the repo: `git clone https://github.com/alexfishy12/audio_to_midi_transcriber.git`
2. Download and install Docker:
   - Windows:  https://docs.docker.com/desktop/install/windows-install/
   - macOS: https://docs.docker.com/desktop/install/mac-install/
   - Linux: https://docs.docker.com/desktop/install/linux-install/
3. Create a `.env` file in the base project directory. The content of the file should look like the following (variable values are up to you, these values are what we used):

    ```env
    PORT_WEB=1110
    PORT_PYTHON=1111
    ```
4. If you plan on running directly on localhost, change the URL in the `transcribe.js` `transcribe_audio` function from `transcribe` to the following: `http://localhost:[PORT_PYTHON]/transcribe`. You must also change the first part of the `midi_file_url` in the `get_midi_file` function from `/static` to `http://localhost:[PORT_PYTHON]/static`

### Model Training Setup

1. Download the MAESTRO dataset of mp3 and midi files from: https://magenta.tensorflow.org/datasets/maestro#v300
    - Follow the instructions of the [README.md](./independent_study/datasets/maestro-v3.0.0/README) file under `./independent_study/datasets/maestro-v3.0.0` to properly position the dataset for the training notebook to find:

        ```
        - Base project directory folder
          - independent_study
            - datasets
              - maestro-v3.0.0
                - maestro-v3.0.0.json
                - README.md
                - [place dataset folders here ("/2006", "/2007", etc.)] 
        ```

2. Create and activate virtual environment (in base project folder):
    - `pip install virtualenv`
    - `virtualenv [ENVIRONMENT_NAME]`
    - Windows: `.\[ENVIRONMENT_NAME]\Scripts\activate` || Unix/Mac: `source [ENVIRONMENT_NAME]/bin/activate`
3. Install dependencies into the virtual environment: `pip install python/requirements.txt`

4. To train and save a model to make predictions, you must run each cell in order in the file: [Training.ipynb](independent_study/Training.ipynb) (make sure you are using python.exe in the created virtual environment as the kernel for the notebook). 
    - If successful, the folder [independent_study/saved_models/new_saved_model](./independent_study/saved_models/new_saved_model/) will contain the newly trained model from the python notebook. This is a file containing saved model weights for your finetuned model. 
    - Feel free to connect your model to the front-end by moving the `new_saved_model` folder to [python/usable_models/](./python/usable_models/). You will need to modify the code in [python/app.py](./python/app.py) and [web/index.html](./web/index.html) to include a new option to choose the newly created model for making predictions.

## Usage
1. Run docker compose in the terminal of the base project directory: `docker compose up --build`
2. Visit `http://localhost:[PORT_WEB]` to interact with the running web application.

## Code Examples
- **MIDI Prediction Function (credits to [Spotify Basic Pitch](https://github.com/spotify/basic-pitch))**: 

  ```python
  predict_and_save(model_path=model_path, output_directory=TEMP_FILE_STORAGE_PATH, audio_path_list=[audio_file],    save_midi=True, sonify_midi=False, save_model_outputs=False, save_notes=False)
  ```
- **Model Training Code**: 

  ```python
  model_train = models.model()
  adam_optimizer = tf.keras.optimizers.Adam(learning_rate=0.001)
  onset_loss_function = WeightedBinaryCrossEntropy(pos_weight=0.99, neg_weight=0.01)
  contour_loss_function = WeightedBinaryCrossEntropy(pos_weight=0.99, neg_weight=0.01)
  note_loss_function = WeightedBinaryCrossEntropy(pos_weight=0.99, neg_weight=0.01)
  model_train.compile(optimizer=adam_optimizer, loss={"onset": onset_loss_function, "note": note_loss_function})

  # train model
  num_epochs = 1

  model_train.fit(train_dataset, validation_data=val_dataset, epochs=num_epochs, batch_size=16)
  ```

## Contact
Alexander J. Fisher
  - **Email**: alexfisher0330@gmail.com
  - **LinkedIn**: https://www.linkedin.com/in/alexjfisher

Kevin Parra-Olmedo
  - **Email**: parraolk@kean.edu
  - **LinkedIn**: https://www.linkedin.com/in/kevin-parra-5823401b8

## Acknowledgments
We would like to thank Kuan Huang, Ph.D. (khuang@kean.edu) who advised us during our Independent Study for this project.

---
