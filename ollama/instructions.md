# ollama model



## github for demo and instructions
https://github.com/EnkrateiaLucca/llama2_oreilly_live_training/tree/main

for ollam see:  
https://github.com/EnkrateiaLucca/llama2_oreilly_live_training/blob/main/notebooks/1.0-quickstart-ollama.ipynb


## download ollama 
This is the URL to download ollama
https://ollama.com/download/mac



## create virtualenv and install ollama cli

here is what commands i ran
```
 485  cd virtualenv
  486  ls
  487  mkdir venv_ollama
  488  cd venv_ollama/
  489  python3 -V
  490  python3 -m venv ./venv --prompt="venv_ollama"
  491  ls
  492  source venv/bin/activate
  493  python -m pip list
  494  python -m pip install ollama
  495  ls
  496  git clone https://github.com/EnkrateiaLucca/llama2_oreilly_live_training.git
  497  python -m pip install llama2_oreilly_live_training/requirements/requirements.txt
  498  python -m pip install -r llama2_oreilly_live_training/requirements/requirements.txt
  499  python -m pip install python-dotenv
  500  ollama pull gemma3:1b
  501  ollama
  502  vi test1.py
  504  python test1.py
  505  ls -alrt
  506  vi test1.py
  507  python test1.py
  508  ollama list
  -->
  displays the model youhave chosen in your script

```

This is the content of the script
```
# pwd = /Users/aliansari/virtualenv/venv_ollama
import ollama

response = ollama.chat(model='gemma3:1b', messages=[
  {
    'role': 'user',
    'content': 'Say hello to my students for the course: "Getting Started with Llama 3". One single sentence.',
  },
])
print(response['message']['content'])

```

## using cli
doc: https://docs.ollama.com/cli 

This is how i did it

```
(venv_ollama) aliansari@Alis-MacBook-Air: ~/virtualenv/venv_ollama $ ollama run gemma3:1b
>>> Hello. Can you tell me what LLM is?
Okay, let's break down what an LLM is – it’s a really hot topic right now! Here's a breakdown of what it means:

```


## using streamlit

this was a question i aksed:
```
sorry Lucas.. how did you get to port 8501 as in the UI localhist:8501 ... how would i open this port?

streamlit does that for us, to run this use streamlit run app-name .py
```

so this is what i did in my virtualenv

```
(venv_ollama) aliansari@Alis-MacBook-Air: ~/virtualenv/venv_ollama $ python -m pip install streamlit
(venv_ollama) aliansari@Alis-MacBook-Air: ~/virtualenv/venv_ollama $ streamlit run test1.py

-->
this opens in your browser port 8501
http://localhost:8501/

```
