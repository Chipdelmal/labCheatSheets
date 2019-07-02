# Jupyter/Hydrogen


Add to the Jupyter/Hydrogen kernels list:

```bash
source activate ENV_NAME
python -m ipykernel install --user --name ENV_NAME
```

Remove from the Jupyter/Hydrogen kernels list:

```bash
jupyter kernelspec uninstall ENV_NAME
```

<hr>

Startup code for **MoNeT_MGDrivE**:

```
{"MoNeT": "%matplotlib inline \nimport os \nimport conda \nconda_file_dir = conda.__file__ \nconda_dir = conda_file_dir.split('lib')[0] \nproj_lib = os.path.join(os.path.join(conda_dir, 'share'), 'proj') \nos.environ['PROJ_LIB'] = proj_lib"}
```
