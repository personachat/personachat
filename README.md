Further development has been [moved to Codeberg](https://codeberg.org/personachat/personachat).

# PersonaChat

## About

**PersonaChat is currently in an early alpha. Not all features are guaranteed to work properly, and errors may occur.** Please do not use PersonaChat in a production environment.

### Overview

PersonaChat is a free and open-sourced system which allows you to easily chat with a limitless number of customizable personalities. Using quantization, PersonaChat can achieve decent speeds on consumer hardware without GPUs.

### How does it work?

Currently, PersonaChat uses an un-finetuned LLM. We are currently using OpenLLaMA 7B, a 7 billion parameter model trained on 1 trillion tokens from the RedPajama dataset. Unlike the original LLaMA, OpenLLaMA is licensed under the Apache 2.0 license, a permissive license.

## Installation & Usage

The different components of PersonaChat have been split into multiple repositories and use multiple programming languages.

We are eventuallyA compiled binary

### Requirements

Before you begin, please ensure that you meet the following requirements:

- macOS/Linux/Windows (Apple Silicon Supported)
  
- Python >= 3.9
  
- A PHP + MySQL stack
  
  - PHP >= 7.4 (PHP 8 supported)
    
  - MySQL
    

Additionally, if you'd like to run PersonaChat with decent speed:

- \>= 16 GB RAM
  
- \>= 8 CPU cores
  

### Start the Backend

Clone the backend server:

```shell
git clone "https://github.com/personachat/backend"
cd backend
```

Download the models:

```shell
wget "https://huggingface.co/personachat/model-hosting/resolve/main/ol7b_q4_1.bin" -O "models/ggml-model-q4_1.bin"
```

Start the server:

```shell
cd pc_webui
python3 main.py
```

Warning: if you run `python3 pc_webui/main.py` instead of `cd`ing into the `pc_webui` directory, the model will not be able to load.

**Important:** Leave the backend running when you start your frontend!

## Start the Frontend

Download the frontend:

```shell
git clone "https://github.com/personachat/webui"
```

Modify `config.php` in your favorite code editor. If you did everything normally while running the backend, the default configuration should be fine. Update the MySQLi configuration for your MySQL server.

Start your MySQL server and run [this](https://raw.githubusercontent.com/personachat/webui/main/INSTALL.sql) SQL script.

Set the directory of your PHP server to the `webui` folder you cloned using `git`, then visit the GUI on your localhost.

Congratulations, you've successfully started PersonaChat!
