# langchain-13-min

This is a fork of the code/notebook used in the YouTube video [LangChain Explained in 13 Minutes](https://youtu.be/aywZrzNaKjs) by Rabbitmetrics. The code is slightly modified from the original to use the *Azure* OpenAI LLMs.

## What is LangChain?

LanchChain is an open source framework that allows AI developers to combine LLMs like GPT-4 with external sources of computation and data.
For a great quickstart tutorial for beginners and how to use this code, watch the [video](https://youtu.be/aywZrzNaKjs) first.

## Prerequisites

* An [Azure account](https://azure.microsoft.com/en-us/pricing/details/cognitive-services/openai-service/) with an active subscription. Note: If you don't have access to an Azure subscription, you may be able to start with a [free account](https://www.azure.com/free).
* A (free or paid) [Pinecone Vector database](https://www.pinecone.io/) account to run the vector search examples.
* If you want to run the code in the Jupyter Notebook on your local machine, you'll need a recent version of [Python 3](https://www.python.org/downloads/) and a Notebook runner (e.g. [Visual Studio Code](https://code.visualstudio.com/)) installed.

## Preparations

* Go to the [Azure OpenAI Studio](https://oai.azure.com/portal) and create 3 model deployments:
    * Deployment name: `text-davinci-003` (model: text-davinci-003)
    * Deployment name: `gpt-35-turbo` (model: gpt-35-turbo)
    * Deployment name: `text-embedding-ada-002` (model: text-embedding-ada-002)
* Click the 'gear' icon in the top-bar of Azure AI Studio, select the 'Resource' tab and:
    * Copy-paste the `Endpoint` of your Azure AI resource into the `OPENAI_API_BASE` variable (see `./notebooks/.env` file)
    * Copy-paste the `Key` of your Azure AI resource into the `OPENAI_API_KEY` variable (see `./notebooks/.env` file)
* Go to your [Pinecone environment](https://app.pinecone.io/), create a new project (picking any environment) and then create a new index named `langchain-quickstart` (metric=cosine, dimensions=1536)
* Copy-paste the environment where your Pinecone project is hosted into the `PINECONE_ENV` variable (see `./notebooks/.env` file)
* Create a new Pinecone API key, and copy-paste that into the environment variable `PINECONE_API_KEY` (see `./notebooks/.env` file)

## Installing python libs

* Open a command prompt and type: 
```
pip install -r requirements.txt
```

## Running example Notebook
* Open the file `./notebooks/langchain-13-min.ipynb`.

When using Visual Studio Code, you can simply click the notebook and then execute its cells step by step.