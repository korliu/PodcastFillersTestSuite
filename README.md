###### Korey Liu, koreyliu@buffalo.edu

Google Drive Zip File download: https://drive.google.com/file/d/1ttgKLtobJsCHrVfut6YQ9IAXnVkRX9cA/view?usp=sharing

#### Dataset created using resources:
1. Description on PodcastFillers data: https://podcastfillers.github.io/dataset/
2. Paper on how dataset was created: https://arxiv.org/pdf/2203.15135.pdf
3. PodcastFillers Dataset downloaded from: https://zenodo.org/record/7121457#.Y0bzKezMKdY

### Total 197 podcast data:

- `test` Folder contains **20** podcasts
- `train` Folder contains **171** podcasts; 2 podcasts from the original dataset were removed from this split folder
- `validation` Folder contains **6** podcasts

#### Each split folder ("test", "train", "validation") contains the same format of information:
    [split_folder]: 
        [podcast_name]
            ["audio"]
                audio files folder; segmented based on start and end times of each segment
                "{segment_id}.wav" files
            ["transcript.csv"]
                - segmented transcriptions (with "Uh"s and "Um"s) of the podcast
                Headers:
                    "segment_id": id of segment; audio file = "./audio/{segment_id}.wav"
                    "language": language of segment
                    "start_time": time (in seconds) at which the segment recording starts
                    "duration": length (in seconds) of the segment recording
                    "text_with_NSS": transcription of segment, NSS included. Not 100% accurate as the transcription of the podcast episode was generated with SpeechMatics STT API
                    "avg_confidence": the average confidence of the words in the {text_with_NSS}. NSS words were manually annotated, so only non-NSS words had a confidence value
                    "median_confidence": median confidence of the words in the {text_with_NSS}.


#### Two podcasts were skipped, csv reader could not read them, I think their path names are too long:
    ./podcast_fillers_data/PodcastFillers/metadata/episode_annotations/train/FLY Travel Radio, with Melissa Rodway_FLY Travel Radio Episode 170 7+Yrs, Every Country, No Planes. Thor Pedersen, Once Upon A Saga.csv
    ./podcast_fillers_data/PodcastFillers/metadata/episode_annotations/train/Livin That Life – Digital Nomad Podcast_Boss Girl Entrepreneur Stories–Breaking Free, Solo Travel & Online Business– Female Digital Nomad.csv
