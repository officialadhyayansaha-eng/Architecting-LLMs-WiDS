# Week 1: The Engine of AI (Autograd & Backpropagation)

> **"You cannot understand the neural network unless you build the neural network."**

Welcome to Week 1! We are skipping the high-level APIs (like `torch.nn` or `Keras`) and going straight to the metal.

This week, you will build **micrograd**: a tiny Autograd engine. You will implement the mathematical machinery that allows neural networks to learn. By the end of this week, the "magic" of how ChatGPT or Stable Diffusion updates its weights will be demystified—it's just the Chain Rule, applied recursively.

## Learning Objectives

* **Understand the Computation Graph:** How mathematical expressions are built as trees of operations.
* **Master Backpropagation:** How to recursively apply the Chain Rule to calculate gradients.
* **Build the `Value` Object:** Creating a Python class that tracks its own history and gradients.
* **Train a Neuron:** Using your custom engine to train a simple perceptron to classify data.

---

## Optional: Python OOP Refresher

**Status:** *Optional (Skip if you are comfortable with Classes, `__init__`, and `__repr__`)*.

The core assignment relies heavily on Python's Object-Oriented Programming (OOP) features. [cite_start]If you need a refresher, these are the **Corey Schafer** tutorials referenced in the course PDF[cite: 8]:

* [cite_start]**[Tutorial 1: Classes and Instances](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)** - The basics of `class`, `self`, and `__init__`[cite: 8].
* [cite_start]**[Tutorial 2: Class Variables](https://www.youtube.com/watch?v=BJ-VvGyQxho)** - Sharing data between all instances[cite: 8].
* [cite_start]**[Tutorial 3: Class Methods and Static Methods](https://www.youtube.com/watch?v=rq8cL2XMM5M)** - The `@classmethod` and `@staticmethod` decorators[cite: 9].
* [cite_start]**[Tutorial 4: Inheritance - Creating Subclasses](https://www.youtube.com/watch?v=RSl87lqOXDE)** - How to extend classes (crucial for PyTorch later)[cite: 9].
* [cite_start]**[Tutorial 5: Special (Magic/Dunder) Methods](https://www.youtube.com/watch?v=3ohzBxoFHAY)** - **Essential:** How to override `__add__` and `__mul__`[cite: 9].
* [cite_start]**[Tutorial 6: Property Decorators](https://www.youtube.com/watch?v=jCzT9XFZ5bw)** - Using `@property` for getters and setters[cite: 10].

---

## The Lecture

[cite_start]**Video:** [The spelled-out intro to neural networks and backpropagation: building micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0) [cite: 16]
* **Duration:** ~2 hours 30 mins
* **Instructor:** Andrej Karpathy

**Advice:** Do not just watch. **Type along.** Pause the video, implement the method, and inspect the variables.

---

## Star Resources (The "Why" & "How")

Before or during your coding, use these resources to visualize the math.

### 1. Visual Intuition (Highly Recommended)
* **[But what is a Neural Network?](https://www.youtube.com/watch?v=aircAruvnKk)** (3Blue1Brown) - The high-level view of layers and weights.
* **[Gradient Descent, how neural networks learn](https://www.youtube.com/watch?v=IHZwWFHWa-w)** (3Blue1Brown) - Visualizing the "cost landscape."
* **[What is backpropagation really doing?](https://www.youtube.com/watch?v=Ilg3gGewQ5U)** (3Blue1Brown) - The best visual explanation of the chain rule.

### 2. Reference Code
* **[micrograd GitHub Repo](https://github.com/karpathy/micrograd)** - Karpathy's original code. Use this to debug if you get stuck.

---

## The Assignment

**Goal:** Complete the Micrograd exercises in the provided notebook.

### Step 1: Get the Notebook
1.  Navigate to the **`week1/`** folder in your forked repository.
2.  Open the file `week1_assignment.ipynb`.
3.  Click the **"Open in Colab"** badge (if available) or simply upload this file to [Google Colab](https://colab.research.google.com/).

### Step 2: Implement the `Value` Object
Follow the instructions in the notebook cells. You will need to fill in the missing code for:
* **Basic Arithmetic:** `__add__`, `__mul__`, `__pow__`.
* **Activations:** The `tanh` or `relu` function.
* **Backpropagation:** The `backward()` method and the topological sort.

### Step 3: Train the MLP
The final cells of the notebook will ask you to use your new `Value` class to build a small `MLP` (Multi-Layer Perceptron) and train it on a binary classification dataset.

---

## Submission

1.  **Save your work:**
    * In Colab, go to `File` > `Save a copy in GitHub`.
    * Select your **forked repository**.
    * Ensure the file path matches **`week1/week1_assignment.ipynb`** so it updates the existing file.
    * Commit message: "Week 1: Completed Micrograd Exercises".
2.  **Verify:** Check your forked repo on GitHub to ensure your changes are visible.

**Next Week:** We move from scalar values to **Tensors** and start building language models!
