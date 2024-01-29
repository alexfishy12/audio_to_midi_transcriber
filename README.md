# Audio To MIDI Transcriber

<details>
<summary>Table of Contents</summary>
  
1. [Summary](#summary)
2. [Features](#features)
3. [Visuals](#visuals)
4. [Technologies](#technologies)
5. [What We Learned](#what-we-learned)
6. [Setup, Installation, and Usage](#setup-installation-and-usage)
7. [Usage](#usage)
8. [Code Examples](#code-examples)
9. [License](#license)
10. [Contact](#contact)
11. [Acknowledgments](#acknowledgments)

</details>

## Summary
A web application that automatically transcribes audio (.mp3 format) to MIDI notation.

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

## Documentation
- [Final Presentation Slides](web/_assets/AI%20Audio%20to%20MIDI%20Transcriber.pdf)
- [Final Paper](web/_assets/Convolutional_Neural_Network_Based_Approach_for_MIDI_Transcription_from_Raw_Audio.pdf)

## Technologies
- Front-end: HTML, CSS (with Bootstrap), Javascript
- Backend: Docker, Python, FastAPI, Tensorflow ML Framework

## What We Learned
- **Fundamentals of TensorFlow**: How to use TensorFlow ML Framework to build data processing pipelines for ML training.
- **Containerization**: How to dockerize software including all of its dependencies for easier portability.
- **Implementing AI into a web application**: Used FastAPI to interface with Python backend to run model and produce MIDI predictions.
- **Audio data processing**: How to extract, transform, and load audio data and process it to enable a machine learning model to perform audio to MIDI transcription training and prediction

## Setup, Installation, and Usage

*[NOTE]: Choose one of the following two sections for setup, installation, and usage of the project (**Docker** or **Virtualenv**)*

### Docker
<details open>
<summary>Set up, installation, and usage</summary>
  
#### Setup and Installation
1. Clone the repo: `git clone https://github.com/alexfishy12/audio_to_midi_transcriber.git`
2. Download and install Docker:
   - Windows:  https://docs.docker.com/desktop/install/windows-install/
   - macOS: https://docs.docker.com/desktop/install/mac-install/
   - Linux: https://docs.docker.com/desktop/install/linux-install/
3. Build docker image: `docker build -t [IMAGE_TAG] [REPOSITORY_DIRECTORY]`

#### Usage
1. Run a docker container of the built image: `docker run -p 8000:8000 [IMAGE_TAG]`
2. Use a local hosting tool like XAMPP or NGINX to host a web server and run the webpage in a browser

</details>

### Virtualenv
<details>
<summary>Set up, installation, and usage</summary>

#### Setup and Installation
1. Clone the repo: `git clone https://github.com/alexfishy12/audio_to_midi_transcriber.git`
2. Create and activate virtual environment:
    - `pip install virtualenv`
    - `virtualenv [ENVIRONMENT_NAME]`
    - Windows: `.\[ENVIRONMENT_NAME]\Scripts\activate` || Unix/Mac: `source [ENVIRONMENT_NAME]/bin/activate`
4. Install dependencies: `pip install requirements.txt`

#### Usage
1. Run python backend: `python src/app.py`
2. Use a local hosting tool like XAMPP or NGINX to host a web server and run the webpage in a browser

</details>

## Code Examples
- **MIDI Prediction Function (credits to [Spotify Basic Pitch](https://github.com/spotify/basic-pitch))**: `predict_and_save(model_path=model_path, output_directory=TEMP_FILE_STORAGE_PATH, audio_path_list=[audio_file], save_midi=True, sonify_midi=False, save_model_outputs=False, save_notes=False)`
- **Model Training Code**: `model_train.fit(train_dataset, validation_data=val_dataset, epochs=num_epochs, batch_size=16)`

## License
*State the license under which your project is available.*

## Contact
Alexander J. Fisher
  - **Email**: alexfisher0330@gmail.com
  - **LinkedIn**: www.linkedin.com/in/alexjfisher

Kevin Parra-Olmedo
  - **Email**: parraolk@kean.edu
  - **LinkedIn**: www.linkedin.com/in/kevin-parra-5823401b8

## Acknowledgments
We would like to thank Kuan Huang, Ph.D. (khuang@kean.edu) who advised us during our Independent Study for this project.

---
