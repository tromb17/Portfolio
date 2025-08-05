# Toxic Comments Classification for Wikishop

## Project Description

Internet store "Wikishop" is launching a new service where users can edit and supplement product descriptions, similar to wiki communities. Clients can suggest edits and comment on changes made by others. The store needs a tool to detect toxic comments and send them for moderation.

The goal is to train a model to classify comments as positive or negative. We have a labeled dataset indicating comment toxicity. The model must achieve an F1 score of at least 0.75.

## Data Overview

The dataset contains:
- **159,292 entries** with two columns: `text` (comment) and `toxic` (binary label: 1 for toxic, 0 for non-toxic).
- Class imbalance: ~10% toxic comments, 90% non-toxic.

## Data Preprocessing

1. **Text Cleaning**:
   - Converted to lowercase.
   - Removed special characters and extra spaces.
   - Kept only letters and apostrophes.

2. **Lemmatization**:
   - Used NLTK and WordNetLemmatizer to reduce words to their base forms.
   - Applied part-of-speech tagging for accurate lemmatization.

3. **Train-Test Split**:
   - Divided into 90% training and 10% test sets.

4. **Feature Extraction**:
   - Used TF-IDF vectorization with stopwords removal.
   - Focused on unigrams (single words).

## Model Training and Evaluation

Three models were trained and evaluated:

### 1. Logistic Regression
- **Best Parameters**: `C=9`, `penalty='l2'`.
- **F1 Score**: **0.78** (exceeds the target of 0.75).
- **Training Time**: ~3 minutes.

### 2. Random Forest
- **Best Parameters**: `n_estimators=10`, `max_depth=None`.
- **F1 Score**: 0.65 (below target).
- **Training Time**: ~1.7 minutes.

### 3. CatBoost
- **Best Parameters**: `iterations=10`, `learning_rate=0.1`, `depth=3`.
- **F1 Score**: 0.41 (below target).
- **Training Time**: ~52 seconds per fold.

## Results

The **Logistic Regression** model performed best, achieving an F1 score of **0.78** on the test set, meeting the project requirement. This model was selected for deployment due to its balance of performance and efficiency.
