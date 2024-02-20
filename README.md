# Weakly Supervised Audio Tagging
Implementation of New dataset Audio Tagging Via Weak Supervision Learning

## Preparing the dataset
MuLaP is pre-trained on a multimodal dataset of (audio, text) pairs. 

Annotations should be provided in JSON format and must include the following fields:

```audio_id```:     the unique identifier for each audio track in the dataset

```caption``` :     a string with the textual description of the audio track 

```audio_path```:   path to the audio track, relative to the root audio directory

One JSON file per split must be provided and stored in the [`data/datasets`](data/datasets/) directory, following this structure:

```
dataset_name
├── audio            
│   ├── track_1.mp3
│   ├── track_2.mp3
|   └── ...
├── audio_caption.json    
```

## Pre-training 
Dataset, model and training configurations are set in the respective `yaml` files in [`configs`](configs). You can also pass some options via the CLI, overwriting the arguments in the config files. For more details on the CLI options, please refer to the [training script](scripts/pretrain.py).

## Additional Considerations
```Feature Extraction```: Ensure your model is capable of extracting relevant features from news audio, as news audio might have different characteristics compared to music.

```Labeling```: Make sure your dataset is accurately labeled with the 'anchor', 'interview', and 'debate' tags.

```Task-Specific Configurations```: Adjust model configurations and hyperparameters according to the characteristics of your dataset and task.

