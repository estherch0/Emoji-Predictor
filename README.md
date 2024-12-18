# Bridging Text and Emotion: An Emoji Prediction Model
For our project, we created a model that translates textual sentiment into a corresponding emoji. To build and evaluate the model, we utilized tweet data from Twitter, now known as X. We created and compared three different models to determine which would perform best: a Support Vector Machine (SVM), a BERT Sequence Classification model, and a Distilled BERT Sequence Classification model. Each model was chosen based on its ability to process languages and capture the contextual meaning behind words.

## Description of the files
* The `data` folder contains the 42 CSV emoji files that we sourced from [Kaggle](https://www.kaggle.com/datasets/ericwang1011/tweets-with-emoji/data). Each file has tweets that correspond to the emoji mentioned in the CSV's title.
* The `emoji_map.csv` file contains the emoji mapping data from the [Amsterdam University of Applied Sciences](https://uvaauas.figshare.com/articles/dataset/Twemoji_Dataset/5822100). It has data on the description of each emoji as well as its ucode.
* The `Preprocessing.ipynb` file contains code for how we merged the datasets together and cleaned the data. Running this file will create the `merged_emoji_data.csv` file locally.
  * `merged_emoji_data.csv` is the final cleaned dataset that was used to train our models. It merges all of the data from the `data` folder as well as from `emoji_map.csv`.
* The `SVM.ipynb` file contains code for our SVM model.
* The `BertForSequenceClassification.ipynb` file contains code for our BERT Sequence Classification model.
* The `DistilBertForSequenceClassification.ipynb` file contains code for our Distilled BERT Sequence Classification model.

## Running the project
1. Download all of the files in the GitHub repository.
2. Navigate to the `Preprocessing.ipynb` file. Run each cell in this file. This should create the `merged_emoji_data.csv` file locally on your computer. You will use `merged_emoji_data.csv` as the main dataset for the next steps.
3. Navigate to the `SVM.ipynb` file. Run each cell in this file. This should process all of the data from `merged_emoji_data.csv`, split the data into training and testing datasets, and run the SVM model. It will output an accuracy for the results of the model. You can add more sentences to the `new_texts` list in the last cell of the file if you would like a demonstration of how the SVM model works. Running the last cell will output predicted emojis for every sentence in `new_texts`.
4. Navigate to the `BertForSequenceClassification.ipynb` file. Run each cell in this file. This should process all of the data from `merged_emoji_data.csv`, split the data into training and testing datasets, tokenize the data, and run the BERT Sequence Classification model. It will output an accuracy after every iteration of an epoch. You can add more sentences to the `new_texts` list in the last cell of the file if you would like a demonstration of how the BERT Sequence Classification modelworks. Running the last cell will output predicted emojis for every sentence in `new_texts`.
5. Navigate to the `DistilBertForSequenceClassification.ipynb` file. Run each cell in this file. This should process all of the data from `merged_emoji_data.csv`, split the data into training and testing datasets, tokenize the data, and run the Distilled BERT Sequence Classification model. It will output an accuracy after every iteration of an epoch. You can add more sentences to the `new_texts` list in the last cell of the file if you would like a demonstration of how the Distilled BERT Sequence Classification model works. Running the last cell will output predicted emojis for every sentence in `new_texts`.

## References for Code
### SVM
- https://takelab.fer.hr/podium/examples/tfidf_example.html
- https://machinelearningmastery.com/one-vs-rest-and-one-vs-one-for-multi-class-classification/
### BERTForSequenceClassification 
- https://huggingface.co/transformers/v3.3.1/training.html
- https://huggingface.co/docs/transformers/v4.47.1/en/model_doc/bert#transformers.BertForSequenceClassification
### DistilledBERTForSequenceClassification 
- https://huggingface.co/docs/transformers/v4.47.1/en/model_doc/distilbert#transformers
- https://www.analyticsvidhya.com/blog/2022/11/introduction-to-distilbert-in-student-model/

Note: Utilized ChatGPT for initial hyperparameters, and further debugging
