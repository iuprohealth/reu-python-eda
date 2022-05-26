# Exploratory Data Analysis with Python - ProHealth REU Summer 2022

## Abstract

You've collected some data about the thing you're interested in.
What do you do with it? How can form further research questions?
[Exploratory data analysis](https://en.wikipedia.org/wiki/Exploratory_data_analysis)
is part a part of a [data science](https://en.wikipedia.org/wiki/Data_science)
or statistics workflow that typically involves summarizing, visualizing, and
doing preliminary modeling. Here we'll work our way up to EDA in Python,
starting with a quick introduction to the language, then working on some
skills for "[Scientific Programming](https://en.wikipedia.org/wiki/Scientific_programming_language)."

## Introduction

Notebooks are available in this repository:

| Notebook | Colab Link | View on GitHub |
| :---- | :---- | ----: |
| Intro Python | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iuprohealth/reu-python-eda/blob/main/notebooks/00-intro-python.ipynb) | [`00-intro-python.ipynb`](https://github.com/iuprohealth/reu-python-eda/blob/main/notebooks/00-intro-python.ipynb) |
| Scientific Programming | [![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iuprohealth/reu-python-eda/blob/main/notebooks/01-scientific-programming.ipynb) | [`01-scientific-programming.ipynb`](https://github.com/iuprohealth/reu-python-eda/blob/main/notebooks/01-scientific-programming.ipynb) |

We'll work with Python and Jupyter as a [literate programming](https://en.wikipedia.org/wiki/Literate_programming)
environment.

Instead of thinking about programs as scripts:

```python
class LinearModel:

    def __init__(self):
        self.parameters = None

    def fit(self, X, y):
        X = np.hstack([np.ones(X.shape), X])
        self.parameters = np.linalg.inv(X.T @ X) @ (X.T @ y)

    def predict(self, X):
        X = np.hstack([np.ones(X.shape), X])
        return X @ self.parameters

if __name__ == "__main__":

    lm = LinearModel()
    print(lm.parameters)
```

We'll build up a program as a series of steps, executed in "*cells*."

### Libraries

Not all of these are covered here, but these are some of the common libraries for exploring data:

- [`numpy`](https://numpy.org/): "*The fundamental package for scientific computing with Python*"
- [`pandas`](https://pandas.pydata.org): "a fast, powerful, flexible and easy to use open source data analysis and manipulation tool, built on top of the Python programming language"
- [`matplotlib`](https://matplotlib.org/): "a comprehensive library for creating static, animated, and interactive visualizations in Python"
- [`seaborn`](https://seaborn.pydata.org/): "A Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics"
- [`scikit-learn`](https://scikit-learn.org/stable/): "Machine learning in Python. Simple and efficient tools for predictive data analysis."
- [`statsmodels`](https://www.statsmodels.org/): "Classes and functions for fitting statistical models, running tests, and exploration"

### Some "Gotcha's"

- In Jupyter, programs are broken into "*cells*." Cells may be executed in any order,
  and the order of execution can change the result. **As a best practice**: if you work
  in a notebook, try to keep the cells in a logical order.
