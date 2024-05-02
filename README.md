## Setup Environment
Helping You Code Faster


### 1. Setup New Anaconda/Conda Environment
1. Go to Start and Type 'Anaconda Prompt'

2. Create New Anaconde Environment
conda create --name myenv python=3.8
conda env list
conda activate myenv

3. Install Required Libraries
# Initiating with Pytorch
conda install pytorch torchvision torchaudio -c pytorch

# For CPU Only PC 
# conda install pytorch torchvision torchaudio cpuonly -c pytorch

# For Compatible GPU
# conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch


# Installing Python Libraries
conda install numpy pandas matplotlib scikit-learn

# Installing Tensorflow (Depending on Requirements)
conda install tensorflow

# Installing Jupyter Notebook
conda install jupyter

# Verify INstallinations
# Type Python in Command Prompt and Go into Python Terminal 
python

# If Python installed, Exit by Typing "Ctrl + V" & Enter

# To Check List of Libraries in Environment
conda list



# Learn CUDA Deployment Next
### PENDING ###

