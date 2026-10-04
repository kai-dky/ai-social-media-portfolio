# Will This Game Be a Hit?

## Explaining and Predicting Video Game Review Scores Using Machine Learning

## Project Overview

This team project explored whether video game review scores could be explained and predicted using review sentiment, game attributes, and developer-region information.

We collected critic and user reviews from Metacritic, applied sentiment analysis with gaming-specific language adjustments, identified sentiment across 12 game-related aspects, and built a regression model to predict review scores.

- **Project Type:** Team Data Science Project
- **Course:** USC DSCI 510 — Principles of Programming for Data Science
- **Team Members:** Kaiyue Deng and Yuhan Wang
- **Original Team Repository:** [USC-DSCI510-Final-Project](https://github.com/ywang204/USC-DSCI510-Final-Project)

> **Team Attribution:** This project was completed collaboratively by Kaiyue Deng and Yuhan Wang. Both team members worked together throughout the research, data collection, analysis, modeling, visualization, and reporting process rather than dividing the project into isolated individual sections. The original repository is maintained under Yuhan Wang’s GitHub account.

---

## Research Questions

The project focused on three main questions:

1. Can sentiment expressed in critic and user reviews help explain a game’s final review score?
2. Which aspects—such as story, gameplay, visuals, or audio—have the strongest relationship with review scores?
3. Can review sentiment and developer-region information be combined to predict game ratings?

---

## Dataset

The final dataset contained:

- **259 video games**
- **1,553 total reviews**
- **909 critic reviews**
- **644 user reviews**

The collected information included:

- Game title and platform
- Developer and publisher
- Critic and user scores
- Critic and user review text
- Developer and publisher region
- Aspect-based sentiment scores

Game titles were collected using a custom web crawler, followed by requests to the Metacritic API for detailed review information.

---

## Project Workflow

### 1. Data Collection

We collected game titles and review data from Metacritic using Python, web scraping, and API requests.

### 2. Data Cleaning

We cleaned and tokenized the review text, handled missing values, and removed game-title words from reviews to reduce sentiment distortion.

### 3. Sentiment Analysis

We used VADER sentiment analysis and supplemented its standard lexicon with gaming-specific language corrections.

This adjustment improved the correlation between sentiment and review scores from approximately **0.144 to 0.162**.

### 4. Aspect-Based Analysis

Reviews were analyzed across 12 game-related aspects, including:

- Story and narrative
- Gameplay mechanics
- Visuals and graphics
- Audio and music
- Controls and camera
- Multiplayer features
- Monetization

### 5. Exploratory Data Analysis

We compared review scores across developer and publisher regions and examined how critics and users emphasized different aspects of a game.

### 6. Predictive Modeling

We built a linear regression model combining:

- Aspect-based sentiment scores
- Developer-region information
- Developer and publisher characteristics

After filtering reviews without usable sentiment signals and addressing major residual outliers, the optimized model achieved:

- **RMSE: 9.12**
- **R²: 0.7350**

---

## Key Findings

- **Story and narrative sentiment** showed one of the strongest relationships with review scores, with a correlation of approximately **0.53**.
- **Gameplay mechanics sentiment** also showed a strong relationship, with a correlation of approximately **0.49**.
- Developer region appeared more informative than publisher region in the analyzed sample.
- Games developed in Japan showed a higher score distribution in this dataset, although this finding should not be interpreted as causal.
- Critics and users placed different levels of emphasis on areas such as gameplay, controls, multiplayer experience, and monetization.
- Gaming-specific sentiment adjustments improved the usefulness of general-purpose sentiment analysis.

---

## Challenges and Solutions

### Gaming-Specific Language

Words commonly used in gaming reviews may carry meanings that differ from their general-language sentiment.

**Solution:** We created gaming-domain sentiment corrections to improve VADER’s interpretation of review language.

### Reviews Without Clear Sentiment Signals

Some reviews contained little usable sentiment information, which weakened the initial model.

**Solution:** We filtered reviews without meaningful sentiment signals and examined model residuals before rebuilding the model.

### Regional Imbalance

The dataset did not contain equal numbers of games from every developer region.

**Solution:** We treated regional findings as exploratory correlations and clearly documented the limitation.

---

## Tools and Technologies

- Python
- pandas
- requests
- BeautifulSoup
- NLTK and VADER
- scikit-learn
- Matplotlib
- seaborn
- Jupyter Notebook

---

## Relevance to Social Media and Content Optimization

Although this project focused on video game reviews, the analytical workflow can also support social media strategy:

- Converting audience feedback into measurable sentiment signals
- Identifying which content or product aspects drive positive reactions
- Comparing the priorities of different audience segments
- Using data to explain performance instead of relying only on intuition
- Translating analytical results into clear recommendations and reports

These skills are relevant to social media performance analysis, audience research, content testing, and data-driven optimization.

---

## Supporting Materials

- [Original Team Repository](https://github.com/ywang204/USC-DSCI510-Final-Project)
- [Final Project Report](./final-report.pdf)

---

## Limitations and Future Improvements

Future versions of the project could:

- Expand the number and diversity of games
- Improve regional balance within the dataset
- Use more advanced aspect-extraction methods
- Compare linear regression with nonlinear models such as Random Forest
- Collect review data across multiple platforms rather than relying on one source
