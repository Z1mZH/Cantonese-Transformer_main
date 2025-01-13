# Cantonese-Transformer_main
  This is the source code of  our Deep Learning Project: Cantonese-Transformer based on Llama3-8B and PPO
### Basic Settings
  - In order to run this project, you first need to configure the relevant environment. The hardware environment for this project is Intel Xeon Silver 4310 CPU @ 2.1GHz, NVIDIA GeForce RTX 4090 * 3. The software environment is PyCharm 2022.3, Python 3.11, CUDA 12.4, Torch 2.4.1+cu124, vllm
  - The hyperparameters of the project are set as follow: batch size is set as 128, learning rate is 10e-4.
  - To start with, please install all dependent environment.
  ```
pip install torch 2.4.1+cu124
pip install vllm
pip install transformer
```
  - Please make sure that your cuda devices are available, due to the huge number of parameters in the comparison method, pure CPU computation is completely incapable of doing this job. It is best to set up a clustered working environment with two or more RTX 4090 graphics cards to accelerate the model training.

### Training of Oral Llama3-8B, Mistral-7B and Falcon-7B 
  - Oral Llama3-8B, Mistral-7B and Falcon-7B are training with a project on GitHub named llama-factory. [https://github.com/hiyouga/LLaMA-Factory/]
  - Using the tool llama-factory, we trained large language models such as LLAMA3-8B, Mistral-7B and Falcon-7B using datasets collected independently by us. To do this, firstly do some basic configurations of llama-factory. Make sure your dependent environment is ready.
```
pip install accelerate
pip install peft
pip install trl
pip install bitsandbytes
```
- Then, download and install llama-factory.
```
git clone --depth 1 https://github.com/hiyouga/LLaMA-Factory.git
cd LLaMA-Factory
pip install -e ".[torch, metrics]"
```
- You can use our prepared datasets provided in our github project Cantonese-Transformer to train the LLM, or you can prepare your own dataset based on the format of the dataset provided in this project. Then, you can start the front-end website or directly utilize lora for training, reasoning and generating.
1. To directly utilize lora for training, reasoning and generating,
```
llamafactory-cli train [your_model.yaml]
llamafactory-cli chat [your_model.yaml]
llamafactory-cli export [your_model.yaml]
```
2. To start the front-end website of llama-factory,
```
llamafactory-cli webui
```
- Once you have completed the above process, all you need is to fine-tune the large language model using the desired dataset and various adjustable parameters in the visualization interface. We have completed the fine-tuning and generation of three comparison LLM (Oral Llama3-8B, Mistral-7B and Falcon-7B) using the Cantonese dataset collected independently.

### Training of Cantonese-Transformer
- To utilize the large language model proposed in this project for Cantonese translation with human feedback reinforcement learning, the first step is to clone this repository.
```
git clone --depth 1 https://github.com//Z1mZH/Cantonese-Transformer_main.git
```
- Then four ipynb files, actor, critic, rlhf and test, are run in the already labeled order, the first file is used to train a generative Cantonese translation large language model, the second file evaluates the large language model of the first file and performs human feedback reinforcement learning, followed by generation and evaluation, and the final experimental results are obtained.
