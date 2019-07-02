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

<hr>

Export to **YML**:

```bash
conda env export > FILENAME.yml
```

Create environment from **YML**:

```bash
conda env create -f FILENAME.yml
```

<hr>


Uninstall environment:

```bash
conda env remove -n ENV_NAME
```

List environments:

```bash
conda info --envs
```

Update anaconda:

```bash
conda update -n base conda
```
