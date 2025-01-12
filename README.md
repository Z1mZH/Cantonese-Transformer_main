# Cantonese-Transformer_main
  This is the source code of  our Deep Learning Project: Cantonese-Transformer based on Llama3-8B and PPO
### Basic Settings
  In order to run this project, you first need to configure the relevant environment. The hardware environment for this project is Intel Xeon Silver 4310 CPU @ 2.1GHz, NVIDIA GeForce RTX 4090 * 3. The software environment is PyCharm 2022.3, Python 3.11, CUDA 12.4, Torch 2.4.1+cu124, vllm
  The hyperparameters of the project are set as follow: batch size is set as 128, learning rate is 10e-4.
  To start with, please install all dependent environment.
  ```
pip install torch 2.4.1+cu124
pip install vllm
pip install transformer
```
  Please make sure that your cuda devices are available, due to the huge number of parameters in the comparison method, pure CPU computation is completely incapable of doing this job. It is best to set up a clustered working environment with two or more RTX 4090 graphics cards to accelerate the model training.

### Training of Oral Llama3-8B, Mistral-7B and Falcon-7B 
  Oral Llama3-8B, Mistral-7B and Falcon-7B are training with llama-factory.
  
