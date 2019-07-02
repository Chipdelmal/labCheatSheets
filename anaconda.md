# Anaconda Environments


Activate environment:

```bash
source activate ENV_NAME
```

```bash
conda activate ENV_NAME
```

Deactivate environment:

```bash
conda deactivate
```

Export to **YML**:

```bash
conda env export > FILENAME.yml
```

Add to the Jupyter/Hydrogen kernels list:

```bash
source activate ENV_NAME
python -m ipykernel install --user --name ENV_NAME
```

Create environment from **YML**:

```bash
conda env create -f FILENAME.yml
```

List environments:

```bash
conda list
```

Uninstall environment:

```bash
conda env remove -n ENV_NAME
```

List environments:

```bash
conda info --envs
```
