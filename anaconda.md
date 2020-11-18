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

Create environment:

```bash
conda create -n ENV_NAME python=3.6
```

<hr>

Export to **YML**:

```bash
conda env export > FILENAME.yml
```

Create environment from **YML**:

```bash
conda env create -f REQUIREMENTS.txt
```

Export requirements to **txt** file:

```bash
conda list -e > REQUIREMENTS.txt
```

Import requirements from **txt** file:

```bash
conda create -n new ENV_NAME --file REQUIREMENTS.txt
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
