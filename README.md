# Instagram Comment Sentiment Analysis

A Natural Language Processing (NLP) project that analyzes sentiment in Instagram comments using VADER (Valence Aware Dictionary and sEntiment Reasoner). This project processes thousands of Instagram comments to determine whether they express positive, negative, or neutral sentiment.

## Overview

This project performs comprehensive sentiment analysis on Instagram comments by:
- Cleaning and preprocessing text data
- Removing stopwords and performing lemmatization
- Applying VADER sentiment analysis
- Visualizing sentiment distribution
- Generating detailed reports

## Features

- **Data Preprocessing**: Handles missing values, converts text to lowercase, removes punctuation and numbers
- **NLP Processing**:
  - Stopword removal
  - Lemmatization (converting words to root forms)
  - URL and mention removal
  - Whitespace normalization
- **Sentiment Analysis**: Uses VADER (Valence Aware Dictionary and sEntiment Reasoner) for accurate social media text analysis
- **Visualization**: Creates professional bar charts showing sentiment distribution
- **Export Results**: Saves processed data and analysis results to CSV files

## Technologies Used

- **Python 3.7+**
- **pandas**: Data manipulation and analysis
- **NLTK**: Natural Language Toolkit for text processing
- **VADER Sentiment**: Lexicon-based sentiment analysis
- **Matplotlib**: Data visualization

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd NLP-project
```

### 2. Create a virtual environment (recommended)

```bash
# Windows
python -m venv myenv
myenv\Scripts\activate

# macOS/Linux
python3 -m venv myenv
source myenv/bin/activate
```

### 3. Install required packages

```bash
pip install -r requirements.txt
```

### 4. Download NLTK data

Run these commands in Python or in the first cell of the notebook:

```python
import nltk
nltk.download('stopwords')
nltk.download('wordnet')
```

## Usage

### Running the Jupyter Notebook

1. Launch Jupyter Notebook:
```bash
jupyter notebook
```

2. Open `Comment sentiment NLP project.ipynb`

3. Run all cells sequentially or use "Run All" from the Cell menu

### Input Data

The project expects an input file named `instagram_comments.csv` with the following columns:
- `created_at`: Timestamp of the comment
- `text`: The comment text
- `username`: Username of the commenter

### Output Files

The notebook generates several output files:

1. **cleaned_instagram_comments.csv**: Preprocessed comments ready for analysis
2. **null_comments_trum_14k.csv**: Comments with missing values (for reference)
3. **sentiment_analysis_results_after.csv**: Complete sentiment analysis results including:
   - Original and cleaned text
   - Positive, neutral, negative scores
   - Compound sentiment score
   - Sentiment label (Positive/Negative/Neutral)
4. **sentiment_distribution_plot.png**: Visualization of sentiment distribution

## Project Structure

```
NLP-project/
│
├── Comment sentiment NLP project.ipynb    # Main Jupyter notebook
├── requirements.txt                        # Python dependencies
├── README.md                               # Project documentation
├── instagram_comments.csv                  # Input data (not included)
├── ig_comm_14k.xlsx                       # Alternative input format
│
├── cleaned_instagram_comments.csv         # Generated: Preprocessed data
├── null_comments_trum_14k.csv            # Generated: Null value records
├── sentiment_analysis_results_after.csv  # Generated: Analysis results
├── sentiment_distribution_plot.png       # Generated: Visualization
└── analysis result plot.png              # Generated: Result plot
```

## Sentiment Analysis Methodology

### VADER Sentiment Scores

The project uses VADER, which provides four sentiment scores:

1. **Positive (pos)**: Proportion of text that is positive (0-1)
2. **Neutral (neu)**: Proportion of text that is neutral (0-1)
3. **Negative (neg)**: Proportion of text that is negative (0-1)
4. **Compound**: Normalized composite score (-1 to 1)

### Classification Thresholds

Comments are classified based on the compound score:
- **Positive**: compound score > 0.05
- **Negative**: compound score < -0.05
- **Neutral**: -0.05 ≤ compound score ≤ 0.05

## Data Preprocessing Pipeline

1. **Load Data**: Import Instagram comments from CSV
2. **Remove Unnecessary Columns**: Drop timestamp column
3. **Handle Missing Values**: Identify and remove null entries
4. **Text Normalization**: Convert to lowercase
5. **Clean Text**: Remove punctuation and numbers
6. **Remove Stopwords**: Filter out common English words
7. **Lemmatization**: Convert words to base forms
8. **Remove URLs/Mentions**: Clean social media artifacts
9. **Normalize Whitespace**: Standardize spacing

## Results

The analysis processes approximately 14,000+ Instagram comments and provides:
- Distribution of positive, negative, and neutral sentiments
- Detailed sentiment scores for each comment
- Visual representation of overall sentiment trends
- Statistical insights into comment patterns

## Example Results

Based on the sample dataset:
- Total comments analyzed: ~14,207 (after cleaning)
- Sentiment distribution visualization available in output plot
- Detailed per-comment analysis in results CSV

## Future Improvements

- [ ] Add support for multiple languages
- [ ] Implement additional sentiment analysis models (TextBlob, Transformers)
- [ ] Create interactive dashboard for real-time analysis
- [ ] Add word cloud generation for positive/negative comments
- [ ] Implement topic modeling to identify common themes
- [ ] Add time-series analysis for sentiment trends
- [ ] Create comparison between different posts or accounts

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is available for educational and research purposes.

## Acknowledgments

- VADER Sentiment Analysis: Hutto, C.J. & Gilbert, E.E. (2014). VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text. Eighth International Conference on Weblogs and Social Media (ICWSM-14).
- NLTK: Natural Language Toolkit for Python
- Instagram comment data source: [Specify your data source]

## Contact

For questions or feedback, please open an issue in the repository.

---

**Note**: This project is for educational and research purposes. Ensure you have proper authorization before collecting and analyzing social media data. Respect user privacy and platform terms of service.
