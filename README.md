# Text To Speech Dataset Maker 👷‍♂️

![TTS Datamaker](https://user-images.githubusercontent.com/55686042/211143554-771ff02a-3f79-4008-8eb6-7553ebcd846f.png)


### This repository offers a way to make personalized dataset for model creation using the LJSpeech format.


## Full code available for use now!😁: [🎶Remisal Audio 🎵](https://colab.research.google.com/github/kudzaijaure-dot/tts_datamaker/blob/main/RemisalAudio.ipynb)



## Steps to build your Dataset
If you have want to use an audio file of your own skip step 2 . If you want to use audio from a wide range of speakers available from youtube step 2 is for you.

### 1. Clone the repository
```
git clone https://github.com/kudzaijaure-dot/tts_datamaker
```
```
cd TTS_Data_Maker
pip install -r requirements.txt
```

### 2. Download a speech
To download an audio from YouTube, Google Drive or other online storage mediums, make use of one of these: 

```
python audio_download.py --video_link https://www.youtube.com/watch?v=-B8Ikd1E --speaker_name got
!cd main_audi && gdown https://link-to-donwload/token=xyz

```


### 3.Split the audio into small parts.
To split the downloaded audio into smaller parts use the extract_segment.py file of the repository. Only upload mp4 content.

### Audio to speech 

For Audio to speech we will use Google's Speech-To-Text engine, which enables easy integration of Google speech recognition technologies into applications 
to extract text from the audio snippets.
For optimal results, the recognizer is designed to ignore background voices and noise without additional noise-canceling. However, for optimal results, position the microphone as close to the user as possible, particularly when background noise is present. Excessive background noise and echoes may reduce accuracy, especially if a lossy codec is also used.
If you are capturing audio from more than one person, and each person is recorded on a separate channel, send each channel separately to get the best recognition results. However, if all speakers are mixed in a single channel recording, send the recording as is.	
Multiple people talking at the same time, or at different volumes may be interpreted as background noise and ignored.
For short queries or commands, use StreamingRecognize with single_utterance set to true. This optimizes the recognition for short utterances and also minimizes latency.




### Final Dataset
The final dataset will have metadata.txt and audio_split folder having all the audio files like 1.wav , 2.wav , 3.wav and soon
metadata.txt file will look like this
```
metadata.txt-
audio1|Hey how are you
audio2|I hope you are fine
audio3|Lets meet at dinner
```
The wav folder containing all the audio files will look like this
```
wav
-audio1.wav
-audio2.wav
-audio3.wav
```
In the end, we should have the following folder structure:
```
/MyTTSDataset
 |
 | -> metadata.txt
 | -> /wavs
  | -> audio1.wav
  | -> audio2.wav
  | ...
```



