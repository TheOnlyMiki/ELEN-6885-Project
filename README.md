---

## **ELEN 6885 - Reinforcement Learning**

## Reward Shaping for Battery Control in CityLearn: Penalizing Peak Increases and Export Waste

### [**FINAL PROJECT NOTEBOOK**](./project.ipynb)

### [**FINAL PROJECT REPORT**](./Report.pdf)

### JingZeng Xie (jx2668@columbia.edu), Linghao Tian (lt3035@columbia.edu)

---

# Environment

The environment we used for CityLearn:
- Conda environment name - citylearn-dev
- CUDA: 11.0
- cudnn: 8.0
- Python 3.9.23
- OS: Windows 11

# Instructions for Windows

1. Create the Conda/Miniconda virtual environment
```
conda conda create -n citylearn-dev python=3.9 -y
```
2. Activate the virtual environment
```
conda activate citylearn-dev
```
2. Clone the repository from GitHub
```
git clone https://github.com/TheOnlyMiki/ELEN-6885-Project.git
```
3. Navigate into the repository
```
cd ELEN-6885-Project
```
4. Install the dependency libraries for the project
```
pip install -e .
pip install -r requirements.txt
```

If you have any trouble with pip install,  use `conda install -c conda-forge <package_name>`.

Make sure those libraries match:
```
citylearn=2.1.2
ipywidgets=8.1.8
gym=0.25.2
gymnasium=1.1.1
numpy=1.26.4
scikit-learn==1.0.2
stable_baselines3==2.7.1
```

5. Testing CityLearn
```
python -c "from citylearn.citylearn import CityLearnEnv; env=CityLearnEnv('citylearn_challenge_2023_phase_2_local_evaluation', central_agent=True); obs,_=env.reset(); print('OK')"
```
If the terminal displays `OK` without any errors, then you're good to go.

# Notebooks

The Jupyter Notebook file [project](./project.ipynb) in the main directory is the primary workflow for our project. Detailed explanations, descriptions, and experiments can be found in the respective ipynb files.

# CityLearn Introduction
CityLearn is an open-source Farama Foundation Gymnasium environment for the implementation of Multi-Agent Reinforcement Learning (RL) for building energy coordination and demand response in cities. A major challenge for RL in demand response is the ability to compare algorithm performance. Thus, CityLearn facilitates and standardizes the evaluation of RL agents such that different algorithms can be easily compared with each other.

![Demand-response](./assets/images/dr.jpg)

## CityLearn Environment Overview

CityLearn includes energy models of buildings and distributed energy resources (DER) including air-to-water heat pumps, electric heaters and batteries. A collection of building energy models makes up a virtual district (a.k.a neighborhood or community). In each building, space cooling, space heating and domestic hot water end-use loads may be independently satisfied through air-to-water heat pumps. Alternatively, space heating and domestic hot water loads can be satisfied through electric heaters.

![Citylearn](./assets/images/environment.jpg)

## CityLearn Documentation
Refer to the [docs](https://intelligent-environments-lab.github.io/CityLearn/).

**CityLearn Developed by:** José, a member of the [SoftCPS](https://www2.isep.ipp.pt/softcps/), Software for Cyber-Physical Systems research group (ISEP, Portugal) in collaboration with the Intelligent Environments Lab, University of Texas at Austin.
