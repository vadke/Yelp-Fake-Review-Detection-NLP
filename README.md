# ⭐ Yelp Fake Review Detection System (NLP)

## 📌 Business Overview
In the digital economy, consumer trust is currency. However, fake or "astroturfing" reviews threaten the integrity of platforms like Yelp. 
This project develops an automated **Fraud Detection Engine** that processes unstructured text data to identify and flag suspicious review patterns before they damage business reputations.

## 🧠 Technical Approach
This solution moves beyond simple keyword matching by using **Semantic Analysis** and **Machine Learning**.

### 1. NLP & Feature Engineering
* **Sentiment Analysis:** Used **NLTK VADER** and **TextBlob** to calculate polarity scores. We hypothesized that fake reviews often have "extreme" sentiment (pure 1.0 or -1.0) compared to nuanced real reviews.
* **Text Mining:** Analyzed review length, word count, and vocabulary richness.

### 2. Anomaly Detection (Unsupervised)
Since "Fake Reviews" are rare events (class imbalance), we used outlier detection techniques:
* **Isolation Forest:** Efficiently isolates anomalies by randomly partitioning data points.
* **One-Class SVM:** Maps data into a high-dimensional space to find the boundary of "normal" behavior.

### 3. Classification (Supervised)
* **XGBoost:** Trained on the anomalies identified above to create a predictive model for future reviews.
* **Performance:** Achieved **99% Accuracy** and **0.99 F1-Score**.

## 📊 Key Insights
* **The "Short & Extreme" Pattern:** The majority of flagged reviews were unusually short (<15 words) and had a sentiment polarity of exactly +1.0 or -1.0.
* **Campaign Clusters:** Suspicious reviews often appeared in "bursts" targeting specific businesses, suggesting coordinated campaigns.
* **Moderation Efficiency:** The model successfully filtered out the **8.3%** of reviews that required manual human review, saving moderators 90%+ of their time.

## 🛠 Tools Used
* **Python:** NLTK, TextBlob, Scikit-Learn, XGBoost
* **Visualization:** Plotly, Seaborn, Matplotlib
* **Dashboard:** Ipywidgets (for interactive filtering)

## 🚀 How to Run
1.  Clone the repository.
2.  Install dependencies: `pip install -r requirements.txt`
3.  Run `Project_FinalCode_Team05.ipynb`.
