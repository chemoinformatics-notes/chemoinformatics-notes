
Getting Started: The Structure of a Chemoinformatics Dataset. 

Before diving into the details of molecular representation and how computers interpret chemical structures, let’s take a look at the image below.
Any proper chemoinformatics project begins with a dataset containing at least two colums.

The **first column** lists all $n$ entries (observations or molecules) measured in our experiment. Each molecule is associated with a starting representation—most commonly a **SMILES code** (we will return to the fact that a SMILES string is not always unique for a given molecule).


The **second column** contains the **endpoint** values, often referred to as the target variable or label in machine learning.     What is an Endpoint? An endpoint represents the biological or chemical property measured in an experiment. Common examples in chemoinformatics and bioinformatics include permeability (Papp A-to-B), activity (IC50), binding affinity ($K_d$, $K_i$), solubility, and lipophilicity ($\text{LogD}$). 

So, for every observation in the dataset, there is a corresponding endpoint value, and this can be **Categorical**: $y_i$ belongs to a discrete set of classes (e.g., active vs. inactive, high vs. low permeability) or **Continuous**: $y_i$ spans a continuous space of real numbers ($y_i \in \mathbb{R}$).

This one is our starting point :) 

<img width="812" height="373" alt="table_smile_output" src="https://github.com/user-attachments/assets/c8eec90e-85cc-4b09-a183-22677e2dcb83" />

**What does it mean to represent a molecule?**

Humans can interpret a molecule from the way it's drawn on paper — as a graph, where atoms are the nodes and bonds are the edges. This representation is especially useful for us when comparing two similar molecules and spotting their differences (we'll come back to this concept later).

For a computer, however, this process is far from trivial.

**Variables, Features, and Descriptors**

Before we can talk about how to represent a molecule numerically, we need to introduce the **concept of variables** (also called features or descriptors). These are typically grouped into three main classes:

**1D representations**

1D representations are simple linear encodings — the classic example is SMILES. Strictly speaking, SMILES is a representation rather than a descriptor: it's extremely useful for storing, exchanging, and reconstructing a molecule's structure, but on its own it doesn't provide the kind of quantitative, comparable information needed for most modeling tasks.

**2D descriptors**

2D descriptors are more interesting for quantitative work and especially useful for structural comparison and match-pair analysis (how to find match pairs: structural analogs with minor structural differences).

This class includes:

**numerical descriptors** — scalar properties computed from the molecular graph. The sets of numerical descriptors will define a space (the chemical space) where the molecule (the observation i-th) will be represented as a vector. 

**molecular fingerprints** — a large and important family of representations in their own right

We'll cover fingerprints in more detail in other posts. 

**3D descriptors**

3D descriptors depend on a molecule's conformation. We'll return to these further on, since computing them properly (conformer generation, energy minimization, etc.) adds a fair amount of complexity.

