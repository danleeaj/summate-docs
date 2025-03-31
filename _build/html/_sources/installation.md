# Installation

The autograder is written using Ollama as the inference engine. Therefore, we must first install Ollama.

## Installing Ollama

1. Download and install Ollama (https://ollama.com/).
2. Check that installation was completely successfully by running the following code in your terminal:
```commandline
$ ollama --version
ollama version is 0.6.2
```
3. Pull a model ([list of models](https://ollama.com/search)). We recommend installing `llama3.1:8b`.
```commandline
$ ollama pull llama3.1:8b
pulling manifest 
pulling 667b0c1932bc... 100% ▕█████▏ 4.9 GB
verifying sha256 digest 
writing manifest 
success 
```
:::{important}
If you installed a model that's not `llama3.1:8b`, write down the model name. We'll have to update `config.py` later on.
:::
4. Verify that the download was successful by listing out all installed models.
```commandline
$ ollama list
NAME        ID              SIZE      MODIFIED      
llama3.1:8b 46e0c10c039e    4.9 GB    8 seconds ago  
```
5. You can also test out inference by chatting with the model!
```commandline
$ ollama run llama3.1:8b
success
>>> Hello!
It's nice to meet you. Is there something I can help you with, 
or would you like to chat?
>>> /bye
```

## Using the autograder

Now that Ollama has been installed, we can start using the autograder.

6. Clone and access the repository.
```commandline
$ git clone https://github.com/danleeaj/summate-ai.git
```
7. Install all dependencies with pip...
```commandline
$ pip install ollama langchain-ollama
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ...or with uv
```commandline
$ uv sync
```
8. Traverse to `summate-ai/src/hello.py` to access the autograder.
:::{important}
If you installed a model different from `llama3.1:8b` in step 3, go to `config.py` and update the model name under the constant `MODEL`.
:::
9. Update your rubric and student response and run the script!

In the next section, we will provide you with a step-by-step explanation of everything happening in the code.