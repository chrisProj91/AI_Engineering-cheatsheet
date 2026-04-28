# Deep Learning

## 1. What is Deep Learning?

Deep Learning is a subset of Machine Learning that uses neural networks with many layers to learn complex patterns from data.

It excels at:
- Images
- Text
- Audio
- Video
- Complex patterns

---

## 2. Neural Networks Basics

A neural network is composed of layers of interconnected neurons.

### Structure:
- Input Layer
- Hidden Layers
- Output Layer

Each connection has:
- Weight (importance)
- Bias (offset)

---

## 3. The Neuron

A neuron computes:

z = w·x + b
a = activation(z)


Where:
- x = inputs
- w = weights
- b = bias
- a = output

---

## 4. Activation Functions

Introduce non-linearity.

### 4.1 ReLU (Most Common)

f(x) = max(0, x)


Pros:
- Simple
- Fast
- Works well in practice

---

### 4.2 Sigmoid

f(x) = 1 / (1 + e^-x)


Range: (0, 1)

---

### 4.3 Tanh

f(x) = tanh(x)


Range: (-1, 1)

---

### 4.4 Softmax

Used for multi-class classification:

softmax(x_i) = e^{x_i} / Σ e^{x_j}


---

## 5. Forward Propagation

Data flows from input → output:

1. Multiply inputs by weights
2. Add bias
3. Apply activation
4. Repeat layer by layer

---

## 6. Loss Functions

Measure prediction error.

### Common:

#### Classification:
- Binary Cross Entropy
- Categorical Cross Entropy

#### Regression:
- MSE
- MAE

---

## 7. Backpropagation

Algorithm to compute gradients of loss w.r.t weights.

Steps:
1. Compute loss
2. Propagate error backward
3. Update weights

---

## 8. Gradient Descent in Deep Learning

Update rule:
θ = θ - α * ∂L/∂θ


---

### Variants:
- SGD
- Adam (most popular)
- RMSprop
- Adagrad

---

## 9. Learning Rate

Critical hyperparameter.

### Strategies:
- Constant
- Step decay
- Cosine decay
- Warmup schedules

---

## 10. Weight Initialization

Bad initialization → poor training.

### Common Methods:
- Xavier (Glorot)
- He Initialization (for ReLU)

---

## 11. Vanishing & Exploding Gradients

### Vanishing Gradient:
- Gradients → 0
- Stops learning

### Exploding Gradient:
- Gradients → huge
- Unstable training

### Solutions:
- ReLU
- Proper initialization
- Gradient clipping
- Batch normalization

---

## 12. Batch Normalization

Normalizes layer inputs.

Benefits:
- Faster training
- More stable gradients
- Higher learning rates

---

## 13. Dropout

Regularization technique.

### Idea:
Randomly deactivate neurons during training.

Example:
- Dropout = 0.5 → 50% neurons off

---

## 14. Training Process

### Steps:
1. Forward pass
2. Compute loss
3. Backpropagation
4. Update weights

Repeat for many epochs

---

## 15. Epochs & Batches

- **Epoch**: full dataset pass
- **Batch**: subset of data

### Types:
- Batch Gradient Descent
- Mini-batch (most common)
- Stochastic (1 sample)

---

## 16. Overfitting in Deep Learning

Deep models easily overfit.

### Solutions:
- More data
- Dropout
- Data augmentation
- Regularization
- Early stopping

---

## 17. Early Stopping

Stop training when validation loss increases.

Prevents overfitting.

---

## 18. Data Augmentation

Artificially increase dataset size.

### Examples:
- Image rotation
- Flipping
- Cropping
- Noise

---

## 19. Hardware for Deep Learning

### CPU
- General purpose
- Slow for DL

### GPU
- Parallel computation
- Essential for training

### TPU
- Specialized for DL (Google)

---

## 20. Frameworks

### Popular:
- TensorFlow
- PyTorch (most popular today)
- JAX

---

## 21. Convolutional Neural Networks (CNNs)

CNNs are specialized for grid-like data such as images.

### Key Idea:
Automatically learn spatial features.

---

### 21.1 Convolution Operation

Applies filters (kernels) to input:

output = input * kernel


- Detects edges, textures, shapes
- Shared weights → fewer parameters

---

### 21.2 Key Components

#### Convolution Layer
- Extracts features

#### Activation (ReLU)
- Adds non-linearity

#### Pooling Layer
- Reduces spatial size

Types:
- Max Pooling
- Average Pooling

---

### 21.3 CNN Architecture Example

Input → Conv → ReLU → Pool → Conv → Pool → FC → Output


---

### 21.4 Advantages

- Parameter efficiency
- Translation invariance
- Strong performance on vision tasks

---

## 22. Recurrent Neural Networks (RNNs)

Designed for sequential data.

### Use Cases:
- Text
- Time series
- Speech

---

### 22.1 Key Idea

Maintains hidden state:

h_t = f(x_t, h_{t-1})


---

### 22.2 Problems

- Vanishing gradients
- Difficulty learning long-term dependencies

---

## 23. LSTM (Long Short-Term Memory)

Improved RNN architecture.

### Components:
- Forget gate
- Input gate
- Output gate
- Cell state

### Advantage:
- Captures long-term dependencies

---

## 24. GRU (Gated Recurrent Unit)

Simplified version of LSTM.

- Fewer parameters
- Faster training
- Similar performance

---

## 25. Attention Mechanism

Allows model to focus on important parts of input.

### Key Idea:
Not all inputs are equally important.

---

## 26. Transformers

Revolutionized deep learning (especially NLP).

### Key Paper:
"Attention is All You Need"

---

### 26.1 Core Idea

Replace recurrence with attention.

---

### 26.2 Architecture Components

- Self-Attention
- Multi-Head Attention
- Feedforward layers
- Positional Encoding

---

### 26.3 Self-Attention

Computes relationships between all tokens.

Attention(Q, K, V) = softmax(QK^T / √d_k)V


---

### 26.4 Why Transformers Matter

- Parallel processing
- Scalable
- State-of-the-art in NLP, vision, audio

---

## 27. Embeddings

Convert discrete data into dense vectors.

### Examples:
- Word embeddings
- Sentence embeddings
- Image embeddings

### Properties:
- Semantic meaning
- Similar items → close in vector space

---

## 28. Transfer Learning

Reuse pre-trained models.

### Benefits:
- Less data required
- Faster training
- Better performance

---

### Common Strategy:

1. Load pre-trained model
2. Freeze base layers
3. Train top layers
4. Fine-tune entire model

---

## 29. Fine-Tuning

Continue training a pre-trained model on new data.

### Types:
- Full fine-tuning
- Partial fine-tuning
- Parameter-efficient (LoRA, adapters)

---

## 30. Optimization Tricks

### 30.1 Learning Rate Scheduling
- Warmup
- Decay

---

### 30.2 Gradient Clipping
- Prevent exploding gradients

---

### 30.3 Mixed Precision Training
- Faster training
- Lower memory usage

---

### 30.4 Checkpointing
- Save model during training

---

## 31. Regularization in Deep Learning

- Dropout
- Weight decay (L2)
- Data augmentation
- Label smoothing

---

## 32. Debugging Deep Learning Models

### Common Issues:

#### Model not learning
- Learning rate too high/low
- Bad initialization

#### Overfitting
- Model too complex
- Not enough data

#### Unstable training
- Exploding gradients

---

### Debugging Tips:

- Overfit a small batch
- Check data pipeline
- Visualize loss curves
- Inspect gradients

---

## 33. Evaluation in Deep Learning

Same metrics as ML:
- Accuracy
- F1 Score
- RMSE

### Additional:
- Top-K accuracy
- BLEU (NLP)
- Perplexity

---

## 34. Deep Learning vs Traditional ML

| Feature              | Traditional ML      | Deep Learning        |
|---------------------|--------------------|----------------------|
| Feature Engineering | Manual             | Automatic            |
| Data Requirement    | Low–Medium         | High                 |
| Compute             | Low                | High                 |
| Performance         | Good               | State-of-the-art     |

---

## 35. When to Use Deep Learning

Use DL when:
- Large datasets available
- Complex patterns
- Unstructured data (images, text, audio)

Avoid when:
- Small dataset
- Simple problem

---

## 36. Real-World Applications

- Image classification
- Object detection
- Speech recognition
- Machine translation
- Chatbots / LLMs
- Recommendation systems

---

## 37. Model Deployment Considerations

- Model size
- Latency
- Throughput
- Hardware constraints

---

## 38. Deep Learning Pipeline

1. Data collection
2. Preprocessing
3. Model design
4. Training
5. Evaluation
6. Deployment
7. Monitoring

---

## 39. Cheat Sheet Summary

- Neural networks = layers of neurons
- Backpropagation trains the model
- CNNs → images
- RNNs → sequences
- Transformers → everything
- Transfer learning is powerful
- Regularization prevents overfitting
- Debugging is critical

---

## 40. What to Learn Next

After deep learning:

- Transformers in depth
- Large Language Models (LLMs)
- Prompt Engineering
- RAG systems
- AI Agents
- MLOps

---

# End of Deep Learning
