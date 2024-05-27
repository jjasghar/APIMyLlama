
# APIMyLlama Documentation

## Overview

APIMyLlama is a server application that provides an interface to interact with the Ollama API, a powerful AI tool to run LLMs. It allows users to run this alongside Ollama to easily distrubute API keys to create amazing things.

# Installation

## Ollama Setup
If you already have Ollama setup with the 'ollama serve' command and your desired model. You can skip this. If not i'll show you how to set it up. First install [Ollama](https://ollama.com/download) for your desired operating system. Once installed open a terminal instance and run the command below.
```bash
ollama pull llama3
```

If done correctly you should now have the Meta's Llama3 LLM installed. You can use any model with the API but for this example we will use this model. Now you are gonna run this command after the install is complete.
```bash
ollama serve
```
Now you have an Ollama server setup. Time for the next step.

## Hosting the API


Install [Node.JS](https://nodejs.org/en/download/package-manager) on your server. Then clone the git repository.

```bash
git clone https://github.com/Gimer-Studios/APIMyLlama.git
cd APIMyLlama
node APIMyLlama.js
```
After cloning go into the cloned directory and run the APIMyLlama.js file.
On startup it will ask what port you want to use.
```bash
PS C:\Users\EXAMPLE\Documents\APIMyLlama> node APIMyLlama.js
Connected to the apiKeys.db database.
Enter the port number: <ENTER_PORT>
```
Enter the desired port you would like to use with the API. After you choose your port you will NEED to port foward this port if you are gonna use the API Key system OUTSIDE of your network.

## Commands
These are the commands you can use in the APIMyLlama application

```bash
generatekey
```
This command will generate a key using Cryptography and save it to the local database.

```bash
listkey
```
This command will list all API Keys in the database.

```bash
removekey <KEY>
```
This command will remove any key from the database.

```bash
addkey <KEY>
```
You can add custom keys if wanted. (DO with CAUTION as it may be unsafe)

## Working with the API
Install APIMyLlama packages with NPM or PIP

NPM Install
```bash
  cd PROJECT_NAME
  npm install apimyllama-node-package
```
PIP Install
```bash
  cd PROJECT_NAME
  pip install apimyllama
```

Node.JS example:
```bash
const apiMyLlamaNodePackage = require('apimyllama-node-package');

// Intialize Parameters
const apiKey = 'API_KEY';
const prompt = 'Hello!';
const model = 'llama3';
const ip = 'SERVER_IP';
const port = 'SERVER_PORT';
const stream = false;

apiMyLlamaNodePackage.generate(apiKey, prompt, model, ip, port, stream)
  .then(response => console.log(response))
  .catch(error => console.error(error));
  ```

Python example:
```bash
from ApiMyLlama import ApiMyLlama

# Initialize ApiMyLlama with server IP and port
api = ApiMyLlama(ip='SERVER_IP', port='SERVER_PORT')

# Example usage
apiKey = 'API_KEY'
prompt = 'Hello!'
model = 'llama3'
stream = False

try:
    response = api.generate(apiKey, prompt, model, stream)
    print("Response from Ollama API:")
    print(response)
except Exception as e:
    print("Error:", e)
```
## API References
```
ApiMyLlama(ip, port)
ip: IP address of the APIMyLlama server.
port: Port number on which the APIMyLlama server is running.
```
```
api.generate(apiKey, prompt, model, stream)
apiKey: API key for accessing the Ollama API.
prompt: Text prompt to generate a response.
model: Machine learning model to use for text generation.
stream: Boolean indicating whether to stream the response.
```
# Support
If there are any issues please make a Github Issue Report. To get quicker support join our discord server.
-[Discord Server](https://discord.gg/r6XazGtKg7) If there are any feature requests you may request them in the discord server. PLEASE NOTE this project is still in EARLY BETA. 


## Authors

- [@gimerstudios](https://github.com/Gimer-Studios)