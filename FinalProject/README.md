DAT6 final project: &#9835; Music Science! &#9835;
=======
Cory Kendrick
--------------

**Objective**: 
Investigate music listening habits, and identify which features of music listening (at the user level) explain the variance between users.
Or, what factors -- if any -- can predict artist or song popularity before it happens. 


**Methods**: 
* PCA: Feature reduction: which factors are most explanatory of variance?
* PCA: Feature selection: which features to put into regression model?
* Regression: how do certain attributes of a track (X: artist, length, year released, popularity) affect users' chosen genre (y = genres)
* Clustering/User Segmentation: segment users based on listening history

**Datasets**:
* `millionsongsubset_full` (1.9GB 10K song subset of the Million Song Dataset)
* `artist_similarity.db` (321 MB SQLite database of artist similarity)
* `msd_summary_file.h5` (301MB summary of what's in the dataset)
* **TODO** Last.FM API export (my personal listening history since 2005)
* **TODO** EchoNest API export (for additional features not included below)

**More about the _Million Song Dataset_:**

| FIELD NAME                  | TYPE           | DESCRIPTION                                   |
|-----------------------------:|:----------------:|-----------------------------------------------:|
| analysis sample rate        | float          | sample rate of the audio used                 |
| artist 7digitalid           | int            | ID from 7digital.com or -1                    |
| artist familiarity          | float          | algorithmic estimation                        |
| artist hotttnesss           | float          | algorithmic estimation                        |
| artist id                   | string         | Echo Nest ID                                  |
| artist latitude             | float          | latitude                                      |
| artist location             | string         | location name                                 |
| artist longitude            | float          | longitude                                     |
| artist mbid                 | string         | ID from musicbrainz.org                       |
| artist mbtags               | array string   | tags from musicbrainz.org                     |
| artist mbtags count         | array int      | tag counts for musicbrainz tags               |
| artist name                 | string         | artist name                                   |
| artist playmeid             | int            | ID from playme.com, or -1                     |
| artist terms                | array string   | Echo Nest tags                                |
| artist terms freq           | array float    | Echo Nest tags freqs                          |
| artist terms weight         | array float    | Echo Nest tags weight                         |
| audio md5                   | string         | audio hash code                               |
| bars confidence             | array float    | confidence measure                            |
| bars start                  | array float    | beginning of bars, usually on a beat          |
| beats confidence            | array float    | confidence measure                            |
| beats start                 | array float    | result of beat tracking                       |
| danceability                | float          | algorithmic estimation                        |
| duration                    | float          | in seconds                                    |
| end of fade in              | float          | seconds at the beginning of the song          |
| energy                      | float          | energy from listener point of view            |
| key                         | int            | key the song is in                            |
| key confidence              | float          | confidence measure                            |
| loudness                    | float          | overall loudness in dB                        |
| mode                        | int            | major or minor                                |
| mode confidence             | float          | confidence measure                            |
| release                     | string         | album name                                    |
| release 7digitalid          | int            | ID from 7digital.com or -1                    |
| sections confidence         | array float    | confidence measure                            |
| sections start              | array float    | largest grouping in a song, e.g. verse        |
| segments confidence         | array float    | confidence measure                            |
| segments loudness max       | array float    | max dB value                                  |
| segments loudness max time  | array float    | time of max dB value, i.e. end of attack      |
| segments loudness max start | array float    | dB value at onset                             |
| segments pitches            | 2D array float | chroma feature, one value per note            |
| segments start              | array float    | musical events, ~ note onsets                 |
| segments timbre             | 2D array float | texture features (MFCC+PCA-like)              |
| similar artists             | array string   | Echo Nest artist IDs (sim. algo. unpublished) |
| song hotttnesss             | float          | algorithmic estimation                        |
| song id                     | string         | Echo Nest song ID                             |
| start of fade out           | float          | time in sec                                   |
| tatums confidence           | array float    | confidence measure                            |
| tatums start                | array float    | smallest rythmic element                      |
| tempo                       | float          | estimated tempo in BPM                        |
| time signature              | int            | estimate of number of beats per bar, e.g. 4   |
| time signature confidence   | float          | confidence measure                            |
| title                       | string         | song title                                    |
| track id                    | string         | Echo Nest track ID                            |
| track 7digitalid            | int            | ID from 7digital.com or -1                    |
| year                        | int            | song release year from MusicBrainz or 0       |

Dataset citation:
Thierry Bertin-Mahieux, Daniel P.W. Ellis, Brian Whitman, and Paul Lamere. 
The Million Song Dataset. In Proceedings of the 12th International Society
for Music Information Retrieval Conference (ISMIR 2011), 2011.