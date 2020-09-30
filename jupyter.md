# Jupyter/Hydrogen


Add to the Jupyter/Hydrogen kernels list:

```bash
source activate ENV_NAME
python -m ipykernel install --user --name ENV_NAME
```

List available environments:

```bash
ipython kernelspec list
```
Remove from the Jupyter/Hydrogen kernels list:

```bash
jupyter kernelspec uninstall ENV_NAME
```

<hr>

Startup code for **MoNeT_MGDrivE**:

There are two options to fix this. The first one is a bit more obscure but automatic:

```
{"MoNeT": "%matplotlib inline \nimport os \nimport conda \nconda_file_dir = conda.__file__ \nconda_dir = conda_file_dir.split('lib')[0] \nproj_lib = os.path.join(os.path.join(conda_dir, 'share'), 'proj') \nos.environ['PROJ_LIB'] = proj_lib"}
```

Stable Hydrogen version:

```
apm install hydrogen@2.8.0
```

The second one is more manual but clear:

```
import os
os.environ['PROJ_LIB'] = 'PATH_TO_ANACONDA/share/proj'
```
