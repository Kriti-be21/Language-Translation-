# Language-Translation

1. **Data Preparation:**
   - English and Italian parallel text data is loaded from a file ('ita.txt') and split into training and testing sets.
   - Preprocessing includes lowercasing, punctuation removal, and tokenization.

2. **Tokenization and Padding:**
   - Tokenizers are created for English and Italian text.
   - English and Italian sentences are tokenized and padded to prepare them for model input.

3. **Model Architecture:**
   - The seq2seq model consists of an encoder and a decoder.
   - The encoder processes English input sequences and produces hidden states.
   - The decoder takes these hidden states and generates Italian output sequences.
   - Word embeddings and GRU layers are used in both encoder and decoder.

4. **Training:**
   - The model is trained using the training data with teacher forcing.
   - The training involves minimizing the sparse categorical crossentropy loss.
   - The trained model is saved for later use.

5. **Inference:**
   - During inference, the trained model is used to generate Italian translations for English sentences.
   - The encoder encodes the input sequence, and the decoder generates the output sequence word by word.
   - The decoding process continues until the end token is predicted or a maximum length is reached.

6. **Embedding Extraction:**
   - The original encoder's embedding (before being updated by the decoder) is saved for potential use in other tasks.

7. **Decoding Loop:**
   - A decoding loop is implemented to generate Italian translations.
   - The loop predicts the next word, updates the hidden state, and continues until a stopping condition is met.

8. **Summary Output:**
   - The final Italian translation is stored in the `decoded_sentence` variable.

Overall, this project involves training a seq2seq model for English to Italian translation, saving the trained model, and using it for inference to generate translations. Additionally, it captures the original embedding of the English input for potential use in other tasks.
