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

