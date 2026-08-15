
Getting Started: The Structure of a Chemoinformatics Dataset. 

Before diving into the details of molecular representation and how computers interpret chemical structures, let’s take a look at the image below.
Any proper chemoinformatics project begins with a dataset containing at least two **core columns **
The **first column** lists all $n$ entries (observations or molecules) measured in our experiment. Each molecule is associated with a starting representation—most commonly a **SMILES code** (we will return to the fact that a SMILES string is not always unique for a given molecule).
The **second column** contains the **endpoint**, often referred to as the target variable or label in machine learning.     What is an Endpoint? An endpoint represents the biological or chemical property measured in an experiment. Common examples in chemoinformatics and bioinformatics include permeability ($\text{P}_{\text{app}}$ A-to-B), activity ($\text{IC}_{50}$), binding affinity ($K_d$, $K_i$), solubility, and lipophilicity ($\text{LogD}$). 

So, for every observation in the dataset, there is a corresponding endpoint value, and this can be **Categorical**: $y_i$ belongs to a discrete set of classes (e.g., active vs. inactive, high vs. low permeability) or **Continuous**: $y_i$ spans a continuous space of real numbers ($y_i \in \mathbb{R}$).

This one is our starting point :) 

<img width="812" height="373" alt="table_smile_output" src="https://github.com/user-attachments/assets/c8eec90e-85cc-4b09-a183-22677e2dcb83" />

