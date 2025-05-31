COMPANY NAME: CODETECH IT SOLUTIONS 
NAME :KALPANA KORNI
INTERN ID : CT04DM636
DOMAIN: ARTIFICIAL INTELLIGENCE 
DURATION: 4 WEEKS
MENTOR : NEELA SANTOSH 


Library for performing speech recognition, with support for several engines and APIs, online and offline.

Speech recognition engine/API support:

CMU Sphinx (works offline)
Google Speech Recognition
Google Cloud Speech API
Wit.ai
Microsoft Azure Speech
Microsoft Bing Voice Recognition (Deprecated)
Houndify API
IBM Speech to Text
Snowboy Hotword Detection (works offline)
Tensorflow
Vosk API (works offline)
OpenAI whisper (works offline)
OpenAI Whisper API
Groq Whisper API
Quickstart: pip install SpeechRecognition. See the "Installing" section for more details.

To quickly try it out, run python -m speech_recognition after installing.

Project links:

PyPI
Source code
Issue tracker
Library Reference
The library reference documents every publicly accessible object in the library. This document is also included under reference/library-reference.rst.

See Notes on using PocketSphinx for information about installing languages, compiling PocketSphinx, and building language packs from online resources. This document is also included under reference/pocketsphinx.rst.

Examples
See the examples/ directory in the repository root for usage examples:

Recognize speech input from the microphone
Transcribe an audio file
Save audio data to an audio file
Show extended recognition results
Calibrate the recognizer energy threshold for ambient noise levels (see recognizer_instance.energy_threshold for details)
Listening to a microphone in the background
Various other useful recognizer features
Installing
First, make sure you have all the requirements listed in the "Requirements" section.

The easiest way to install this is using pip install SpeechRecognition.

Otherwise, download the source distribution from PyPI, and extract the archive.

In the folder, run python setup.py install.

Requirements
To use all of the functionality of the library, you should have:

Python 3.9+ (required)
PyAudio 0.2.11+ (required only if you need to use microphone input, Microphone)
PocketSphinx (required only if you need to use the Sphinx recognizer, recognizer_instance.recognize_sphinx)
Google API Client Library for Python (required only if you need to use the Google Cloud Speech API, recognizer_instance.recognize_google_cloud)
FLAC encoder (required only if the system is not x86-based Windows/Linux/OS X)
Vosk (required only if you need to use Vosk API speech recognition recognizer_instance.recognize_vosk)
Whisper (required only if you need to use Whisper recognizer_instance.recognize_whisper)
Faster Whisper (required only if you need to use Faster Whisper recognizer_instance.recognize_faster_whisper)
openai (required only if you need to use OpenAI Whisper API speech recognition recognizer_instance.recognize_openai)
groq (required only if you need to use Groq Whisper API speech recognition recognizer_instance.recognize_groq)
The following requirements are optional, but can improve or extend functionality in some situations:

If using CMU Sphinx, you may want to install additional language packs to support languages like International French or Mandarin Chinese.
The following sections go over the details of each requirement.

Python
The first software requirement is Python 3.9+. This is required to use the library.

PyAudio (for microphone users)
PyAudio is required if and only if you want to use microphone input (Microphone). PyAudio version 0.2.11+ is required, as earlier versions have known memory management bugs when recording from microphones in certain situations.

If not installed, everything in the library will still work, except attempting to instantiate a Microphone object will raise an AttributeError.

The installation instructions on the PyAudio website are quite good - for convenience, they are summarized below:

On Windows, install with PyAudio using Pip: execute pip install SpeechRecognition[audio] in a terminal.
On Debian-derived Linux distributions (like Ubuntu and Mint), install PyAudio using APT: execute sudo apt-get install python-pyaudio python3-pyaudio in a terminal.
If the version in the repositories is too old, install the latest release using Pip: execute sudo apt-get install portaudio19-dev python-all-dev python3-all-dev && sudo pip install SpeechRecognition[audio] (replace pip with pip3 if using Python 3).
On OS X, install PortAudio using Homebrew: brew install portaudio. Then, install with PyAudio using Pip: pip install SpeechRecognition[audio].
On other POSIX-based systems, install the portaudio19-dev and python-all-dev (or python3-all-dev if using Python 3) packages (or their closest equivalents) using a package manager of your choice, and then install with PyAudio using Pip: pip install SpeechRecognition[audio] (replace pip with pip3 if using Python 3).
PocketSphinx (for Sphinx users)
PocketSphinx is required if and only if you want to use the Sphinx recognizer (recognizer_instance.recognize_sphinx).

On Linux and other POSIX systems (such as OS X), run pip install SpeechRecognition[pocketsphinx]. Follow the instructions under "Building PocketSphinx-Python from source" in Notes on using PocketSphinx for installation instructions.

Note that the versions available in most package repositories are outdated and will not work with the bundled language data. Using the bundled wheel packages or building from source is recommended.

See Notes on using PocketSphinx for information about installing languages, compiling PocketSphinx, and building language packs from online resources. This document is also included under reference/pocketsphinx.rst.

Vosk (for Vosk users)
Vosk API is required if and only if you want to use Vosk recognizer (recognizer_instance.recognize_vosk).

You can install it with python3 -m pip install SpeechRecognition[vosk].

You also have to install Vosk Models:

Here are models available for download. You have to place them in the model directory of your project, like "your-project-folder/model". You can also run sprc download vosk to download the default model.

Google Cloud Speech Library for Python (for Google Cloud Speech-to-Text API users)
The library google-cloud-speech is required if and only if you want to use Google Cloud Speech-to-Text API (recognizer_instance.recognize_google_cloud). You can install it with python3 -m pip install SpeechRecognition[google-cloud]. (ref: official installation instructions)

Prerequisite: Create local authentication credentials for your Google account

Digest: Before you begin (Transcribe speech to text by using client libraries)
Set up Speech-to-Text
User credentials (Set up ADC for a local development environment)
Currently only V1 is supported. (V2 is not supported)

FLAC (for some systems)
A FLAC encoder is required to encode the audio data to send to the API. If using Windows (x86 or x86-64), OS X (Intel Macs only, OS X 10.6 or higher), or Linux (x86 or x86-64), this is already bundled with this library - you do not need to install anything.

Otherwise, ensure that you have the flac command line tool, which is often available through the system package manager. For example, this would usually be sudo apt-get install flac on Debian-derivatives, or brew install flac on OS X with Homebrew.

Whisper (for Whisper users)
Whisper is required if and only if you want to use whisper (recognizer_instance.recognize_whisper).

You can install it with python3 -m pip install SpeechRecognition[whisper-local].

Faster Whisper (for Faster Whisper users)
The library faster-whisper is required if and only if you want to use Faster Whisper (recognizer_instance.recognize_faster_whisper).

You can install it with python3 -m pip install SpeechRecognition[faster-whisper].

OpenAI Whisper API (for OpenAI Whisper API users)
The library openai is required if and only if you want to use OpenAI Whisper API (recognizer_instance.recognize_openai).

You can install it with python3 -m pip install SpeechRecognition[openai].

Please set the environment variable OPENAI_API_KEY before calling recognizer_instance.recognize_openai.

Groq Whisper API (for Groq Whisper API users)
The library groq is required if and only if you want to use Groq Whisper API (recognizer_instance.recognize_groq).

You can install it with python3 -m pip install SpeechRecognition[groq].

Please set the environment variable GROQ_API_KEY before calling recognizer_instance.recognize_groq.

Troubleshooting
The recognizer tries to recognize speech even when I'm not speaking, or after I'm done speaking.
Try increasing the recognizer_instance.energy_threshold property. This is basically how sensitive the recognizer is to when recognition should start. Higher values mean that it will be less sensitive, which is useful if you are in a loud room.

This value depends entirely on your microphone or audio data. There is no one-size-fits-all value, but good values typically range from 50 to 4000.

Also, check on your microphone volume settings. If it is too sensitive, the microphone may be picking up a lot of ambient noise. If it is too insensitive, the microphone may be rejecting speech as just noise.

The recognizer can't recognize speech right after it starts listening for the first time.
The recognizer_instance.energy_threshold property is probably set to a value that is too high to start off with, and then being adjusted lower automatically by dynamic energy threshold adjustment. Before it is at a good level, the energy threshold is so high that speech is just considered ambient noise.

The solution is to decrease this threshold, or call recognizer_instance.adjust_for_ambient_noise beforehand, which will set the threshold to a good value automatically.

The recognizer doesn't understand my particular language/dialect.
Try setting the recognition language to your language/dialect. To do this, see the documentation for recognizer_instance.recognize_sphinx, recognizer_instance.recognize_google, recognizer_instance.recognize_wit, recognizer_instance.recognize_bing, recognizer_instance.recognize_api, recognizer_instance.recognize_houndify, and recognizer_instance.recognize_ibm.

For example, if your language/dialect is British English, it is better to use "en-GB" as the language rather than "en-US".

The recognizer hangs on recognizer_instance.listen; specifically, when it's calling Microphone.MicrophoneStream.read.
This usually happens when you're using a Raspberry Pi board, which doesn't have audio input capabilities by itself. This causes the default microphone used by PyAudio to simply block when we try to read it. If you happen to be using a Raspberry Pi, you'll need a USB sound card (or USB microphone).

Once you do this, change all instances of Microphone() to Microphone(device_index=MICROPHONE_INDEX), where MICROPHONE_INDEX is the hardware-specific index of the microphone.

To figure out what the value of MICROPHONE_INDEX should be, run the following code:

import speech_recognition as sr
for index, name in enumerate(sr.Microphone.list_microphone_names()):
    print("Microphone with name \"{1}\" found for `Microphone(device_index={0})`".format(index, name))
This will print out something like the following:

Microphone with name "HDA Intel HDMI: 0 (hw:0,3)" found for `Microphone(device_index=0)`
Microphone with name "HDA Intel HDMI: 1 (hw:0,7)" found for `Microphone(device_index=1)`
Microphone with name "HDA Intel HDMI: 2 (hw:0,8)" found for `Microphone(device_index=2)`
Microphone with name "Blue Snowball: USB Audio (hw:1,0)" found for `Microphone(device_index=3)`
Microphone with name "hdmi" found for `Microphone(device_index=4)`
Microphone with name "pulse" found for `Microphone(device_index=5)`
Microphone with name "default" found for `Microphone(device_index=6)`
Now, to use the Snowball microphone, you would change Microphone() to Microphone(device_index=3).

Calling Microphone() gives the error IOError: No Default Input Device Available.
As the error says, the program doesn't know which microphone to use.

To proceed, either use Microphone(device_index=MICROPHONE_INDEX, ...) instead of Microphone(...), or set a default microphone in your OS. You can obtain possible values of MICROPHONE_INDEX using the code in the troubleshooting entry right above this one.

The program doesn't run when compiled with PyInstaller.
As of PyInstaller version 3.0, SpeechRecognition is supported out of the box. If you're getting weird issues when compiling your program using PyInstaller, simply update PyInstaller.

You can easily do this by running pip install --upgrade pyinstaller.

On Ubuntu/Debian, I get annoying output in the terminal saying things like "bt_audio_service_open: [...] Connection refused" and various others.
The "bt_audio_service_open" error means that you have a Bluetooth audio device, but as a physical device is not currently connected, we can't actually use it - if you're not using a Bluetooth microphone, then this can be safely ignored. If you are, and audio isn't working, then double check to make sure your microphone is actually connected. There does not seem to be a simple way to disable these messages.

For errors of the form "ALSA lib [...] Unknown PCM", see this StackOverflow answer. Basically, to get rid of an error of the form "Unknown PCM cards.pcm.rear", simply comment out pcm.rear cards.pcm.rear in /usr/share/alsa/alsa.conf, ~/.asoundrc, and /etc/asound.conf.

For "jack server is not running or cannot be started" or "connect(2) call to /dev/shm/jack-1000/default/jack_0 failed (err=No such file or directory)" or "attempt to connect to server failed", these are caused by ALSA trying to connect to JACK, and can be safely ignored. I'm not aware of any simple way to turn those messages off at this time, besides entirely disabling printing while starting the microphone.

On OS X, I get a ChildProcessError saying that it couldn't find the system FLAC converter, even though it's installed.
Installing FLAC for OS X directly from the source code will not work, since it doesn't correctly add the executables to the search path.

Installing FLAC using Homebrew ensures that the search path is correctly updated. First, ensure you have Homebrew, then run brew install flac to install the necessary files.

Developing
To hack on this library, first make sure you have all the requirements listed in the "Requirements" section.

Most of the library code lives in speech_recognition/__init__.py.
Examples live under the examples/ directory, and the demo script lives in speech_recognition/__main__.py.
The FLAC encoder binaries are in the speech_recognition/ directory.
Documentation can be found in the reference/ directory.
Third-party libraries, utilities, and reference material are in the third-party/ directory.
To install/reinstall the library locally, run python -m pip install -e .[dev] in the project root directory.

Before a release, the version number is bumped in README.rst and speech_recognition/__init__.py. Version tags are then created using git config gpg.program gpg2 && git config user.signingkey DB45F6C431DE7C2DCD99FF7904882258A4063489 && git tag -s VERSION_GOES_HERE -m "Version VERSION_GOES_HERE".

Releases are done by running make-release.sh VERSION_GOES_HERE to build the Python source packages, sign them, and upload them to PyPI.

Testing
Prerequisite: Install pipx.

To run all the tests:

python -m unittest discover --verbose
To run static analysis:

make lint
To ensure RST is well-formed:

make rstcheck
Testing is also done automatically by GitHub Actions, upon every push.

FLAC Executables
The included flac-win32 executable is the official FLAC 1.3.2 32-bit Windows binary.

The included flac-linux-x86 and flac-linux-x86_64 executables are built from the FLAC 1.3.2 source code with Manylinux to ensure that it's compatible with a wide variety of distributions.

The built FLAC executables should be bit-for-bit reproducible. To rebuild them, run the following inside the project directory on a Debian-like system:

# download and extract the FLAC source code
cd third-party
sudo apt-get install --yes docker.io

# build FLAC inside the Manylinux i686 Docker image
tar xf flac-1.3.2.tar.xz
sudo docker run --tty --interactive --rm --volume "$(pwd):/root" quay.io/pypa/manylinux1_i686:latest bash
    cd /root/flac-1.3.2
    ./configure LDFLAGS=-static # compiler flags to make a static build
    make
exit




