# aider-Local
- Its a fork, the main is, [here](https://github.com/paul-gauthier/aider) or [here](https://aider.chat/).
- Fork Status: Beta - Tested and working, further development planned.

### DESCRIPTION:
- The aider-Local project includes a set of batch scripts designed to facilitate the setup and execution of the aiDEr application in a local environment. The aiDEr-Local.Bat script serves as a user-friendly launcher, providing options to run the application with various configurations, including different models and file inputs. It ensures that settings are preserved across sessions through a persistence mechanism, enabling consistent operation without requiring reconfiguration. The accompanying Install-Setup.Bat script automates the environment setup, detecting the necessary Python installation, installing dependencies, and ensuring that the environment is properly configured. Together, these scripts provide a streamlined and reliable workflow for managing and running the aider application locally.

### FEATURES:
- Enforces administrator privileges to ensure proper execution and saving of files.
- Provides an interactive menu for selecting different modes to run the aiDEr application.
- Supports model management, allowing users to select, delete, and configure models for Ollama.
- Handles configuration persistence through a persistence.txt file to save and load settings across sessions.
- Detects and configures the Python environment, including automatic installation of required packages.
- Allows for the execution of aiDEr with or without file inputs, adapting to various use cases.
- Includes error handling and user prompts for guidance during setup and execution.
- Verifies and installs essential Python packages, such as setuptools and wheel, to ensure a stable environment.
- If all that has'nee made you moist, it also has the ability to select the folder that contains your files.

### PREVIEW:
- The `aiDEr-Local.Bat` Main Menu...
```
========================================================================================================================
                                                   AiDEr-Local Launcher
========================================================================================================================


    1. Run Aider with Ollama and Selected Model

    2. Run Aider with Ollama and Selected Model and Files

    3. Run Aider with Ollama and Selected Model and Files from Folder

    4. Manage Ollama Settings


------------------------------------------------------------------------------------------------------------------------

    * Model Selected:
DeepSeek-Coder-V2-Lite-Instruct:latest

    * Threads Used:
0

    * Python Location:
C:\Users\Mastar\AppData\Local\Programs\Python\Python312\python.exe

========================================================================================================================
Selection; Menu Options = 1-4, Exit Batch = X:

```
- The `aiDEr-Local.Bat` Running with Ollama...
```
========================================================================================================================
                                                     aiDEr-Local
========================================================================================================================

Starting Ollama server...
Setting API Base...
Running Aider with Ollama model...
No git repo found, create one to track aider's changes (recommended)? (Y)es/(N)o [Yes]: n
Model ollama/DeepSeek-Coder-V2-Lite-Instruct: Unknown context window size and costs, using sane defaults.
Did you mean one of these?
- ollama/deepseek-coder-v2-lite-instruct
For more info, see: https://aider.chat/docs/llms/warnings.html


Aider v0.54.0
Model: ollama/DeepSeek-Coder-V2-Lite-Instruct with whole edit format
Git repo: none
Repo-map: disabled
Use /help <question> for help, run "aider --help" to see cmd line args
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
> make me a maze game.



```
- The `Setup-Install.Bat` Main Menu...
```
========================================================================================================================
                                                     Setup-Installer
========================================================================================================================


    1. Re-Install Setup Tools

    2. Install `.\Requirements.Txt`

    3. ModelFile Management


------------------------------------------------------------------------------------------------------------------------


    * Admin Status:
Administrator

    * Working Folder:
D:\ProgsOthers\aiDEr-Local\aider-0.54.0

    * Python Location:
C:\Users\**UserName**\AppData\Local\Programs\Python\Python312\python.exe


========================================================================================================================
Selection; Menu Options = 1-3, Exit Batch = X:

```
- The `Setup-Install.Bat` model install magic...
```
========================================================================================================================
                                             Ollama Model Management
========================================================================================================================



    * Available Ollama models:
NAME                                    ID              SIZE    MODIFIED
deepseek-coder-v2-lite-instruct:latest  34ddb66744d3    17 GB   20 hours ago




 =======================================================================================================================
Selection; Install ModelCard = I, Remove Modelcard = R, Back to Menu = B: i
Enter the full path to the model including filename: L:\TEXT\mradermacher\Meta-Llama-3.1-Chat-Uncensored-GGUF\Meta-Llama-3.1-Chat-Uncensored.Q5_K_M.gguf
Enter the full path to the ModelFile: L:\TEXT\mradermacher\Meta-Llama-3.1-Chat-Uncensored-GGUF\Meta-Llama-3.1-Chat-Uncensored.Q5_K_M.modelfile
Model name will be: meta-llama-31-chat-uncensored-gguf
Is this model name okay? (Y/N): n
Do you want to use the model file name instead? "meta-llama-31-chat-uncensoredq5km" (Y/N):
Is this model name okay? (Y/N): n
Please enter the desired model name: meta-llama-31-chat-uncensored
Model name will be: meta-llama-31-chat-uncensored
Is this model name okay? (Y/N): y
Installing Model to Ollama...
transferring model data ⠏

```


## REQUIREMENTS:
- Windows v7-v11?? - version 10 is the, programming and testing, platform, and thats non-WSL.
- Python v3.9-3.12 - USes whatever Python version is specified by the user in `Install-Setup.Bat`
- Aider v0.54.0 - Launch commands/arguments are designed for this version, others work unless they changed.

### USAGE: 
1. Even though My batches will detect the location of Python, I do notice that `aider` is unable to be used with python in `Program Files`, so do NOT install python for all users or `aider` will have issues.
2. Copy aider from the zip to a suitable directory, ie `D:\Programs\aider-0.5x.x`.
3. The files are dropped into relevantly `D:\Programs\aider-0.5x.x` or whatever folder. 
4. Run the batch `Install-Setup.Bat`, it will for setup and install of requirements, this includes, `setup-tools` and `requirements.txt`.
5. Ensure model is loaded in LM Studio, or otherwise that you have installed the model in Ollama (see folder .\modelfiles). 
6. Run The batch `aiDEr-Offline.Bat`, to, configure models/threads, and launch aider with, LM Studio or Ollama, with options to include files.

### NOTATION:
- If you have issues with `No filename provided before ``` in file listing`, then ensure to specify the files (albeit blank ones) at launch, I also found that when I .
- The batch located at `.\tools\Extract-Aider.Bat`, will extract aider zips in its own directory to an appropriate folder, using 7z installed in the default location. This is useful if windows is giving issues with, paths or folders, during extraction.
- In `aiDEr-Local.Bat`, When selecting model, you would copy and paste, for example `DeepSeek-Coder-V2-Lite-Instruct:latest`, not `DeepSeek-Coder-V2-Lite-Instruct`.
- As you can tell from the threads settings for ollama, its currently designed for CPU users, but if you are on GPU, then you will want to, specify a number that relates to the number of shaders or set it to `0` for `auto`. At least I think thats how it works. I have a AMD RX 470, but if you can donate on kofi, maybe I will have a, AMD RX 7600 or GeForce RTX 4060, a little sooner, and these things can be known.
- Whats the best model for aider?? `DeepSeek-Coder-V2-Lite-Instruct` produced the error I am getting every so often. I tried [Meta-Llama-3.1-Chat-Uncensored-GGUF](https://huggingface.co/mradermacher/Meta-Llama-3.1-Chat-Uncensored-GGUF) but I dont think llama-3.1 is compatible with the version of numpy. Maybe the instruct version after, both have 128k context. The meta rounds off its abilities, and uncensored supposedly more intelligent, and its 3.1 not 3.0)... 
```
                    Code Generation
          #TP 	#AP 	HumanEval 	MBPP+ 	LiveCodeBench 	USACO							
CodeStral                      22B 	22B 	78.1 	68.2 	31.0 	4.6
DeepSeek-Coder-Instruct      33B 	33B 	79.3 	70.1 	22.5 	4.2
Llama3-Instruct                70B 	70B 	81.1 	68.8 	28.7 	3.3
DeepSeek-Coder-V2-Lite-Instruct    16B 	2.4B 	81.1 	68.8 	24.3 	6.5
DeepSeek-Coder-V2-Instruct    236B 	21B 	90.2 	76.2 	43.4 	12.1
```

### EXAMPLES:
- Prompt to make a game...
```
Prompt 1 (Start):
the files I have provided 4 files, `data.dat`, `main.py`, `maze_game.bat`, `settings.json`, are all blank files, they are the files, that you should save to, in order to produce the game. A simple maze game in Python, using, `main.py` for main code and `settings.json` for peristent settings and `data.dat` for maps and `maze_game.bat` to run `main.py`, utilize them optimally and logically. Plan it all out, the goal is the completion, the result should be a good demonstration of your abilities. After each significant phase in editing, ensure to save the files, but ensure to save over the files provided with those filenames, do not save files with alternate names. 

Prompt 2 (continue):
please check the current state of all 4 of the scripts. Your work is now... 1. Progress the game towards completion. 2. Ensure the scripts are, logical and sound. 3. Improve the code. 3. upgrade the code. ...And remember, I have provided 4 files, `data.dat`, `main.py`, `maze_game.bat`, `settings.json`, ensure to save to those files, do not save files with alternate names.

Prompt 3 (resume):
Progress the game towards completion. A simple maze game in Python, check the current state of all 4 of the scripts, then your work is... 1. Progress the game towards completion. 2. Ensure the scripts are, logical and sound. 3. Improve the code. 3. upgrade the code. ...And remember, I have provided 4 files, `data.dat`, `main.py`, `maze_game.bat`, `settings.json`, ensure to save to those files, do not save files with alternate names.
```

## DEVELOPMENT:
With the primary project of the batches done...
- Last chance to get it working is, download `Llama 3 Instruct` Q6 for my 64GB system memory. If that dont work then it rests at the point made below.
- Due to repeating errors in using aider on local models, development is stopped/slowed. May be required to wait for advancement of, my own hardware or model technologies/variantes or libraries or aider. I tried altering `.\aider\models.py` in conjunction with updating litellm to latest version, but it still doesnt identify `llama 3.1`. The problem is possibly  between LiteLLM and Ollama, though I cant rule out the models, here making simple maze game with 4 files and the `deepseek v2 lite` model...
```
litellm.APIConnectionError: {"error":"error reading llm response: read tcp 127.0.0.1:50209-\u003e127.0.0.1:50207: wsarecv: An existing connection was forcibly closed by the remote host."}
Traceback (most recent call last):
  File "C:\Users\Mastar\AppData\Local\Programs\Python\Python312\Lib\site-packages\litellm\main.py", line 2415, in completion
    generator = ollama.get_ollama_response(
                ^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "C:\Users\Mastar\AppData\Local\Programs\Python\Python312\Lib\site-packages\litellm\llms\ollama.py", line 269, in get_ollama_response
    raise OllamaError(status_code=response.status_code, message=response.text)
litellm.llms.ollama.OllamaError: {"error":"error reading llm response: read tcp 127.0.0.1:50209-\u003e127.0.0.1:50207: wsarecv: An existing connection was forcibly closed by the remote host."}
```

### DISCLAIMER:
Issues that may arrise as a result of the code when aider is running, are not on the part of aiDEr-Local, as currently it does nothing out of the ordinary to the actual runnings of aider.
