# BERT_SentimentClassifier
Movie review classifier using BERT. Finetuning on a BERT model to add the functionality of classifying movie reviews as positive or negative.

OVERVIEW
- Dataset: An IMDB dataset is used with reviews classified as positive and negative.
- Results: The trained model achieves accuracy in classifying sentiments in reviews.
- BERT model: We implement a pre-trained BERT model and fine-tune it to the IMDB dataset.
- Application: The model can be used to automatically analyze sentiments in new reviews, providing valuable insights for decision making

DATASET IMDB
The IMDB review dataset is a widely used dataset in the natural language processing and sentiment analysis community.
- Content: The IMDB dataset contains opinions or reviews of movies extracted from the IMDb (Internet Movie Database) website.
- Rating: Each review is labeled as positive or negative depending on the opinion expressed by the author.
- Text: Reviews are made up of free text, where users express their opinions about movies, including details about plot, acting, direction, etc.
- Variety of genres: The dataset covers a wide spectrum of film genres, ensuring a diversity of opinions and writing styles.

BERT MODEL
BERT, which stands for "Bidirectional Encoder Representations from Transformers", is a language model developed by Google. It is a transformer-based neural network architecture, which has demonstrated exceptional performance in a wide range of natural language processing (NLP) tasks.
1. Bidirectional pre-training: BERT is trained bidirectionally on large amounts of text, meaning it can understand context both before and after a word in a sentence. This allows you to capture more complex relationships in the text.
2. Contextualized Representations: BERT generates vector representations for each word based on its context in the sentence. This means that the representation of a word can vary depending on its meaning in different contexts, which improves understanding of the meaning of the word.
3. Capacity for transfer learning tasks: BERT has proven to be highly effective in a wide range of NLP tasks, including text classification, information extraction, question answering, machine translation, among others. This is due to its ability to capture contextualized information and its ability to perform transfer learning, where the pre-trained model is fine-tuned for specific tasks with smaller, labeled data sets.
4. Common use: BERT is widely used in industry and research for a variety of natural language processing applications, such as sentiment analysis, text classification, text generation, information extraction, among others. Its ability to capture complex contexts and its adaptability to different tasks make it a powerful tool in the field of NLP.

LAYER DESCRIPTION

1. Input: The input to the model is the IDs of the review tokens and an attention mask to indicate which parts are real tokens and which are filler.
2. Embedding Layer: Transforms token IDs into embedding vectors.
3. BERT Model: Uses the pre-trained BERT model to obtain representations
contextualized tokens.
4. Dropout: Dropout layer that helps prevent overfitting by randomly shutting down
some neurons during training.
5. Conv1d Layer: 1D convolutional layer that searches for local features in the sequence
of tokens.
6. ReLU Activation: ReLU activation function applied after convolution to
introduce non-linearities.
7. MaxPool1d Layer: Pooling layer that extracts the most important characteristics of the
sequence.
8. Linear Layer: Linear layer that maps the extracted features to the labels of
classification of feelings (positive or negative).
9. Logits (Output): The final outputs of the model, which represent the predictions of
classification of feelings.

This model uses the output of the BERT pooler as input to a 1D convolutional layer followed by a linear layer to perform sentiment classification.

LOSS AND ACCURACY
After training for about 4 hours on a corpus of about 2000 comments... The Loss and Accuracy curves do not present good results.
Even with the Dropout layer and the L2 regularization that has been introduced, we can see in the Accuracy curve that the model presents overfitting.

CONCLUSIONS

- BERT models with Finetuning can be a good review classifier, but it would be necessary to increase the corpus significantly.
- Several tests have been carried out such as adding new convolution layers or L1 and L2 regularization and it has been verified that there were no improvements after their execution. It is suspected that the solution is to increase the input corpus.
- An execution of a larger corpus could not be carried out due to computing time problems
