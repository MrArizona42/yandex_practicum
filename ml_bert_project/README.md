# Семантический анализ текстов - поиск токсчиных комментариев

## Описание проекта

У некоторой организации существует поток комментариев от пользователей на одном интернет ресурсе. Необходимо автоматизировать поиск токсичных комметрариев для последующей отправки их на модерацию.

## Используемые инструменты

* numpy
* pandas
* matplotlib.pyplot
* WordCloud

**ML-операции**
* Pipeline
* train_test_split
* LogisticRegression
* GridSearchCV
* tqdm

**Работа с текстом**
* nltk
* spacy
* TfidfVectorizer
* torch
* transformers: BertModel, BertTokenizer

## Общий вывод

**TF-IDF пайплайн:**
1. Токенизация: WordNetLemmatizer и SpaCy.
2. TF-IDF векторизация
3. Обучение модели - Линейная регрессия
4. Подбор порога

Результат: F1 = 0.84

**Bert model пайплайн**
1. Токенизация: `transformers.AutoTokenizer.from_pretrained('unitary/toxic-bert')`
2. Получение эмбеддингов: `transformers.AutoModel.from_pretrained('unitary/toxic-bert')`
3. Обучение модели - Линейная регрессия
4. Подбор порога

Обучение проводилось на локальном GPU NVidia RTX3060 на неполных данных: 30000 комментариев.

Результат: F1 = 0.95

Результат с Bert на тесте: F1 = 0.95