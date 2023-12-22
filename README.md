# Audio To MIDI Transcriber

<details>
<summary>Table of Contents</summary>
  
1. [Summary](#summary)
2. [Features](#features)
3. [Visuals](#visuals)
4. [Technologies](#technologies)
5. [What I Learned](#what-i-learned)
6. [Setup and Installation](#setup-and-installation)
7. [Usage](#usage)
8. [Code Examples](#code-examples)
9. [How to Contribute](#how-to-contribute)
10. [License](#license)
11. [Contact](#contact)
12. [Acknowledgments](#acknowledgments)

</details>

## Summary
A web application that automatically transcribes audio (.mp3 format) to MIDI notation.

## Features
- **Automatic Music Transcription**: Uses a machine learning neural network to predict the MIDI transcription of an audio file.
- **In-browser Music Player**: An in-browser music player to listen to uploaded audio files.
- **In-browser Piano Roll**: An in-browser piano roll to follow along with the transcribed MIDI as it is being played back.
- **Download MIDI Transcription**: A button to download the transcribed MIDI file.

## Visuals
*Insert images or gifs showing your project in action. Consider before/after shots, workflows, or demos.*

## Technologies
- Front-end: HTML, CSS (with Bootstrap), Javascript
- Backend: Docker, Python, FastAPI, Tensorflow ML Framework

## What I Learned
Highlight specific skills or concepts you learned or improved upon while working on this project. This section should directly address potential employer interests.
- **Containerization**: How to dockerize software including all of its dependencies for easier portability.
- **Implementing AI into a web application**: Used FastAPI to interface with Python backend to run model and produce MIDI predictions.

## Setup and Installation (using Docker)
1. Clone the repo: `git clone [URL]`
2. Download and install Docker:
   - Windows:  https://docs.docker.com/desktop/install/windows-install/
   - macOS: https://docs.docker.com/desktop/install/mac-install/
   - Linux: `https://docs.docker.com/desktop/install/linux-install/`
3. Build docker image: `docker build -t [IMAGE_TAG] [REPOSITORY_DIRECTORY]`
 
## Setup and Installation (using virtualenv)
1. Clone the repo: `git clone [URL]`
2. Create and activate virtual environment:
    - `pip install virtualenv`
    - `virtualenv [ENVIRONMENT_NAME]`
    - Windows: `.\[ENVIRONMENT_NAME]\Scripts\activate` || Unix/Mac: `source [ENVIRONMENT_NAME]/bin/activate`
4. Install dependencies: `pip install requirements.txt`

## Usage (using Docker)
1. Run a docker container of the built image: `docker run -p 8000:8000 [IMAGE_TAG]`
2. Use a local hosting tool like XAMPP or NGINX to host a web server and run the webpage in a browser

## Usage (using virtualenv)
1. Run python backend: `python src/app.py`
2. Use a local hosting tool like XAMPP or NGINX to host a web server and run the webpage in a browser

## Code Examples
*Show small, but significant snippets of code from your project.*

## How to Contribute
*Encourage contributions and provide guidelines for how others can help.*

## License
*State the license under which your project is available.*

## Contact
*Your contact information or links to your professional profiles like LinkedIn.*

## Acknowledgments
*Credits to individuals or resources that helped you during the project.*

---
