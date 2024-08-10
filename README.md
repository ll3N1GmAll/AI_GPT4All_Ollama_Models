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

rename all symlinks' file extensions from .bin to .gguf, close and reopen GPT4All, models are now available (maybe)

If not..you can make them availble by following the remaining stesp (though it does make a copy of each model. So, this eats up disk space.

Duplicate one or two models to add to GPT4All:
go to /home/<profile>/ollama_model_links/ and find the ollama model you want to use with GPT4All, right click > properties
copy the long sha256:456402914e838a953e0cf80caa6adbe75383d9e63584a964f504a7bbb8f7aad9 string.
go to /usr/share/ollama/.ollama/models/blobs/ and find the blob with that name. right click > copy
go to /home/<profile>/.local/share/nomic.ai/GPT4All/ right click > paste
rename blob to gemma-latest.gguf (or whatever model name), close and reopen GPT4All, model is now available
**********************************************************************************



To add ollama models to LM Studio (work in progress, models recognized; but not working yet):

edit syncmodelsforlmstudio script lines at the top accordingly:
```
base_dir=/usr/share/ollama/.ollama/models/
manifest_dir=/usr/share/ollama/.ollama/models/manifests/registry.ollama.ai/
blob_dir=/usr/share/ollama/.ollama/models/blobs/
publicmodels_dir=~/ollama_model_links_LM/
```
This will create a "library" folder in ```~/ollama_model_links_LM/ ```
copy this "library" folder, in its entirety, and paste it directly in - ```/home/<profile>/.cache/lm-studio/models/```
