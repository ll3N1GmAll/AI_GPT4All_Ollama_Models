# AI_GPT4All_Ollama_Models
Process for making all downloaded Ollama models available for use in GPT4All:

git clone https://github.com/technovangelist/matts-shell-scripts/

sudo apt install jq -y

edit syncmodels script lines at the top accordingly:
```
base_dir=/usr/share/ollama/.ollama/models/
manifest_dir=/usr/share/ollama/.ollama/models/manifests/registry.ollama.ai/
blob_dir=/usr/share/ollama/.ollama/models/blobs/
publicmodels_dir=~/ollama_model_links/
```

run ./syncmodels script from ~/matts-shell-scripts folder

optional: go to localdocs tab in settings of GPT4All, then download local docs file SBert

Create links for all Ollama models to be used in GPT4All without duplicating all models (save on disk space):

copy all links in /home/<profile>/ollama_model_links/ and paste them in /home/<profile>/.local/share/nomic.ai/GPT4All/

rename all symlinks' file extensions from .bin to .gguf, close and reopen GPT4All, models are now available



To add ollama models to LM Studio:
edit syncmodelsforlmstudio script lines at the top accordingly:
```
base_dir=/usr/share/ollama/.ollama/models/
manifest_dir=/usr/share/ollama/.ollama/models/manifests/registry.ollama.ai/
blob_dir=/usr/share/ollama/.ollama/models/blobs/
publicmodels_dir=~/ollama_model_links_LM/
```
This will create a "libray" folder in ```~/ollama_model_links_LM/ ```
copy this "library" folder, in its entirety, and paste it directly in - ```/home/<profile>/.cache/lm-studio/models/```
