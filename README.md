# Disaster-Tweets
#Data Preparation
# 1. Data Loading and Preprocessing
df = pd.read_csv(r"/content/train.csv")

# Handling missing values with imputation
imputer = SimpleImputer(strategy='most_frequent')  # Replace with your preferred strategy
df[['keyword', 'location']] = imputer.fit_transform(df[['keyword', 'location']])

stop_words = set(stopwords.words('english'))
lemmatizer = WordNetLemmatizer()

def preprocess_text(text):
    if isinstance(text, str):
        text = re.sub(r'[^a-zA-Z\s]', '', text)  # Remove non-alphanumeric characters
        text = text.lower()
        tokens = nltk.word_tokenize(text)
        tokens = [lemmatizer.lemmatize(token) for token in tokens if token not in stop_words]  # Lemmatization
        return tokens
    else:
        return []

df['processed_text'] = df['text'].apply(preprocess_text)
