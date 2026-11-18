Ophelia Week 8, Day 2

## RAG (Retrieval Augmented Generation) based on a dataset of 800,000 scraped Amazon products\n",
    "\n",
    "#### For our 2nd agent, we will be asking OpenAI to estimate the price of one of our deals - and we will give it a hand.\n",
    "\n",
    "We discovered that LLMs are really good at this, out of the box.\n",
    "\n",
    "And we discovered that we can beat a frontier LLM by fine-tuning an open-source LLM.\n",
    "\n",
    "Now we are going to try **inference time** techniques instead of training -- by using RAG!"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "2db71ba5-55a8-48b7-97d5-9db8dc872837",
   "metadata": {},
   "outputs": [],
   "source": [
    "# imports\n",
    "\n",
    "import os\n",
    "import logging\n",
    "from dotenv import load_dotenv\n",
    "from huggingface_hub import login\n",
    "import numpy as np\n",
    "import re\n",
    "from sentence_transformers import SentenceTransformer\n",
    "import chromadb\n",
    "from sklearn.manifold import TSNE\n",
    "import plotly.graph_objects as go\n",
    "from litellm import completion\n",
    "from tqdm.notebook import tqdm\n",
    "from agents.evaluator import evaluate\n",
    "from agents.items import Item"
  }

## The Encoder Model

The Encoder model makes Chroma Database a vector Database.

### t-SNE
Stands for t-distributed Stochastic Neighbor Embedding.
It is a common technique for reducing dimensionality of data.

### Linear Regression

## all-MiniLM

all-MiniLM is a very useful model for using for tasks like semantic search, that maps sentences and Paragraphs to 384 dimensional vectors and is ideal for tasks like Semantic Search.

As an alternative, OpenAI provides a cloud-source Embeddings Model.

Benefits Compared to OpenAI Embeddings:

1. It is free
2. It is fast
3. It can be run locally, so data never leaves our PC

Useful when building a personal RAG.
