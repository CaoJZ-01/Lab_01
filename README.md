# CSI5386: Natural Language Processing  
## Assignment 1: Corpus analysis and sentence embeddings

## Part1


## Part2
To run the program, use this command:  
```  
$ python main.py --SE  
```  
SE is the name of the sentence embedding model you would like to choose. There are five models provided:  
SBERT  
UniversalSentenceEncoder  
Skipgram  
NNLM  
Vertex  
If you do not specify a model, the program will choose SBERT as default.  

External resources are used for each model, and here is how to use them:  
### 1. SBERT
We use [SentenceTransformer](https://www.sbert.net/) to load a pre-trained SBERT mode. It is realized as below:  
```
from sentence_transformers import SentenceTransformer  
model = SentenceTransformer("all-MiniLM-L6-v2")  
```  
### 2. UniversalSentenceEncoder  
We load a pre-trained Universal Sentence Encoder model on Kaggle in the program:  
```
module_url = "https://tfhub.dev/google/universal-sentence-encoder/4"  
model = hub.load(module_url)  
```  
### 3. Skipgram 
We load a pre-trained Skip-gram model on Kaggle in the program:  
```
module_url = "https://tfhub.dev/google/universal-sentence-encoder/4"  
model = hub.load(module_url)  
```  
### 4. NNLM 
We load a pre-trained NNLM model on Kaggle in the program:  
```
module_url = "https://tfhub.dev/google/universal-sentence-encoder/4"  
model = hub.load(module_url)  
```  
### 5. Vertex  
We use APIs provided by Google Vertex AI to get access to the pre-trained sentence embedding model based on generative LLM. To use these APIs, please follow the steps below:  
Ⅰ Create a project on the Google Cloud platform  
Ⅱ Enable Vertex AI API for the project  
Ⅲ Add a service account for the project and create a key (.json file) on this account  
Ⅳ Add the key, which is a .json file, to your local project directory  
Ⅴ In sentencessimilarity.py, set the GOOGLE_APPLICATION_CREDENTIALS:  
```
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "YOUR_KEY_LOCATION"  
```  

Please note that since the key is confidential and using Vertex AI API may cause fee, we do not include the key in the zip. Your own key is needed if you would like to choose Vertex as the sentence embedding model.


