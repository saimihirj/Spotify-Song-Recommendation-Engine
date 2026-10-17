# Spotify Song Recommendation Engine

A Streamlit app that recommends songs from the Spotify catalogue based on the mood and sound you choose. Pick a genre, a range of release years and target values for six audio features (acousticness, danceability, energy, instrumentalness, valence and tempo), and the app returns the closest matching tracks, each with a playable Spotify embed and a polar chart of its audio profile.

## How it works

The app filters the catalogue to the chosen genre and years, keeps the 500 most popular tracks, and ranks them by distance to your target audio profile with a k-nearest-neighbours model (scikit-learn). Results load six at a time.

The data covers 9,460 tracks released between 1990 and 2019 across eleven genres (dance pop, electronic, electropop, hip hop, jazz, K-pop, Latin, pop, pop rap, R&B and rock). It was built from the SpotGenTrack dataset by joining track, artist and album tables, keeping tracks released from 1990 onward and filtering to these genres; `data/preprocess_data.ipynb` shows the steps.

## Running it

Requires Python 3.11 or later.

```bash
pip install -r requirements.txt
streamlit run app.py
```

The app opens at `http://localhost:8501`.

## Files

| File | Contents |
|---|---|
| `app.py` | The Streamlit app |
| `data/filtered_track_df.csv` | Track metadata and audio features used by the app |
| `data/preprocess_data.ipynb` | Notebook that built the dataset from SpotGenTrack |
| `requirements.txt` | Python dependencies |

## License

MIT. See [LICENSE](LICENSE).
