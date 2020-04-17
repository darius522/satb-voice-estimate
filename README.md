# satb-voice-estimate
repository for the MIR class final paper which tackles voice number estimation for SATB choral recordings

Keras model weights and original prediction scripts can be found at [2]. 

Unpublished experiment paper can be found at [3]:

# Title:
Source Number Estimation for monoaural SATB choral recording
## Description:
Source number estimation is a task which consists in estimating the number of different sound sources that are present in an audio recording. Previously, there have been several approaches proposed in order to tackle the issue. Some of them are directly derived from source localization methodologies and are thus relying on the spatial information the recording may convey [1]. In the field of MIR, this task depends mainly on the fact that the spectra of common musical sources in a song are largely uncorrelated. The case of choral singing however, involves groups of people singing in harmony, which leads to higher correlation amongst the constituent signals. In this work, we will attempt in proposing a methodology which would allow to predict accurately the number of singer in a given SATB recording.
## Datasets:
For this task, the following datasets will be used: <br />
• Choral Singing Dataset: https://zenodo.org/record/1286570#.Xkp7yi2ZPRY <br />
• EsmucChoralSet: Soon publicly available <br />
• A proprietary dataset: / <br />
## Methods:
### Pre-processing:
- Short segments (song snippets) of audio with randomized SATB part configurations will be
created from the above-mentioned dataset as a first pre-processing step
- Upon creation of these segments, the ground truth represented by the number of singers for
each segment will be saved as one-hot vectors
- Compute the snippets’ MFCCs
### Training:
- Step 1 - Baseline: train Keras DNN model using previously-computed MFCC features.
- Step 2 - Deep Salience approach: use the DeepSalience model from [2] in order to get a multi-pitch contour estimation. From there, we get the estimated numbers of singers.
## Evaluation:
Final predictions are done on a per phrase basis. The number of sources predicted per-frames are handled in three proposed ways [3] in order to predict the final source number prediction.

## Resources:
[1] https://biblio.ugent.be/publication/8585239/file/8585241.pdf <br />
[2] https://github.com/rabitt/ismir2017-deepsalience <br />
[3] https://34e9b95f-78f1-40e1-8a67-e1e6a8455578.filesusr.com/ugd/093395_3fd70e1a5241404297de3e4e75bc39ea.pdf

