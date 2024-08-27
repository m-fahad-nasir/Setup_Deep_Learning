# Setup Environment
Helping You Code Faster
## Setup New Anaconda/Conda Environment

1. Go to Start and Type 'Anaconda Prompt'
2. Create New Anaconde Environment
```
conda create --name myenv python=3.8
conda env list
conda activate myenv
```
## Install Required Libraries
### Install Pytorch (Basic - Non GPU)
``conda install pytorch torchvision torchaudio -c pytorch``

#### For CPU Only PC (Depends on Situation)
Try this as this generally works better.
``conda install pytorch torchvision torchaudio cpuonly -c pytorch``

### Installing Python Libraries
``conda install numpy pandas matplotlib scikit-learn``

### Installing Tensorflow (Depending on Requirements)
``conda install tensorflow``

### Installing Jupyter Notebook
``conda install jupyter``

### Verify Installinations
Type Python in Command Prompt and Go into Python Terminal 

``python``

If Python installed, Exit by Typing "Ctrl + V" & Enter or "exit()"

To Check List of Libraries in Environment

``conda list``

# Setup NVIDIA GPU for Deep Learning

## Step 1: NVIDIA Video Driver

You should install the latest version of your GPUs driver. You can download drivers here:
 - [NVIDIA GPU Drive Download](https://www.nvidia.com/Download/index.aspx)
 - After Going to the Link Add Your Graphics Card Information.
 - Case Study (Example)
     - GeForce
     - Geforce RTX 30 Series (Notebooks) [3060 is from 30 Series and Notebook is for Laptops]
     - Geforece RTX 3060 Laptop GPU
     - Windows 11
     - English (US)
 - Select Search
 - Download the Driver
 - Install (Next - Next - Next)

![image](https://github.com/user-attachments/assets/e6942cbb-d9ff-4a9d-9a54-3c4da5d85b49)


## Step 2: Visual Studio C++

You will need Visual Studio, with C++ installed. By default, C++ is not installed with Visual Studio, so make sure you select all of the C++ options.
 - [Visual Studio Community Edition](https://visualstudio.microsoft.com/vs/community/)
 - Download & Install (Just need C++ Build Tools - Very Important)
 - When Window og Installion Details Appears, go to Individual Components Tab.
 - Search for following
     - C++ 2022 Redistribution MSMs
     - C++ 2022 Redistribution Update
     - C++ Clang Compiler for Windows
     - C++ Clang-cl for v143 build tools
     - ... (Check Youtube Video from 6:00 https://www.youtube.com/watch?v=nATRPPZ5dGE)
 - Size could be between 15-24 GB install and download.
 - When done, Restart the System
 - To Check Installation Status check (Start Menu and in C:/Program Files/Microsoft Visual Studio/2022/Community)

## Step 3: Anaconda (Can be Done Earlier as well)

You will need anaconda to install all deep learning packages
 - [Download Anaconda](https://www.anaconda.com/download/success)
 - However I already have it so need for this step.

## Step 4: CUDA Toolkit

 - [Download CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit-archive)
 - Go to Anaconda Prompt and ``nvidia-smi``
 - Check Image to Confirm Version, cross-check online for ideal version.
 - Select the Relevant Version by your System Requirements, the Cude Toolkit file could be 3GB+.
 - When Downloaded install the file, go through the steps carefully as it reminds you important things.
 - Check in repository for folders C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.4


![image](https://github.com/user-attachments/assets/64df7a72-4ce1-4593-8268-9355542ef40d)

![image](https://github.com/user-attachments/assets/be55cbcb-b05d-481f-bd10-d753276832d0)

![image](https://github.com/user-attachments/assets/7e2172ad-1448-42a9-8261-007fd2749a31)


## Step 5: cuDNN

 - [Download cuDNN](https://developer.nvidia.com/rdp/cudnn-archive)
 - Select which version is compatible, I selected version = 12.x
 - Download the Zip File.
 - Sometimes NVIDIA asks for you to make an account, login details , etc.. (Long Stuff). To bypass that directly serach for cuDNN on Google.
 - Once file is downloaded, Unzip the file.
 - The file has the following folders:
     - bin
     - include
     - lib
 - You neec to copy these files from "cuDNN" directory to the main CUDA Toolkit directory "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.4"
 - Copy cuDNN bin, include, lib folder files and Paste/Replace in CUDA Toolkit folder.
 - Once done search 'Environment Variables' in Start Menu and check if Paths are set, if not set you have to do them manually. ** I previously added the 'LD_LIBRARY_PATH' I am not sure if it is required or not.

![image](https://github.com/user-attachments/assets/716c3226-0a9e-4c84-adb6-223f2d49c53c)


## Step 6: Install PyTorch 

 - [Install PyTorch](https://pytorch.org/get-started/locally/)


![image](https://github.com/user-attachments/assets/034c009b-ecbc-4644-931b-8a1ff689f94e)





## Finally run the following script to test your GPU

```python
import torch

print("Number of GPU: ", torch.cuda.device_count())
print("GPU Name: ", torch.cuda.get_device_name())


device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
print('Using device:', device)
```
