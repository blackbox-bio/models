# Palmreader models

This repository contains all Palmreader pose-estimation models. Every model lives in a folder whose name is a number. Palmreader will, by default, use the model stored in a folder
with the largest number. Palmreader will ignore any folder whose name is not a valid number.

## Structure

Each model directory must contain the following structure:
```
<version number>/
-> config.yaml
-> dlc-models/
--> ... (DeepLabCut defined structure)
-> scorer
```

`config.yaml` and `dlc-models` are stored exactly as produced by DeepLabCut. The `scorer` file must be a text file containing the DLC scorer string (i.e. `DLC_resnet50_arcteryx500Nov4shuffle1_350000`).
If the `scorer` file is missing, the model will be ignored by Palmreader. **If the `scorer` file is incorrect, Palmreader will fail to analyze captures!**

## Note on `project_path` in `config.yaml`

The `project_path` field in the DLC config file is automatically updated to the correct location when the model is used. However, care should be taken to ensure this path is set
correctly **before being committed to this repo**. If this path is wrong, it will be automatically updated which will cause the user's git tree to become dirty, which can break
future `git pull`s.

The `project_path` field should have the following path: `/home/blackbox/.local/share/bio.blackbox.palmreader/models/<version number>`.
