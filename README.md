# Genetic Algorithms for Hollow Knight Route Optimization

This project applies **Genetic Algorithms (GAs)** to solve a constrained optimization problem inspired by the video game *Hollow Knight*.  
The goal is to optimize the route taken through game areas in a session to **maximize Geo earnings** while respecting multiple constraints.

Developed as the **Final Project for Optimization Algorithms (NOVA IMS, 2024)**.

---

## Tech Stack

- **Python 3.10+**
- **NumPy** – numerical operations
- **Pandas** – data handling (optional for dataset preparation)
- **Matplotlib** / **Seaborn** – visualization of runs and performance
- **Jupyter Notebook** – for experimentation and testing

---

## Repository Structure

~~~text
.
├─ src/
│  ├─ main.py                # final GA implementation (ready to run with dataset)
│  ├─ operators.py           # custom crossover and mutation operators
│  ├─ selection.py           # selection algorithms
│  ├─ utils.py               # helper functions
├─ notebooks/
│  └─ experiments.ipynb      # exploratory GA runs and analysis
├─ data/
│  └─ example_dataset.csv    # example valid dataset (Geo gains/losses matrix)
├─ docs/
│  └─ OA_finalproject_2024.pdf   # project report
├─ requirements.txt
├─ README.md
└─ LICENSE
~~~

---

## Optimization Problem

- **Objective**: Maximize *Geo* earnings during a game session.  
- **Areas**: 10 areas, abbreviated (e.g., Dirtmouth = D, Stag Nest = SN).  
- **Constraints**:
  - Route must start and end in **Dirtmouth (D)**.  
  - King’s Station (KS) may be skipped, but if so, **DV must follow QS**.  
  - City Storerooms (CS) cannot directly follow Queen’s Gardens (QG).  
  - Resting Grounds (RG) can only appear in the second half of the session.  
  - Transition G → FC must yield at least 3.2% less Geo than the minimum of all other positive gains.  

The dataset is structured as a **matrix (list of lists)** where each row corresponds to an area and values indicate Geo gains/losses when moving to another area.

---

## Methodology

1. **Representation**  
   - Individuals encode routes as sequences of areas.  
   - Constraints applied during generation & mutation.  

2. **Genetic Operators**  
   - At least **3 crossover operators** implemented.  
   - At least **3 mutation operators** implemented.  

3. **Selection Mechanisms**  
   - Roulette wheel, tournament, rank-based selection tested.  

4. **Grid Search & Robustness**  
   - Performed ≥15 runs with different configurations & random seeds.  
   - Chose final operator set and hyperparameters based on comparative results.  

---

## Evaluation

- **Implementations**: quality, efficiency, and originality of operators.  
- **Methodology**: grid search strategy and robustness across runs.  
- **Model Performance**: tested against unseen datasets.  
- **Report**: literature review, methodology, and results with plots.  

---

## How to Run

1. Clone this repository:
   ~~~bash
   git clone https://github.com/<your-username>/genetic-algorithms-hollowknight-optimization.git
   cd genetic-algorithms-hollowknight-optimization
   ~~~

2. Install dependencies:
   ~~~bash
   pip install -r requirements.txt
   ~~~

3. Run the final model with a dataset:
   ~~~bash
   python src/main.py --data data/example_dataset.csv
   ~~~

---

## Requirements

See [`requirements.txt`](./requirements.txt).
