# Day 8: Recurrent Neural Networks (RNNs) & LSTMs
## Concepts
- Sequential data & time series.
- RNN structure, vanishing gradient.
- LSTM and GRU for long-term memory.

## Analogy
RNNs are like remembering previous words while speaking.

## Practical Exercise
- Train an LSTM on text data for next word prediction.

## Example Code
```python
import tensorflow as tf
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense, Embedding
from tensorflow.keras.preprocessing.sequence import pad_sequences
from tensorflow.keras.preprocessing.text import Tokenizer
import numpy as np

data = "robot moves forward robot turns left robot moves right robot stops"
tokens = data.split()
tokenizer = Tokenizer()
tokenizer.fit_on_texts([data])
seqs = []
for i in range(1, len(tokens)):
    seqs.append(tokenizer.texts_to_sequences([' '.join(tokens[:i+1])])[0])

max_len = max(map(len, seqs))
seqs = pad_sequences(seqs, maxlen=max_len, padding='pre')
X, y = seqs[:,:-1], seqs[:,-1]
vocab_size = len(tokenizer.word_index) + 1

model = Sequential([
    Embedding(vocab_size, 10, input_length=max_len-1),
    LSTM(50),
    Dense(vocab_size, activation='softmax')
])
model.compile(loss='sparse_categorical_crossentropy', optimizer='adam', metrics=['accuracy'])
model.fit(X, y, epochs=200, verbose=0)
```
