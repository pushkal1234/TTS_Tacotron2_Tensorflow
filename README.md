# TTS_Tacotron2_Tensorflow

I had trained the model on LJ Speech Dataset open source speech datasets.

LJ Speech Dataset is recently widely used as a benchmark dataset in the TTS task because it is publicly available. It has 24 hours of reasonable quality samples.
We can get the dataset from https://keithito.com/LJ-Speech-Dataset/  


# About the Dataset:

This is a public domain speech dataset consisting of 13,100 short audio clips of a single speaker reading passages from 7 non-fiction books. A transcription is provided for each clip. Clips vary in length from 1 to 10 seconds and have a total length of approximately 24 hours.

The texts were published between 1884 and 1964, and are in the public domain. The audio was recorded in 2016-17 by the LibriVox project and is also in the public domain.

# File Format
Metadata is provided in transcripts.csv. This file consists of one record per line, delimited by the pipe character (0x7c). The fields are:

1) **ID:** this is the name of the corresponding .wav file

2) **Transcription:** words spoken by the reader (UTF-8)
 
3) **Normalized Transcription:** transcription with numbers, ordinals, and monetary units expanded into full words (UTF-8).
Each audio file is a single-channel 16-bit PCM WAV with a sample rate of 22050 Hz.

# Training

1) Download LJ Speech Dataset from the link mentioned above.

2) Adjust hyper parameters in hyperparams.py. (If you want to do preprocessing, set prepro True`.

3) Run python train.py. (If you set prepro True, run python prepro.py first)

4) Run python eval.py regularly during training.

# Sample Synthesis

Run python synthesize.py and check the files in samples.

I had generated the samples for inference and testing after training it for 200k steps
