# Neural Machine Translation (NMT) - English to German

This project trains a sequence-to-sequence neural machine translation model to translate English text to German. 
The notebook `NMT-English_ to _German_200epochs.ipynb` is used to showcase this demonstration

## Model Architecture
The model consists of an encoder LSTM layer and a decoder LSTM layer with 256 hidden units each. Dropout of 0.3 is used in both LSTM layers to prevent overfitting.
The encoder LSTM encodes the German input text into a 256-dimensional vector representation, and the decoder LSTM is initialized with this vector to generate the English translation word by word.

## Training Data 

The model is trained on the first 25,000 sentence pairs from the deu-eng dataset containing German to English translations. 
The texts are preprocessed and converted to integer sequences using vocabulary dictionaries of the unique input and output tokens.
The model is trained for 200 epochs with a batch size of 64. RMSprop optimizer and categorical cross entropy loss are used. 
Validation split of 20% is used as well as TensorBoard logs for tracking training progress.

## Preprocessing
The texts are preprocessed by:
- Cleaning and tokenization
- Creating vocabularies and one-hot encodings for the input and target texts 
- Padding the input sequences

## Model Training
The model is trained for 200 epochs with a batch size of 64. RMSprop optimizer and categorical cross entropy loss are used.

After 200 epochs:
- Training Accuracy: 82%
- Validation Loss: 29%

## Evaluation
- A validation split of 20% is used during training to monitor overfitting
- BLEU score can be used to evaluate the translation quality

## Inference
An inference function is created to map the input english text to decoded german text using the trained models. 

## Future Work
There is scope for improvement with hyperparameter tuning, using more data, and experimenting with deeper models. Attention mechanism can also be added to potentially improve translation quality.

## Usage
The model can be used by calling the `decode_sequence` method and passing the input text to get the german translation.
