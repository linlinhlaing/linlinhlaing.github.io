---
title: "Introduction to Python"
date: 2024-10-21T17:12:25-05:00
draft: false
tags: ["Python","Basic", "Learning notes"]
categories: ["Python"]
---

### Python

- Born on February 20, 1991.
- An open source (free), high-level, object-oriented, interpreted and general-purpose dynamic programming language.
- Easiest to learn among programming languages! (But slow!)
    
    - Gaining popularity over the past ten years, especially for ML and DL.


### Python version

- For machine learning, particularly neural network deep learning, it’s recommended to use Python 3.8 due to compatibility issues with TensorFlow in later Python versions. Many versions of TensorFlow work more reliably with Python 3.8, avoiding potential problems found in Python 3.9 or newer



### Applications of Python
- Website development
- Software and Mobile Apps development
- Scientific and numeric computing, etc.


### Python libraries
**NumPy** - for numerical computation

**Pandas** - for data processing and analysis(text data)
**Matplotlib,Seaborn** - for creating beautiful visualizations

**SciPy** - scientific computing

**Scikit-learn (sklearn)** - machine learning algorithms

**HadooPy , PySpark** for big data processing



### Basic rules and concepts of Python
**Identifiers**: names of entities (class, functions, and variables)

- Letters (case sensitive), any digits (0, ..., 9), and underscore are used.
- Keywords cannot be used as identifiers.
- Cannot start with a digit! 9x.
- Cannot use special symbols like %, $, &, and !.

**Keywords**

Reserved words to define syntax and structure of Python. Case sensitive and all are in lowercase except True,False, and None.

- True, False, None, and, or, as, with, import, from, is
- if, elif, else, not
- for, in, while, break, pass, continue
- try, lambda, enumerate, zip
- class, def
- global, nonlocal. etc.

**Suite**:

lines of code starting **with a header line in control statement**.

- Header lines begin with **a key word** such as if, for, and while, and end with **a colon**, :
{{< figure src="/images/first-post/suite.png" alt="Suite" width="400" >}}


**Block**: lines of code in functions.

**Snippet**: a small portion of code.

### Clear, concise, and compact coding
- Indentation
- Use blank lines for distinguishing code blocks.
- Use the hash (#) for writing a comment line.
- Use triple quotes (''''' xxx''''') for writing multiple comment lines.
- Use docstrings (''''' xxx''''') for explaining purposes or usages of scripts, functions, and classes.
- docstrings အဖြစ်ရေးမယ်ဆို function ရဲ့ ပထမဆုံးlineမှရေးမှရ ပီးရင် help(function name) နဲ့ခေါ်လို့ရ
- Triple code နဲ့ မဟုတ်ဘဲ single quote နဲ့လဲရ but function ရဲ့ ပထမဆုံးလိုင်းမှတော့ရေးဖို့လို

eg: ***docstrings using single quote***
{{< figure src="static/images/first-post/docString-single.png" alt="docString-single" width="400" >}}

eg: ***docstrings using triple quote***
{{< figure src="/images/first-post/docString-triple.png" alt="docString-triple" width="400" >}}

- For efficient coding and code reuse, use classes! Creating **classes** is the beauty of coding and determines **your coding capacity.**

<!-- Python is dynamically typed, meaning both values and their types are stored in memory. Each time an operation is performed, including during a for-loop, Python checks the type of each element, which slows down execution. This frequent type checking and storage of type information make pure Python inefficient for handling large datasets compared to statically typed languages or optimized libraries. -->