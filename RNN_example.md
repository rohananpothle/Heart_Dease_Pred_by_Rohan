# Recurrent Neural Network (RNN) – Example Explanation

## 🧠 Problem: Next Word Prediction

Given the sentence:

"I am feeling very ____"

We want to predict the next word using a Recurrent Neural Network (RNN).

This is called a **Language Modeling** or **Sequence Modeling** problem.

---

## 📌 Step 1: Input Representation (Word Embedding)

Each word is converted into a numerical vector using an **Embedding Layer**.

Example:

- x₁ = "I"
- x₂ = "am"
- x₃ = "feeling"
- x₄ = "very"

Each word becomes a dense vector:

xₜ → Word Embedding Vector

These embeddings capture semantic meaning.

---

## 🔄 Step 2: Hidden State Computation (Memory Update)

At each time step, the hidden state is updated using:

hₜ = tanh(Wₓxₜ + Wₕhₜ₋₁ + b)

Where:

- xₜ = current word embedding
- hₜ₋₁ = previous hidden state
- hₜ = current hidden state
- Wₓ, Wₕ = weight matrices
- b = bias
- tanh = activation function

The hidden state acts as a **memory** of previous words.

---

## ⏳ Time Step Breakdown

### Time Step 1:
Input: "I"

h₁ = f(Wₓx₁ + Wₕh₀)

Memory contains: "I"

---

### Time Step 2:
Input: "am"

h₂ = f(Wₓx₂ + Wₕh₁)

Memory contains: "I am"

---

### Time Step 3:
Input: "feeling"

h₃ = f(Wₓx₃ + Wₕh₂)

Memory contains: "I am feeling"

---

### Time Step 4:
Input: "very"

h₄ = f(Wₓx₄ + Wₕh₃)

Memory contains: "I am feeling very"

This final hidden state is called the **Context Vector Representation**.

---

## 🎯 Step 3: Output Prediction (Softmax Layer)

To predict the next word:

y₅ = Softmax(Wyh₄)

Softmax converts output into probability distribution over vocabulary.

Example Output:

| Word   | Probability |
|--------|------------|
| happy  | 0.62       |
| sad    | 0.21       |
| tired  | 0.10       |
| angry  | 0.07       |

Model selects highest probability → **"happy"**

---

## 📊 Mathematical Objective

The model learns:

P(x₅ | x₁, x₂, x₃, x₄)

Which means:

Probability of the next word given previous words.

---

## 🔥 Interview Summary

- RNN processes sequential data step-by-step.
- Hidden state stores contextual information.
- Final hidden state is used to predict next word.
- Softmax outputs probability distribution.
- Used in NLP, Time Series, and Speech tasks.
